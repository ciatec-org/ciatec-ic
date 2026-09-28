# Ritmo — Variáveis Propostas (N-Back)

---

## 1. Classificação de variáveis

### 1.1 Settings/Config
Fixo para a sessão inteira.

| Variável | Descrição |
| --- | --- |
| `control_scheme` | Mouse ou touchscreen. |
| `master_volume` | Volume global, 0–100 (GP-02). |
| `narration_enabled` | Narração de fundo dos timestamps, para acessibilidade auditiva. |
| `block_color_scheme` | Paleta customizável dos blocos de resposta, para evitar rejeição por hiperfoco em cor (seção 7.3 do SGDD). |
| `mediator_override_enabled` | Se o dashboard clínico de calibração manual está ativo nesta sessão (essencial para S3, opcional para S1). |
| `session_duration_limit` | Teto de segurança de sessão (GP-04). |
| `timestamp_sync_mode` | Como o timestamp do estímulo é sincronizado entre Unity e o backend FastAPI. A seção 13 do SGDD já marca a latência dessa comunicação como risco de dessincronizar o tempo de reação medido — este parâmetro deve existir e ser logado, não resolvido silenciosamente. |
| `stimulus_modality` | Enum de alto nível: hoje só `audio` implementado; estrutura já prevê `visual`, `spatial`, `dual` como valores futuros. Decide em runtime como interpretar os campos de estímulo (ver seção 4). |

### 1.2 Level
Uma "fase" = um conjunto de timestamps entre pausas de questionamento. Muda dentro da mesma sessão, inclusive dentro da mesma música/sequência.

| Variável | Descrição |
| --- | --- |
| `n_back_distance` | 0 a 3, ou travado pelo mediador via `locked_n_back`. Decide toda a geração da sequência de estímulos da fase — é o primeiro parâmetro a ser fixado. |
| `presentation_interval` | Intervalo entre timestamps. Em áudio se expressa como `bpm` (60–120); generalizado para não ficar preso à modalidade musical (ver seção 4). |
| `phase_duration` | 15–45s, padrão 30 — quantos timestamps cabem na fase antes da pausa. |
| `attempts_allowed` | Padrão 3, mas ajustável dinamicamente pelo sistema (seção 4.3 do SGDD) — não é constante entre fases. |
| `stimulus_source_id` | Aponta para a fonte de estímulos da fase — música/track em áudio, banco de formas/posições em modalidades futuras (ver seção 4). Uma música pode conter várias fases. |
| `num_questions_per_phase` | Quantidade de questionamentos por fase ("um ou mais", hoje sem faixa definida no SGDD). |
| `match_ratio` | Proporção de questionamentos que são match verdadeiro vs. não-match. Sem isso balanceado (~50%), a criança pode aprender o padrão e parar de usar memória de fato. |
| `lure_rate` | Proporção de estímulos que se repetem, mas em distância diferente de N (ex.: 2 passos atrás em vez de 4). Equivalente direto do "distrator espelhado" do jogo de Mental Rotation — é o principal eixo de dificuldade real do N-Back na literatura, e hoje não existe no SGDD do Lucas. Recomenda-se incluir. |

### 1.3 Captura de eventos (discretos)

| Evento | Descrição |
| --- | --- |
| `session_start` / `session_end` | Início e fim da sessão. |
| `phase_start` / `phase_end` | Início e fim de uma fase. |
| `stimulus_presented` | Carrega `timestamp_index`, `stimulus_id`, `stimulus_type`. |
| `probe_presented` | Estímulo reexibido para julgamento; carrega o gabarito `target_lag = N` e `is_match` — dado bruto necessário para rastreabilidade (hoje o SGDD só fala em "resposta sim/não", sem deixar explícito que o match verdadeiro também precisa ser logado). |
| `response_registered` | `response_value`, `response_timestamp`. |
| `attempt_consumed` | Decremento do contador de tentativas ao errar. |
| `phase_repeated` | Contador zerou; mesmo padrão de estímulo tocado novamente (seção 4.3 do SGDD). |
| `phase_advanced` | Avanço de fase. |
| `adaptive_adjustment_applied` | Ação tomada pelo motor de RL: subir N, subir velocidade, manter parâmetros ou facilitar. A seção 5.3 do SGDD já descreve isso como "Ação" do sistema — precisa virar evento registrado, não só efeito invisível. |
| `mediator_variable_locked` / `mediator_variable_unlocked` | Travamento/destravamento manual de N-Back ou velocidade pelo terapeuta. |
| `mediator_soft_interrupt_triggered` | Acionamento da "Interrupção Branda" para o modo Treino. |
| `training_mode_entered` / `training_mode_exited` | Entrada e saída do modo Treino Pré-Jogo. |
| `reward_unlocked` | Liberação da música/sequência completa ao final. |
| `pause` / `resume` | Pausa e retomada. |

### 1.4 Telemetria contínua

Pelo desenho atual (clique/toque discreto em sim/não), não há sinal contínuo de movimento a capturar — mesma situação do jogo de Mental Rotation. O único candidato seria a posição do cursor/dedo entre `probe_presented` e o clique final (mesmo argumento de hesitação por gesto discutido no documento do Meu Pequeno Reino), mas isso não está descrito no SGDD do Lucas hoje — é uma decisão a acrescentar, não algo que já decorre do documento.

### 1.5 Métricas derivadas centrais

`reaction_time = response_timestamp − probe_presented_timestamp`; `accuracy` por fase; `consecutive_correct_streak` (já é o próprio estado que o motor de RL usa como input, seção 5.3 do SGDD); e a trajetória de `n_back_distance`/velocidade ao longo da sessão — importante logar como série discreta por fase, não só o valor final, para não perder a curva de adaptação, que é o próprio objeto de interesse científico aqui.

---

## 2. Como criar uma fase

Diferente dos outros dois jogos, aqui a fase não é só um conjunto de parâmetros — ela precisa gerar uma **sequência de estímulos temporizados** internamente coerente com o `n_back_distance` escolhido, senão o questionamento "isso ocorreu N passos atrás?" não tem resposta calculável.

Ordem de dependência:

1. **`n_back_distance`** — decide tudo que vem depois; a sequência só pode ser gerada sabendo qual distância vai ser cobrada.
2. **`presentation_interval`** — fixa o espaçamento real entre timestamps; determina a janela de tempo que o jogador tem para reter o estímulo.
3. **`stimulus_source_id`** — de onde vêm os estímulos que preenchem cada timestamp.
4. **Geração da sequência de estímulos por timestamp** — ponto central: a sequência precisa ser construída (não aleatória pura) para garantir repetições válidas na distância N, senão nunca existe um "match" possível de testar.
5. **`match_ratio`** — balancear questionamentos match/non-match (~50%), para evitar que a criança aprenda o padrão sem usar memória de fato.
6. **`lure_rate`** — proporção de repetições em distância errada, para forçar discriminação real de N.
7. **`phase_duration`** / quantidade de timestamps — quantos cabem na fase antes da pausa.
8. **`num_questions_per_phase`** e em quais timestamps os `probe_presented` acontecem dentro da fase.
9. **`attempts_allowed`** para essa fase.

### Decisão pendente

Se a geração da sequência de estímulos é determinística/pré-autorada por fase (mais fácil de reproduzir entre sessões e comparar usuários, como recomendado para o HelpIR) ou gerada em tempo real a cada partida. Precisa ser confirmada com o Lucas.

---

## 3. Multimodalidade futura (áudio → visual/espacial/dual)

O N-Back é agnóstico de modalidade por definição no paradigma — variantes clássicas incluem N-Back visual (formas, posição espacial, letras), auditivo (o que o Ritmo já implementa) e dual N-Back (visual + auditivo simultâneos). O construto medido é memória de trabalho, não o canal sensorial.

Preparação estrutural, sem exigir redesenho quando a modalidade visual for implementada:

- `stimulus_modality` (Config) — enum de alto nível decidindo como o resto do schema é interpretado. Hoje só `audio`.
- `stimulus_source_id` (Level) — generalização de `song_id`/`stimulus_track_id`: aponta para um som, uma imagem ou uma posição, dependendo da modalidade.
- `presentation_interval` (Level) — generalização de `bpm`: tempo entre timestamps, expresso como BPM em áudio, como intervalo em ms sem conotação musical em modalidade visual.
- Tudo o resto (`n_back_distance`, `stimulus_id` por timestamp, `match_ratio`, `lure_rate`, eventos, métricas derivadas) já é agnóstico de modalidade — nenhuma mudança necessária.

Implementar uma nova modalidade no futuro significa apenas: setar `stimulus_modality` para o novo valor e construir o renderer correspondente. Eventos e variáveis de telemetria permanecem os mesmos.

