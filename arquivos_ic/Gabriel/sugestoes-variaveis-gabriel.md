# Meu Pequeno Reino — Variáveis Propostas (Mental Rotation)

---

## 1. Classificação de variáveis

### 1.1 Settings/Config
Fixo para a sessão inteira.

| Variável | Descrição |
| --- | --- |
| `platform` | Plataforma em uso (mobile/Flutter ou Unity — ainda em aberto no SGDD, seção 7.4/13). Afeta diretamente a precisão do timestamp de tempo de reação, se RT for usado cientificamente. |
| `audio_volume` / `audio_enabled` | Controle de volume e liga/desliga (GP-02). |
| `visual_effects_intensity` | Redução global de animações/estímulos não essenciais durante o trial (GP-02/GP-05). |
| `reading_dependency_mode` | Quanto de texto vs. só ícone/áudio é exibido na interface (GP-01). |
| `session_purpose` | `training` ou `analysis` — se todos os trials da sessão contam para análise científica ou são só prática. Só cabe em Config se o modo não puder alternar dentro da mesma sessão; caso contrário, vira campo por trial (ver 1.3). |
| `session_duration_limit` / `max_trials_per_session` | Tetos de segurança, quando definidos (hoje "ainda não definida" no SGDD, seção 11.1). |
| `interaction_mode` | `drag` ou `single_click` — decisão pendente (seção 2) que determina se existe ou não telemetria contínua de gesto de decisão, podemos usar ambos. |

### 1.2 Level
Muda entre blocos de trials — aqui funciona como "camada de demanda cognitiva", não como fase espacial.

| Variável | Descrição |
| --- | --- |
| `structural_complexity_tier` | Nível de complexidade da estrutura 3D comparada — eixo principal do paradigma. |
| `rotation_magnitude` | Disparidade angular entre referência e peça candidata — a variável clássica de Shepard-Metzler; é ela que gera a curva RT × ângulo. |
| `stimulus_set_id` | Qual conjunto de objetos está em uso (abstrato vs. concreto — o SGDD já observa que isso muda o efeito, seção 5.3). |
| `distractor_similarity` | O quanto a peça estruturalmente diferente se parece com a referência — controla se dá pra resolver por pista local em vez de rotação mental de fato. |
| `trials_per_tier` | Quantos trials compõem este nível de demanda. |
| `hesitation_threshold` / `error_threshold` | Limiares que disparam a redução silenciosa de demanda (equivalente ao GP-04 aqui). |

### 1.3 Captura de eventos (discretos)

| Evento | Descrição |
| --- | --- |
| `session_start` / `session_end` | Início e fim da sessão. |
| `villager_arrival` | Abertura narrativa do trial (chegada do habitante com a peça). |
| `stimulus_presented` | Carrega `reference_id`, `candidate_id`, `rotation_magnitude` e o gabarito `structural_match` (mesma estrutura ou não). Precisa ser dado bruto — não deriva de "acerto/erro" já calculado. |
| `response_registered` | `response_value`, `response_timestamp`. |
| `trial_completed` | Fecha o trial. |
| `streak_updated` | Incrementa ou zera a streak. |
| `feedback_presented` | Qual tipo de feedback foi mostrado — o próprio SGDD marca o efeito do feedback explícito como "ponto de validação" pendente (seção 4.2), por isso vale registrar o que foi exibido em cada trial, não só que houve feedback. |
| `demand_adjustment_applied` | Redução silenciosa de complexidade/rotação. |
| `pause` / `resume` | Pausa e retomada. |
| `session_interrupted_by_mediator` | Interrupção por sinais de desconforto em contexto supervisionado (seção 11.2). |
| `tutorial_step_completed` | Conclusão de etapa do onboarding. |
| `trial_purpose` | `training` ou `analysis`, por trial — alternativa a travar isso em Config, caso treino e análise possam se misturar na mesma sessão. |

### 1.4 Telemetria contínua

Não se aplica ao objeto em si (rotação livre proibida por DP-01). Mas se aplica ao **gesto de decisão**, condicionado a `interaction_mode`:

- **Se `interaction_mode = drag`** (peça arrastada até um slot de aceitar/rejeitar ou até o Grande Livro): `pointer_position (x,y)` amostrado do início do trial até soltar; `drag_start_timestamp` / `drag_end_timestamp`. Métricas derivadas possíveis: `path_curvature`/`trajectory_deviation` (o quanto o caminho até a resposta foi direto vs. cheio de desvio — indica conflito de decisão) e `reversal_count` (mudanças de direção do cursor antes de soltar). É o mesmo tipo de biomarcador de hesitação já usado no HelpIR, aplicado ao gesto em vez ao deslocamento do jogador.
- **Se `interaction_mode = single_click`** (botões discretos "compatível"/"incompatível", sem arrastar nada): não há o que capturar continuamente — só o clique final. Telemetria permanece puramente discreta (seção 1.3).

Eye-tracking foi mencionado como possibilidade futura, mas está fora do escopo atual do SGDD — não é requisito hoje.

### 1.5 Métricas derivadas centrais

`reaction_time = response_timestamp − stimulus_timestamp` e `accuracy`, sempre cruzadas com `rotation_magnitude` — é esse cruzamento que reproduz a curva de Shepard-Metzler e justifica logar `structural_match` como dado bruto, não apenas o acerto/erro já calculado.

---

## 2. Decisão pendente

`interaction_mode` (drag vs. clique único) não está fechado no SGDD (seção 7.4 trata a interação como "a definir"). Essa escolha não é só estética — ela decide se o jogo tem ou não um biomarcador extra de hesitação/conflito de decisão via gesto. Recomenda-se registrar essa pendência explicitamente na seção 13 do SGDD do Gabriel.