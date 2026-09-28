# HelpIR — Variáveis, Level Design e Condições de Vitória


---

## 1. Classificação de variáveis

Segue o modelo Controlled/Observed/Derived (Session → Condition → Level → Trial → Stimulus → Response → Telemetry → Metric). Cada variável foi alocada em uma das quatro categorias abaixo conforme o critério: **muda por sessão inteira → Config; muda por fase → Level; é um acontecimento discreto → Event; é um valor amostrado ao longo do tempo → Telemetria contínua.**

### 1.1 Settings/Config
Fixo para a sessão inteira (ou por perfil/dispositivo). Não muda entre fases.

| Variável | Descrição |
| --- | --- |
| `control_scheme` | Método de entrada ativo (teclado, mouse ou touch); define qual ganho de input abaixo se aplica. |
| `input_gain_keyboard` | Sensibilidade de giro/avanço por pressionamento de tecla. |
| `input_gain_mouse` | Ganho de rotação/deslocamento por unidade de movimento do mouse. |
| `input_gain_touch` | Sensibilidade/deadzone dos botões virtuais em tela touch. |
| `audio_volume` / `bgm_enabled` | Volume geral e liga/desliga da música de fundo. |
| `session_duration_limit` | Teto de segurança de tempo para a sessão inteira (ex.: 30 min), independente da fase em curso. Interrompe por segurança, não por fracasso. |
| `adaptive_support_enabled` | Liga/desliga geral do mecanismo de regressão silenciosa (GP-04). Útil para desativar em sessões de validação/protocolo onde se quer medir desempenho sem intervenção adaptativa do backend. |
| `max_intersections` | Teto de intersecções possíveis; usado também para dimensionar o tamanho da fábrica. |
| `max_signs` | Teto de placas possíveis na fábrica. |
| `num_sectors` | Quantidade total de setores existentes no jogo. |
| `max_deliveries` | Teto de entregas possíveis por sessão. |

### 1.2 Level
Muda por fase; calibra a progressão de dificuldade.

| Variável | Descrição |
| --- | --- |
| `level_id` | Identificador da fase. |
| `map_id` / `level_layout_id` | Referência ao layout fixo (grid de tiles) usado nesta fase — ver seção 2. |
| `robot_speed` | Velocidade de deslocamento do robô nesta fase. |
| `sign_visibility_time` | Tempo/nitidez de exibição da placa antes de ficar (parcial ou totalmente) encoberta. |
| `smoke_density` | Intensidade do efeito que oculta placas na fase. |
| `blockage_probability` | Chance de um corredor `blockable` aparecer bloqueado na fase. |
| `perturbation_layer` | Quais perturbações estão ativas na fase: nenhuma, só fumaça, só bloqueio, ou combinada. |
| `num_intersections_active` | Quantas intersecções do mapa estão em uso nesta fase. |
| `num_signs_active` | Quantas placas estão presentes nesta fase. |
| `num_sectors_active` | Quantos setores de entrega estão disponíveis nesta fase. |
| `max_deliveries` (por fase) | Quantas entregas compõem a fase. |
| `phase_duration_target` | Duração-alvo da fase (10–20 min, conforme seção 5.1 do SGDD). |
| `hesitation_threshold` / `error_threshold` | Limiares que, se ultrapassados, disparam a regressão silenciosa do GP-04 nesta fase. |
| `blocked_corridor_ids` | Quais tiles `blockable` estão bloqueados nesta sessão/fase. |
| `delivery_targets` | Lista de setor + cor esperada por entrega (a cor da placa deve bater com a cor do setor). |
| `spawn_position` + `spawn_facing` | Posição e direção inicial do robô. |
| `random_seed` | Semente usada para sortear **perturbações** (quais tiles ficam bloqueados/ocultos) em cima do layout fixo — não gera a topologia do mapa em si (ver seção 2). |

### 1.3 Captura de eventos (discretos)

| Evento | Descrição |
| --- | --- |
| `session_start` / `session_end` | Início e fim da sessão. |
| `phase_start` / `phase_end` | Início e fim de uma fase. |
| `package_collected` | Robô pega um pacote para entrega. |
| `intersection_reached` | Robô chega a um ponto de decisão (o "estímulo" do paradigma). |
| `direction_chosen` | Corredor escolhido na intersecção (a "resposta"). |
| `sign_occluded_encountered` | Jogador encontra uma placa oculta/encoberta. |
| `corridor_blocked_encountered` | Jogador encontra um corredor bloqueado. |
| `delivery_attempted` | Tentativa de entrega em um setor (setor tentado vs. setor-alvo; não gravar já como certo/errado — isso é derivado depois). |
| `delivery_completed` | Entrega concluída com sucesso. |
| `backtrack_detected` | Robô inverte a direção — sinal comportamental de recálculo de rota. |
| `pause` / `resume` | Pausa e retomada da sessão. |
| `adaptive_adjustment_applied` | Backend reduziu fumaça/bloqueio silenciosamente — muda a condição experimental em andamento, por isso precisa virar evento, não só efeito invisível. |
| `session_interrupted_by_mediator` | Interrupção manual pelo terapeuta/cuidador (REQ-P3-03). |
| `tutorial_step_completed` | Conclusão de uma etapa da Fase 0 (tutorial). |
| `phase_completed` / `phase_failed_safety_timeout` | Ver seção 3 (condição de vitória). |

### 1.4 Telemetria contínua

| Sinal | Descrição |
| --- | --- |
| `robot_position (x,y,z)` | Posição do robô ao longo do tempo. |
| `robot_orientation` | Direção/ângulo do robô ao longo do tempo. |
| `robot_velocity` | Velocidade instantânea. |
| `input_active` | Tecla/botão pressionado no momento (amostrado). |

A partir desses sinais + eventos, derivam-se as métricas já prometidas no SGDD (3.2 e REQ-P3-01): **latência angular na intersecção** (tempo entre `intersection_reached` e o primeiro input de rotação), **eficiência de rota** (distância percorrida ÷ distância mínima possível dado o bloqueio ativo) e **suavidade de trajetória** (variação de velocidade/aceleração no trecho).

---

## 2. Construção do nível — grid de tiles

Proposta: matriz XY de tiles, cada tile com um tipo (`floor` ou `wall`). A conectividade do caminho é implícita pela adjacência — dois tiles `floor` vizinhos já formam um caminho conectado. Não é necessário um campo `connections` explícito (isso só seria útil com peças pré-desenhadas de formato fixo, tipo dungeon com peças "reto"/"curva"/"T", que não é o caso aqui).

### 2.1 Propriedades de cada tile

- `tile_id` / coordenada — referência única na matriz.
- `tile_type` — `floor` ou `wall`. Muro é estrutural e fixo: nunca vira caminho, não muda entre fases.
- `blockable` (só em tiles `floor`) — indica se aquele tile pode ser sorteado para receber o obstáculo dinâmico (fumaça/bloqueio) nesta sessão. `floor + blockable = false` garante que sempre existe ao menos uma rota livre até o setor.
- `intersection_flag` — marca se o tile é um ponto de decisão (onde a telemetria de hesitação/latência angular é capturada). Nem todo tile de corredor é intersecção.
- `sign_slot` — posição/orientação da placa dentro do tile, quando houver uma ali.
- `smoke_eligible` — se o tile pode receber o efeito de ocultação.
- `sector_entrance` — marca o tile como destino de entrega de um setor específico.
- `start_point` + `spawn_facing` — posição inicial e direção para onde o robô olha ao chegar.
- `end_point` — facing de saída, análogo ao start point.
- `recovery_point` (equivalente a "checkpoint") — ponto de retorno caso o robô fique preso ou a sessão seja pausada/retomada; como o jogo não tem "morte" nem game over, é melhor tratar como ponto de recuperação, não de penalidade.
- `collectible` — se há um coletável no tile (pacote, por exemplo).
- `detour_option` — marca um desvio/rota alternativa disponível a partir daquele ponto.

### 2.2 Progressão de dificuldade

Duas dimensões independentes que sobem juntas ao longo das fases:

1. **Complexidade estrutural do grid** — mais intersecções, mais ramificações, mais setores acessíveis (varia `map_id`/`level_layout_id` por fase).
2. **Intensidade da perturbação** — mais fumaça, mais bloqueio, combinação das duas (`perturbation_layer`, `smoke_density`, `blockage_probability`).

Fases iniciais: grid simples, perturbação baixa ou nula. Fases finais: grid mais ramificado, perturbação combinada — coerente com a "Fase 5 combinada" descrita no SGDD (seção 5.2).

### 2.3 Decisão pendente

O SGDD não define como o layout (grafo de corredores) é gerado. Proposta discutida: **layout fixo e pré-desenhado por fase** (não procedural), com `random_seed` aplicado só às perturbações (quais tiles `blockable`/`smoke_eligible` ficam ativos nesta sessão), não à topologia. Isso preserva a reprodutibilidade entre usuários e sessões (SGDD, 7.10), o que geração procedural do labirinto complicaria. **Precisa ser confirmado pela equipe e registrado na seção 13 do SGDD.**

---

## 3. Condição de vitória

### 3.1 O que está implícito hoje no SGDD

Não há uma seção que defina isso explicitamente. Pelo texto (5.1, 7.1), a fase termina quando o robô completa `max_deliveries` entregas corretas. Não há condição de derrota: sem vidas, sem perda de pontuação, sem tela de "Game Over" — isso é explícito em várias partes (feedback, GP-04, REQ-P1-02). O único limite existente é o teto de segurança de tempo (`session_duration_limit`), que interrompe por segurança, não por fracasso.

### 3.2 É possível mudar

Sim — nada obriga a vitória ser "completar N entregas". Alternativas possíveis:
- Vitória por tempo (navegar/operar por X minutos sem travar).
- Vitória por sequência de decisões corretas (streak).
- Combinação: completar as entregas dentro do `phase_duration_target`.

### 3.3 Decisão pendente

A condição de vitória precisa ser formalizada — hoje só é inferível pela frase "isso acontece até a fase se finalizar" (7.1). Recomenda-se registrar a escolha final na seção 13 do SGDD (Lacunas e Decisões Pendentes), já que ela afeta diretamente `phase_completed` (evento) e a definição de `max_deliveries`.

---
