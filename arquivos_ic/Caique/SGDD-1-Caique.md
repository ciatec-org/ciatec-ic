**CIATec - GLIDE Framework**

# DOC 1 — GAME DESIGN DOCUMENT CIENTÍFICO
*Scientific Game Design Document (SGDD)*

Template v1.0  |  2026  |  CIATec
*Game Lifecycle for Inclusive Development and Evaluation*

**Versão:** v1.0 - formalização inicial do conceito
**Framework:** GLIDE (Game Lifecycle for Inclusive Development and Evaluation)
**Paradigma científico:** Spatial Navigation Task (Morris Water Maze Virtual)

## 1  IDENTIFICAÇÃO DO PROJETO

**Nome do jogo:** HelpIR (Helper Industrial Robot)/ RIA (Robô Insdustrial Auxiliar)
**Versão do documento:** v1.0 — formalização inicial do SGDD
**Projeto vinculado:** CIATec — Plataforma Aberta de Jogos Adaptativos para Educação Inclusiva
**Organização:** CIATec
**Posição no Triple Diamond:** *a confirmar junto à coordenação do GLIDE*. O jogo encontra-se atualmente em fase de co-design e definição conceitual, 
**Ciclos de PPI incorporados:** Relatório PPI TEA v1.0 — Fase 1 de co-design, abril a maio de 2026, incorporado de forma contextual e parcial
**Pesquisador responsável:** Carlos Monteiro
**Data de criação:** 24/09/2026
**Última atualização:** 27/09/2026

## 2  CONCEITO DO JOGO

### 2.1  Premissa

O HelpIR é um jogo no qual vocÊ controla um robô de uma fábrica e sua missão é entregar pacotes entre os setores dela. Para isso, o robô segue caminhos indicados por placas que ficam estacionadas entre as intersecções de corredores que, durante o jogo, podem estar quebradas, trocadas para manutenção ou até escondidas por algum elemento que o ambiente proporcionou (tipo sujeira na placa ou fumaça a tapando); além de que os corredores, com o tempo, pode ser bloqueados por algum evento que venha ocorrer (por exemplo, multidão de pessoas, reformas, etc.). [Pensar em um experiência singular]

### 2.2  Gênero e Plataforma
**Gênero:** Serious Game Terapêutico/Investigativo baseado no Paradigma de Navegação Espacial (Spatial Navigation Task). O *core* da jogabilidade operacionaliza diretamente um teste neuropsicológico validado de memória e reorientação espacial (similar ao *Morris Water Maze Virtual*).
**Plataforma:** desktop e mobile;
**Modo de jogo:** single player, sessão supervisionada, uso domiciliar
**Tecnologia de interação:** uso de periféricos (*mouse* e *teclado*) ou *touching*.

### 2.3  Público-Alvo

1) Usuários Finais (Jogadores)
  - **Público-Alvo Principal:** Crianças e indivíduos com **Transtorno do Espectro Autista (TEA)** enquadrados nos **Níveis de Suporte 1** (suporte pontual) e **Nível de Suporte 2** (suporte substancial). No ecossistema do jogo, esses perfis apresentam capacidades de comunicação funcional e autonomia digital em consolidação;
  - **Perfil de Ancoragem (Limite de Design):** Usuários de **Nível de Suporte 3** (suporte extenso), que servem de referência para delimitar as barreiras de abstração e as necessidades de adaptação severa (como a exigência de mediação física e ausência de interação totalmente autônoma);
  - **Faixa Etária e Contexto:** Foco no público infantil e infantojuvenil (ex.: 5 a 10 anos) em fase de desenvolvimento de habilidades de navegação espacial, flexibilidade cognitiva e autorregulação.
  

2) Profissionais Mediadores (Clínicos e Educadores)
   - **Terapeutas Ocupacionais, Psicólogos (ex.: análise do comportamento/ABA) e Psicopedagogos:** Utilizam o jogo como um **reforçador terapêutico** ao final das sessões ou como um instrumento de treino para atenção, foco e coordenação;
   - **Função no Sistema:** Aplicam o onboarding, supervisionam a execução da tarefa, interpretam os **relatórios de desempenho/telemetria** e ajustam as variáveis de progressão no backend.


3) Cuidadores (Pais e Familiares)
   - **Papel de Suporte:** Ajudam na preparação da infraestrutura (posicionamento de telas, espaço para movimentação), no gerenciamento dos limites de tempo para evitar fadiga e no controle do ambiente sensorial (como ajuste de volume e iluminação);
   - **Mediação Emocional:** Acompanham a resposta do jogador ao aumento de dificuldade e à frustração diante de bloqueios de rota ou mudanças no jogo.

## 3  OBJETIVO TERAPÊUTICO E EDUCACIONAL

### 3.1  Objetivo Terapêutico Principal (Primary Outcome & Target Mechanism)
O objetivo terapêutico principal desta intervenção gamificada é **mensurar, exercitar e estabilizar os construtos de aprendizagem espacial, memória topográfica e flexibilidade cognitiva** (recalculo de rota e reorientação) em crianças e indivíduos com Transtorno do Espectro Autista (TEA). 

A intervenção atua por meio do paradigma experimental da *Spatial Navigation Task*, operacionalizado na forma de tarefas de navegação e entrega em um ambiente virtual 3D. O **mecanismo de ação primário** fundamenta-se no processamento e na integração de pistas visuais de direção (placas coloridas) e na adaptação comportamental diante de perturbações ambientais dinâmicas (bloqueios de rotas preferenciais e ocultação de sinalizadores). 

O **desfecho primário** visa à quantificação do perfil de adaptação cognitiva e da eficácia decisional em navegação espacial, gerando um conjunto de dados padronizados para modelagem e desenvolvimento de futuras tecnologias assistivas e terapêuticas personalizadas para populações neurodivergentes.

### 3.2  Objetivos Secundários (Secondary Outcomes & Process Evaluation)

- **Avaliação de Processo e Telemetria de Biomarcadores Digitais:** Extrair e quantificar desfechos intermediários cinemáticos e decisionais contínuos durante o gameplay — especificamente o *tempo de hesitação e latência angular nas intersecções*, a *eficiência de rota* e a *suavidade da trajetória* — permitindo a caracterização contínua do perfil cognitivo do usuário sem interrupção da experiência lúdica.
- **Tolerabilidade Sensorial e Carga Atencional (Implementation Feasibility):** Garantir a aceitabilidade e o engajamento contínuo por meio do controle estrito da carga sensorial (interface minimalista, estilo gráfico *cartoon* de baixo ruído e contraste visual funcional), prevenindo a fadiga atencional e a sobrecarga sensorial em indivíduos com hipersensibilidade.
- **Viabilidade de Execução e Autonomia no Onboarding:** Validar a usabilidade e a autonomia de acesso ao protocolo por meio de um mecanismo de instrução exclusivamente visual e demonstrativo (instrução guiada concreta), eliminando barreiras de compreensão decorrentes da dependência de linguagem escrita ou falada complexa.
- **Modulação Comportamental e Habituação à Mudança (Behavioral Regulation):** Estimular a autorregulação e a tolerância à frustração por meio da exposição gradativa e segura a alterações imprevisíveis de rotina no ambiente virtual (vias bloqueadas e perda de pistas visuais), promovendo a habituação à incerteza.

### 3.3  Fora do Escopo (Intervention Boundaries & Exclusions)

- **Inexistência de Função Diagnóstica Isolada:** O software atua como instrumento complementar de treino, estimulação e coleta de biomarcadores digitais, não constituindo um teste isolado para diagnóstico clínico, neuropsicológico ou médico formal do TEA ou comorbidades.
- **Delimitação de Domínio Cognitivo:** A intervenção é estritamente delimitada às funções visuoespaciais, motoras e de navegação topográfica, estando fora do escopo o treino direcionado de comunicação social, linguagem verbal/expressiva ou competências fonológicas/semânticas.
- **Ausência de Transferência Ecológica Automática para AVDs:** O aprendizado e a resolução de rotas no ambiente fabril virtual não pressupõem ou garantem a transferência direta, autônoma e imediata para a navegação em cenários físicos reais do cotidiano (Atividades da Vida Diária - AVDs) sem acompanhamento e mediação terapêutica presencial.
- **Restrição de Execução Autônoma para Nível 3 de Suporte:** O jogo não é dimensionado para uso autônomo sem mediação física e verbal direta por profissionais ou cuidadores treinados em indivíduos com TEA Nível de Suporte 3 ou com barreiras severas de representação e abstração visuomotora.


## 3A  GUIDING PRINCIPLES

| GP | Evidência sintetizada do PPI | Objetivo de design | Funcionalidades previstas |
| --- | --- | --- | --- |
| GP-01 | Usuários apresentam barreiras de compreensão quando a interação depende de texto escrito | Permitir uso autônomo sem leitura | Tutorial visual *+ instrução em Libras ou equivalente* |
| GP-02 | Usuários precisam compreender imediatamente a causa dos erros para manter o engajamento | Tornar o estado do jogo imediatamente compreensível | Feedback visual explícito para acerto e falha |
| GP-03 | Usuários respondem melhor à progressão gradual do que a saltos bruscos de dificuldade | Manter engajamento ao longo das sessões | Progressão adaptativa por desempenho consistente, além de um progressão gradual durante as fases (iniciado após a primeira fase) |
| GP-04 | Sessões prolongadas ou sem controle de carga podem aumentar fadiga e reduzir adesão | Preservar segurança e tolerabilidade | Limite de duração e critérios de interrupção |
| GP-05 | Usuários apresentam distrações em relação à diversas cores (não por desconforto e sim por seletividade), atrapalhando no foco ao objetivo | Manter foco no objetivo | Sem abuso de cores, usar cores em pontos específicos, mas manter a estética lúdica |
| GP-06 | Usuários apresentaram preferências musicais (ou sem ela) | Causar o menor desconforto (chegar ao desconforto nulo) | Uso controlado do som (principalmente por ser um cenário industrial), permitir o controle de volume |
| GP-07 | Os usuários demonstraram mais uso de *tablet* ao contrário de outros dispositivos | Maior acessibilidade | Projetar projeto também para dispositivos móveis |
| GP-08 | Usuários apresentam dificuldades em adaptar-se a mudanças de situações | Não ter mudanças bruscas, mas manter a lógica central do jogo | Controle das mudanças do cenário. |


## 4  MECÂNICAS CORE  —  MDA: MECHANICS

### 4.1  Mecânica Principal
**Nome:** Navegação 3D e tomada de decisão em intersecções para entrega de pacotes sob perturbação ambiental

* **Descrição:**
  O jogador controla um robô caixeiro em um ambiente fabril 3D com o objetivo de transportar pacotes até os setores correspondentes. A orientação no espaço ocorre por meio de placas de sinalização coloridas posicionadas nas intersecções dos corredores. À medida que o jogo progride, o ambiente sofre perturbações dinâmicas que alteram a tomada de decisão, tais como a ocultação de placas (por fumaça ou sujeira) e o bloqueio imprevisto de corredores (por reformas ou obstáculos). 
  
  A câmera adota uma perspectiva de navegação egocêntrica com campo de visão limitado à frente do robô, exigindo que o jogador gire o robô para explorar o ambiente. 
  
  * **Controles no PC:** Teclas `W` / `Seta para Cima` (avançar), `S` / `Seta para Baixo` (recuar), `A` / `Seta para Esquerda` (girar à esquerda) e `D` / `Seta para Direita` (girar à direita).
  * **Controles em Dispositivos Móveis:** Botões virtuais direcionais na interface (*touchscreen*) que replicam exatamente os mesmos comandos de movimentação e rotação.

* **Justificativa Clínica:**
  Operacionaliza o paradigma *Spatial Navigation Task*. A navegação com perspectiva egocêntrica e pistas visuais de cores exercita a **aprendizagem espacial** e a **memória topográfica**. A introdução de bloqueios e ocultação de sinalizadores força o **recalculo de rota**, estimulando a **flexibilidade cognitiva**. O sistema utiliza essa mecânica para registrar biomarcadores digitais de hesitação decisional (latência nas intersecções) e eficiência de trajetória em tempo real.

* **Guiding Principle:**
  * **GP-01:** Garantir autonomia e clareza por meio de sinalização visual e demonstrativa, sem dependência de leitura.
  * **GP-03:** Manter a progressão gradual e adaptativa diante de perturbações ambientais.

* **Hipótese de Design (H-01):**
  Acreditamos que a orientação por placas exclusivamente coloridas e a limitação do campo de visão frontal, para crianças com TEA, resultará em maior autonomia de navegação e menor sobrecarga atencional, porque elimina a dependência da linguagem escrita e força a representação mental ativa do mapa da fábrica durante a exploração.

* **Origem PPI:**
  Evidências do relatório de PPI demonstram que indivíduos com TEA apresentam excelente resposta a estímulos visuais concretos e coloridos, mas enfrentam barreiras severas com instruções baseadas em texto. Além disso, o PPI evidenciou que alterações imprevistas na rotina exigem controle estrito de carga sensorial e progressão gradual para não disparar irritabilidade ou desengajamento.


##### 4.2  Sistema de Feedback

O sistema de feedback do **HelpIR** é multimodal (visual, auditivo, háptico, adaptativo e clínico) e foi projetado para comunicar de forma imediata o resultado das ações do jogador, garantindo alta clareza cognitiva e baixa carga sensorial, em conformidade com as diretrizes do framework GLIDE para indivíduos com Transtorno do Espectro Autista (TEA).

###### 1. Mapeamento dos Tipos de Feedback

**A. Feedback de Acerto (Conclusão de Entrega de Pacote)**
* **O que acontece:** Ao encostar e concluir a entrega no setor correto, o robô e o setor de destino emitem um brilho suave e direcionado (na cor correspondente ao setor), a caixa é transferida para o depósito e o robô realiza uma animação curta de confirmação.
* **Mídia e Funcionamento:**
  * **Visual:** Iluminação limpa e direcionada no robô e no setor.
  * **Auditivo:** Efeito sonoro (*SFX*) curto, harmonioso e em tom ascendente suave.
  * **Háptico (Dispositivos Móveis):** Vibração sutil e rápida (*pulse*) no dispositivo no momento exato do impacto com o setor.
* **O que comunica ao jogador:** Confirmação imediata de que o pacote foi entregue no setor correto, validando a rota percorrida e reforçando o acerto.

**B. Feedback de Tentativa Incorreta / Rota Indisponível (Erro)**
* **O que acontece:** Se o jogador tentar entregar em um setor incorreto ou se deparar com um corredor bloqueado/placa oculta, a caixa permanece retida com o robô e o veículo desacelera suavemente diante da barreira (fumaça ou cavalete de obras).
* **Mídia e Funcionamento:**
  * **Visual:** Indicador neutro de impedimento (barreira física visível ou retenção da caixa no robô).
  * **Auditivo:** Som sutil de obstrução física de baixa frequência ou ausência de áudio punitivo.
  * **Háptico (Dispositivos Móveis):** Vibração dupla curta e de baixa intensidade para indicar impedimento de passagem.
* **O que comunica ao jogador:** Que o setor selecionado não corresponde à cor do pacote ou que a via está indisponível, incentivando a reorientação visuoespacial e a consulta às placas sem gerar sensação de punição.

**C. Feedback de Pontuação e Reforço Positivo**
* **O que acontece:** A interface exibe a contagem de entregas acumuladas com sucesso, sem marcação de vidas regressivas ou perda de pontuação em caso de erro.
* **O que comunica ao jogador:** Progresso e conquista contínua, mantendo o enquadramento positivo da sessão de jogo.

**D. Feedback Adaptativo do Sistema (Ajuste Silencioso no Backend)**
* **O que acontece:** Quando a telemetria detecta hesitação prolongada nas intersecções, erros repetidos ou perda de rota, o backend reduz gradualmente e de forma silenciosa a fumaça das placas ou remove bloqueios de corredores.
* **O que comunica ao jogador:** Suporte adaptativo transparente, ajustando a carga cognitiva ao nível do jogador sem exibir telas punitivas de "Você Falhou" ou "Game Over".

**E. Feedback Clínico e Telemetria (Para Terapeutas e Cuidadores)**
* **O que acontece:** Ao final da sessão, a plataforma disponibiliza para o profissional/cuidador um resumo quantitativo contendo o tempo de decisão nas intersecções, a eficiência da rota e a suavidade da trajetória.
* **O que comunica ao clínico:** Evolução dos biomarcadores digitais de navegação espacial para acompanhamento terapêutico sem interromper a experiência lúdica.

**Justificativa clínica:**
O feedback imediato e transparente é um requisito terapêutico indispensável no paradigma *Spatial Navigation Task* para a consolidação da memória topográfica e do aprendizado espacial. No entanto, o erro comunicado de forma ostensiva (luzes vermelhas e alarmes de falha) ou o acerto efusivo em excesso (luzes piscantes e sons estridentes) rompem o engajamento de pessoas com TEA, disparando sobrecarga sensorial, irritabilidade e desistência. A adequação do feedback para uma resposta clara, de baixa carga sensorial e enquadramento não punitivo garante a manutenção da motivação e a validade da coleta de biomarcadores digitais.

**Guiding Principle:**
* **GP-02:** Tornar o estado do jogo e o resultado da ação imediatamente compreensíveis por meio de feedback visual, auditivo e háptico explícito, de baixa carga sensorial e sem caráter punitivo.

**Hipótese de design (H-02):**
Acreditamos que a utilização de um sistema de feedback imediato, porém calibrado e não punitivo (sem luzes piscantes de alta intensidade ou sons estridentes de erro), para crianças com TEA, resultará em maior sustentação do tempo de jogo e menor taxa de desistência por frustração, porque comunica o resultado da ação com clareza sem disparar hiper-reatividade sensorial ou respostas de ansiedade.

**Origem PPI:**
Evidências do relatório de síntese do PPI demonstram que participantes com TEA possuem alta sensibilidade a estímulos auditivos e visuais intensos, além de baixa tolerância a penalizações e telas de erro. O PPI apontou uma alta taxa de preferência por fundos e interfaces limpas, além da obrigatoriedade do controle individualizado de volume (com opção de desativar a música de fundo e manter apenas os SFX), respaldando a substituição de sinalizações efusivas ou punitivas por respostas moderadas e intuitivas.


### 4.3  Sistema de Progressão
*[Como o jogador avança. Critérios de progressão, regressão e interrupção. Parâmetros que mudam entre fases.]*
O jogo se inicia com um tutorial para ensinar a premissa básica dele. Com o passar das fases, e dependendo dos dados obtidos durante a *gameplay* (como exitação nos cruzamentos, dificuldades de lembrar a rota e/ou recalcular outra rota), aparece novas desafios baseado em omitir as placas e/ou bloquear caminhos.
**Justificativa clínica:**
Progressão baseada em desempenho consistente, não em acerto bruto. Calibração terapêutica requer controle de intensidade.
**Guiding Principle:**
* **GP-03**: O jogador avança de fase quando demonstra consistência nas entregas em tempo hábil, e não por acertos brutos isolados;
* **GP-04**:Se a telemetria detectar hesitação prolongada nas intersecções, erros recorrentes ou sinais de desorientação, o servidor reduz silenciosamente o nível de perturbação (diminuindo a fumaça ou removendo o bloqueio de uma via), sem exibir telas de "Game Over" ou perda de pontos.

**Hipótese de design:**
Esse nível de progressão não será masçante, nem será desgatante para os jogadores. Isto será alinhado com o objetivo de não causar desconfortou ou desistência durante a experiência.

### 4.4  Onboarding

##### 4.4  Onboarding

* **Descrição e Funcionamento:**
  O aprendizado das mecânicas do **HelpIR** ocorre por meio da **Fase 0 (Tutorial Prático e Interativo)**, um ambiente fabril simplificado e sem pressão temporal, contagem de vidas ou pontuação punitiva. O tutorial demonstra situações isoladas de navegação e entrega de pacotes.
  
  A instrução é **exclusivamente visual e demonstrativa**: em vez de textos explicativos, o jogo utiliza animações curtas em loop demonstrando o robô se movendo, além de ícones concretos e placas coloridas indicando os setores de destino. O tutorial permanece acessível no menu principal a qualquer momento para reconsulta ou reaquecimento.

* **Justificativa clínica:**
  Indivíduos com Transtorno do Espectro Autista (TEA) frequentemente apresentam barreiras de processamento de linguagem escrita e abstração verbal. No paradigma *Spatial Navigation Task*, o onboarding visual e prático garante que a criança compreenda a regra de associação entre as placas de cores e os setores de destino antes da introdução de perturbações ambientais (fumaça e bloqueios), assegurando que o desempenho do jogador reflita sua capacidade visuoespacial e não uma falha de compreensão das instruções.

* **Guiding Principle:**
  * **GP-01:** Garantir autonomia de uso e clareza de instrução por meio de sinalização visual e demonstrativa (ícones, cores e animações guiadas), sem dependência de leitura ou linguagem escrita complexa.

* **Hipótese de design (H-03):**
  Acreditamos que um onboarding exclusivamente visual e prático (Fase 0), baseado em demonstrações animadas, ícones concretos e associação por cores sem presença de texto escrito, para crianças e indivíduos com TEA, resultará em maior autonomia de uso e rápida compreensão das mecânicas de entrega, porque elimina a barreira do processamento de linguagem verbal e aproveita a alta receptividade da população a estímulos visuais diretos.

* **Origem PPI:**
  Evidências do relatório de síntese do PPI demonstram que participantes com TEA (especialmente dos Níveis de Suporte 2 e 3) apresentam severas barreiras de compreensão diante de tutoriais extensos ou baseados em texto, mas aprendem de forma intuitiva quando expostos a animações concretas e demonstrações práticas. O PPI fundamentou o GP-01, estabelecendo que a instrução visual é um requisito de mecânica e de usabilidade obrigatório, e não um recurso opcional de acessibilidade.


## 5  DINÂMICAS  —  MDA: DYNAMICS

### 5.1  Arco de uma Sessão Típica

No começo de cada fase, o jogador precisa coletar as caixas que vai precisar entregar em cada um dos setores. Após isso, o robô precisa percorrer o caminho seguindo as placas. No final, ele entrega o pacote para o setor. Esse ciclo se repete algumas vezes, no qual fases futuras são adicionados novos obstáculos, como omissão de placas e bloqueio de caminhos.

*Duração esperada:* entre 10 minutos à 20 minutos por fase.

### 5.2  Progressão Longitudinal

Com o passar do tempo, as fases vão ganhando camadas de complexidade. A Fase 0 é um tutorial que vai apresentar isoladamente cada um dos obstáculos.

Após ela, as fases aumentam suas dificuldade progressivamente, como a adição de novos setores, omissão das placas e bloqueio de caminhos. Entretanto, durante a fase, é possível ajustar a dificuldade para gerar o menor desconforto.

Em cada fase, ela começa sem nenhuma anormalidade, posteriormente é adicionado os obstáculos.

### 5.3  Calibração de Intensidade Terapêutica

Por conta do cenário se passar em uma fábrica, podemos implementar as seguintes variável de controle:
* **Controle de áudio**;
* **Número máximo de interesecções** (será usado também para definir o tamanho da fábrica);
* **Número máximo de placas**;
* **Número de setores**;
* **Número de entregas máximo**.
  

## 6  EXPERIÊNCIA PRETENDIDA  —  PLAYER EXPERIENCE (MDA: AESTHETICS)

O jogo se enquadrariam em três MDA's: *Sensation*, *Challenge* e *Submission*. Abaixo é detalhado o porquê:
* **Sensation**: o jogo utiliza muito de elementos visuais para guiar o usuário pela fábrica, sendo ajustado com o tempo para adequar para o usuário;
* **Challenge**: gradualmente o jogo incrementa a dificuldade em cada uma das fases, equilibrando em relação às adservidades registradas pelo usuário;
* **Submission**: por conta de sua identidade visual girar em torno do lúdico e das mecânicas dele, o jogo gera uma experiência de passatempo, visando o estresse nulo.

## 7  ELEMENTAL TETRAD

### 7.1  Mechanics  —  Regras e Sistemas
O jogador controla o robô através do teclado: `W/Seta para Cima` e `S/Seta para Baixo` para avançar e recuar, respectivamente; `A/Seta para Esquerda` e `D/Seta para Direita` para movimentar a câmera. Para dispositivos móveis, deve-se ser controlado por icones que represetam as setas do teclado. Esta mecânica é usada para movimentar o robô pela fábrica e permitir que ele entregue as encomendas.

O jogo é divido em fases, no qual é Fase 0 é o tutorial (que pode ser sempre acessável) que demonstra todas os obstáculos do jogo de maneira individual. Logo depois disso, as fases avançam a dificuldade de maneira progressiva aumentado os setores, as placas omitidas e/ou corredores bloqueados. Em cada fase, o robô coleta a encomenda e faz seu caminho baseado nas placas até o setor para entregar. Isso acontece até a fase se finalizar.
**Restrições da população:**
Ausência de feedbacks sonoros punitivos; duração máxima de 30 minutos de jogo.
### 7.2  Story  —  Narrativa e Contexto
*[Contexto narrativo do jogo, se existir. Pode ser mínima em jogos terapêuticos abstratos.]*
Você é um robô que foi criado para evitar que mais acidentes de trabalhos ocorram na hora de entregar o pacote em outros setores. Com suas rodas rápidas e alta tecnologia, você tem essa missão tão honrosa.
**Restrições da população:**
Não depende de elementos textuais.

### 7.3  Aesthetics  —  Visual, Som e Sensação
Um *design* mais cartunesco e com cores mais pastéis, formas mais redondas para não demonstrar perigo. Em questão do campo visual, evitar que tenha muitas máquinas exposta, serem separadas por cabines. 

Na questão de áudios, ponderar o uso de áudios fabris.
**Restrições da população:**
Controle do áudio; sem abuso de cores.

### 7.4  Technology  —  Plataforma e Implementação
O jogo será portado para computadores pessoais (*Personal Computer* - PC) e em dispositivos móveis. Para seu funcionamento, deverá ter teclado e mouse na questão do computador, e *touchscreen* na questão do dispositivos móveis. Nescessitará da conexão à *Internet*.

A construção será feito na plataforma Unity para computadores, e Dart/Flutter para dispositivos móveis.
**Restrições da população:**
Funcionar em hardware doméstico de baixo custo.

#### 8  MAPEAMENTO LM-GM

| Objetivo clínico / educacional | Mecânica de jogo | Como operacionaliza | GP |
| --- | --- | --- | --- |
| **Exercitar a aprendizagem espacial e a memória topográfica** | Navegação 3D egocêntrica guiada por placas de sinalização coloridas | O jogador percorre os corredores da fábrica identificando e associando a cor das placas aos setores de entrega correspondentes, construindo a representação mental do mapa do ambiente. | **GP-01 / GP-03** |
| **Estimular a flexibilidade cognitiva e a reorientação por recalculo de rota** | Perturbação ambiental dinâmica (ocultação de placas e bloqueio de vias) | O sistema introduz fumaça/sujeira sobre os sinalizadores e bloqueia imprevistamente corredores habituais, forçando a descontinuidade da rotina e a busca de rotas alternativas. | **GP-03** |
| **Manter o engajamento terapêutico e promover a autorregulação** | Progressão adaptativa por desempenho com suporte silencioso | O jogo ajusta a dificuldade conforme a consistência de acertos e reduz silenciosamente os obstáculos em caso de hesitação prolongada, mantendo o enquadramento positivo sem telas de erro. | **GP-03 / GP-02** |
| **Mensurar biomarcadores digitais de navegação espacial de forma não invasiva** | Telemetria silenciosa em tempo real (*Spatial Navigation Task*) | O motor de jogo registra continuamente a hesitação angular e a latência nas intersecções, a eficiência do percurso e a suavidade da trajetória durante a execução normal das entregas. | **GP-02 / GP-04** |
| **Assegurar autonomia de uso para indivíduos com barreiras de linguagem escrita** | Onboarding prático e exclusivamente visual (Fase 0 - Tutorial) | Apresenta animações curtas em *loop*, ícones concretos e prática guiada de movimentação e entrega, eliminando a dependência de texto escrito para compreensão das regras | **GP-01** |
| **Prevenir sobrecarga sensorial e hiper-reatividade** | Sistema de feedback calibrado de baixa carga sensorial | Utiliza iluminação limpa e direcionada nos alvos, efeitos sonoros curtos e suaves, ausência de alarmes punitivos, controle de volume e limite de 30 segundos por fase. | **GP-02 / GP-04 / GP-06** |


## 9  PERSONAS E REQUISITOS DERIVADOS
#### 9  PERSONAS E REQUISITOS DERIVADOS

##### 9.1  Persona 1 — Criança com TEA Nível de Suporte 1 (Autonomia e Flexibilidade)

* **Identificação funcional:** 
  Usuário infantojuvenil (5 a 10 anos) com Transtorno do Espectro Autista (TEA) Nível de Suporte 1 (suporte pontual). Apresenta boa autonomia no uso de dispositivos digitais (tablets e computadores), comunicação verbal funcional e atenção direcionada. Pode apresentar comorbidades neurocomportamentais como TDAH e Transtorno Opositivo Desafiador (TOD), que afetam a regulação emocional e a tolerância à frustração diante de falhas.

* **Ciclo PPI de origem:** 
  `PPI-ATGCP-TEA` (composto a partir dos dados dos participantes U1-S1, U2-S1 e U3-S1).

* **Contexto de uso:** 
  Uso autônomo em ambiente domiciliar ou clínico, em partidas de curta duração sob supervisão direta ou indireta de adultos.

* **Requisitos derivados:**
  * **REQ-P1-01 (Onboarding Prático e Visual):** Implementar a Fase 0 (Tutorial) exclusivamente com demonstração animada em *loop* e execução prática das entregas, eliminando a dependência de linguagem escrita para instrução inicial (GP-01).
  * **REQ-P1-02 (Regressão Silenciosa de Dificuldade):** Ativar suporte adaptativo no backend para redução silenciosa de perturbações (fumaça sobre placas ou bloqueio de vias) quando a telemetria indicar hesitação excessiva, sem exibir telas de "Game Over", avisos de erro ostensivos ou perda de pontos, prevenindo reações de irritabilidade em usuários com comorbidade TDAH/TOD (GP-02, GP-03).
  * **REQ-P1-03 (Interface Sensorial Limpa):** Manter fundo de tela neutro/branco na interface e no ambiente 3D estilizado (*cartoon*), sem elementos decorativos piscantes ou animações de fundo para evitar competição atencional e sobrecarga visual (GP-02).
  * **REQ-P1-04 (Mapeamento Flexível de Controles):** Oferecer suporte nativo tanto para navegação por teclado (`W/A/S/D` e Setas direcionais) no PC quanto para botões direcionais visíveis e espaçados na tela *touchscreen* para tablets (GP-01).

* **Guiding Principles relacionados:** 
  GP-01, GP-02, GP-03, GP-04.

* **Impacto nas decisões:** 
  Seções 4.1 (Mecânica Principal), 4.2 (Feedback), 4.3 (Progressão), 4.4 (Onboarding), 10 (Interface e Acessibilidade) e 11 (Parâmetros de Fase).

* **Status de validação:** 
  Válida (sustentada por dados primários e diretos de sessões e entrevistas do PPI).

##### 9.2  Persona 2 — Criança com TEA Nível de Suporte 2 (Suporte Substancial e Sensibilidade a Mudanças)

* **Identificação funcional:** 
  Usuário infantil (5 a 10 anos) com TEA Nível de Suporte 2 (suporte substancial). Apresenta comunicação verbal restrita ou em consolidação, presença de hiperfoco em temas ou cores específicas, elevada inflexibilidade comportamental diante de alterações na rotina e maior susceptibilidade à hiper-reatividade sensorial (auditiva e visual).

* **Ciclo PPI de origem:** 
  `PPI-ATGCP-TEA` (composto a partir de dados do participante U4-S2, com dados complementares do cuidador C1 e da profissional PC-B).

* **Contexto de uso:** 
  Ambiente clínico ou domiciliar sob mediação e acompanhamento presencial constante de um cuidador ou profissional de saúde.

* **Requisitos derivados:**
  * **REQ-P2-01 (Parametrização e Restrição de Cores):** Permitir a personalização e a restrição da paleta de cores das placas de sinalização no menu de configurações para evitar a recusa de interação por hiperfoco ou aversão a cores específicas (GP-05).
  * **REQ-P2-02 (Acomodação Auditiva do Jogo):** Oferecer controle independente de volume com a opção de desativar totalmente a música de fundo (*BGM*) mantendo apenas os efeitos sonoros de ação (*SFX*), prevenindo estresse e sobrecarga auditiva (GP-06).
  * **REQ-P2-03 (Enquadramento Positivo e Duração Curta):** Limitar a duração padrão de tentativa a 30 segundos por fase e utilizar enquadramento exclusivamente acumulativo de pontos, sem contagem regressiva de vidas ou cronômetros punitivos visíveis (GP-02, GP-04).
  * **REQ-P2-04 (Progressão Gradual de Perturbações):** Introduzir os desafios de fumaça (Fase 3) e bloqueio de caminhos (Fase 4) de forma estritamente sequencial e parametrizável, ativando perturbações combinadas (Fase 5) apenas após consolidação demonstrada por consistência nas fases anteriores (GP-03).

* **Guiding Principles relacionados:** 
  GP-01, GP-02, GP-03, GP-04, GP-05, GP-06.

* **Impacto nas decisões:** 
  Seções 4.1 (Mecânica Core), 4.2 (Feedback), 4.3 (Progressão), 10 (Interface e Acessibilidade) e 11 (Parâmetros de Fase).

* **Status de validação:** 
  Válida com ressalva (dados baseados em sessão observada e relatos de cuidador e profissional; requer validação no protocolo experimental do Doc 3).

##### 9.3  Persona 3 — Profissional Mediador / Terapeuta (Acompanhamento e Telemetria)

* **Identificação funcional:** 
  Profissional clínico (Psicólogo/ABA, Terapeuta Ocupacional, Psicopedagogo) ou educador especializado responsável pelo acompanhamento terapêutico, estimulação cognitiva visuoespacial e avaliação do desenvolvimento.

* **Ciclo PPI de origem:** 
  `PPI-ATGCP-TEA` (composto a partir das entrevistas estruturadas com as profissionais PC-A e PC-B).

* **Contexto de uso:** 
  Consultórios clínicos, centros de reabilitação ou instituições especializadas durante ou ao final de sessões estruturadas de intervenção.

* **Requisitos derivados:**
  * **REQ-P3-01 (Emissão de Relatório de Biomarcadores):** Gerar relatórios quantitativos automáticos pós-sessão contendo os dados de telemetria da *Spatial Navigation Task*: tempo de hesitação decisional nas intersecções, eficiência de rota e suavidade da trajetória.
  * **REQ-P3-02 (Painel de Calibração no Backend):** Disponibilizar interface no servidor `research.ciatec.org` para ajuste personalizado de parâmetros da fase (velocidade do robô, tempo de visibilidade das placas, densidade da fumaça e probabilidade de bloqueios de vias).
  * **REQ-P3-03 (Mecanismo de Interrupção e Pausa Limpa):** Oferecer atalho de pausa imediata e interrupção de sessão que possa ser acionado pelo terapeuta diante de sinais evidentes de sobrecarga, agitação motora ou desengajamento da criança (GP-04).

* **Guiding Principles relacionados:** 
  GP-02, GP-04.

* **Impacto nas decisões:** 
  Seções 3.1 (Objetivo Terapêutico), 3.2 (Objetivos Secundários), 5.3 (Calibração Terapêutica), 11 (Parâmetros de Fase) e 12 (Requisitos Técnicos Consolidados).

* **Status de validação:** 
  Válida (derivada de entrevistas com profissionais especialistas em intervenção no TEA).


## 10  INTERFACE E ACESSIBILIDADE
#### 10  INTERFACE E ACESSIBILIDADE

##### 10.1  Princípios de Interface

* **Campo Visual Limpo e Mínimo de Distratores:** Interface minimalista em estilo gráfico *cartoon* simplificado, com fundo neutro/branco por padrão no ambiente 3D da fábrica (baseado na preferência convergente de 100% dos participantes de Suporte 1 no PPI), eliminando poluição visual, iluminação piscante ou animações decorativas de fundo que geram dispersão atencional e hiperfoco indesejado (GP-02).
* **Independência de Linguagem Escrita (Onboarding Visual):** Eliminação de textos longos e instruções verbais complexas. A interface prioriza o uso de cores contrastantes, ícones concretos e animações demonstrativas em *loop* (GP-01).
* **Enquadramento Positivo e Ausência de Punição:** Exibição contínua do progresso acumulado (número de entregas realizadas com sucesso), sem contagens regressivas de vidas, cronômetros punitivos visíveis ou telas de "Game Over" (GP-02).
* **Prevenção de Sobrecarga Sensorial:** Controle estrito das saídas auditivas e visuais, garantindo que o jogador não seja submetido a estímulos abruptos, luzes estroboscópicas ou sons de alta frequência (GP-02, GP-06).

##### 10.2  Requisitos de Acessibilidade por Domínio

* **Visual:**
  * **Fundo e Contraste:** Fundo de tela neutro/branco por padrão e alto contraste visual entre as placas de sinalização, o robô caixeiro e os setores de entrega.
  * **Parametrização de Paletas de Cores:** Menu de configurações que permite alterar ou restringir a paleta de cores das placas e setores para evitar a recusa de interação decorrente de hiperfoco ou aversão a cores específicas (GP-05).
  * **Redução de Carga Estética:** Ausência de partículas dinâmicas, flashes visuais piscantes ou elementos decorativos em movimento ao fundo da fábrica.

* **Auditivo:**
  * **Equivalência Visual Total:** Todos os eventos e comandos sonoros do jogo possuem equivalentes visuais diretos (a ausência total de áudio não compromete a jogabilidade).
  * **Controle Independente de Áudio:** Opção no menu para ajuste independente do volume da música de fundo (*BGM*) e dos efeitos sonoros de ação (*SFX*), permitindo desligar a *BGM* e manter apenas os *SFX* (GP-06).
  * **Ausência de Sons Punitivos:** Eliminação de alarmes de erro, buzinas ou timbres estridentes em caso de falhas ou bloqueios de rota.

* **Motor:**
  * **Mapeamento Duplo de Controles:** Suporte nativo a comandos via teclado no PC (`W/A/S/D` e Setas direcionais) e a botões direcionais virtuais visíveis na tela em dispositivos móveis (*touchscreen*).
  * **Área de Toque Expandida:** Botões virtuais na tela *touchscreen* com dimensões amplas e espaçamento adequado para acomodar variações na precisão motora e evitar toques acidentais.
  * **Sem Exigência de Combinações Simultâneas:** Todas as ações de movimentação do robô são executadas por comandos únicos e sequenciais (sem exigir o pressionamento de duas teclas ao mesmo tempo).

* **Linguístico:**
  * **Tutorial Exclusivamente Visual:** Onboarding prático na Fase 0 com animações demonstrativas do robô e sinalizações coloridas, sem necessidade de leitura (GP-01).
  * **Simbologia Concreta:** Substituição de rótulos de texto por ícones universais e visualmente intuitivos para representar setores, pacotes, menus e configurações.

* **Cultural e Contextual:**
  * **Ambientação Lúdica e Amigável:** Estética de fábrica estilizada (*cartoon*) com visual simpático do robô caixeiro, promovendo engajamento seguro sem ambientações sombrias ou ameaçadoras.


##### 10.3  Telas e Fluxo de Navegação

1. **Tela de Menu Principal:**
   * Layout minimalista com poucas opções visíveis e ícones grandes: **[Jogar]**, **[Tutorial]** e **[Configurações]**.
   * Ausência de anúncios, menus aninhados complexos ou textos explicativos.

2. **Tela de Gameplay (Fábrica 3D):**
   * Perspectiva de navegação egocêntrica / 3ª pessoa alinhada à frente do robô.
   * **HUD Minimalista:**
     * Canto superior: Ícone com a cor e o símbolo do pacote atual a ser entregue.
     * Canto oposto: Contador simples de entregas acumuladas com sucesso.
     * Canto superior discreto: Botão de Pausa.
     * *(Em dispositivos móveis)*: Setas direcionais virtuais fixadas nas extremidades inferiores da tela com ampla área de toque.

3. **Menu de Pausa:**
   * Sobreposição limpa e semitransparente que paralisa o jogo instantaneamente.
   * Opções icônicas: **[Continuar]**, **[Reiniciar Fase]**, **[Configurações Sensoriais]** e **[Sair]**.

4. **Tela de Conclusão de Fase:**
   * Apresentação positiva curta do número de entregas realizadas.
   * Botão direto de avanço para a próxima fase, garantindo fluidez no ritmo de jogo sem interrupções desnecessárias.



## 11  PARÂMETROS DE FASE E PROGRESSÃO

### 11.1  Variáveis de Fase

| Variável | Descrição e faixa de valores |
| --- | --- |
| **Número de intersecções** | **faixa:** 6 a 24 intersecções no mapa da fábrica; **impacto:** define a complexidade da malha viária 3D e a quantidade de pontos de tomada de decisão/orientação nas bifurcações (onde se posicionam os postes com placas de sinalização). |
| **Número de placas por intersecção** | **faixa:** 1 a 4 placas por poste; **impacto:** quantidade de pistas visuais de direção e opções de rota disponíveis para orientar o percurso até os setores. |
| **Controle de áudio (Volume BGM e SFX)** | **faixa:** 0 dB (mudo) a 70 dB (ou 0% a 100%); **impacto:** acomodação e regulação sensorial para prevenção de sobrecarga auditiva em indivíduos com hipersensibilidade (permite desligar a música de fundo e manter apenas os efeitos sonoros de ação) [GP-06]. |
| **Número de setores ativos** | **faixa:** 3 a 6 setores (ex.: 3 setores na Fase 1, expandindo até 5/6 nas fases avançadas); **impacto:** expansão da carga de memória topográfica/espacial e da quantidade de alvos de entrega na fábrica. |
| **Número de entregas por fase/sessão*** | **faixa:** 10 a 30 entregas (*parâmetro modificável no backend); **impacto:** determina a extensão da tarefa, a sustentação atencional e a taxa de amostragem de biomarcadores digitais por sessão. |
| **Opacidade / Densidade da fumaça** | **faixa:** 0% (placa totalmente visível) a 100% (placa oculta); **impacto:** nível de perturbação visual e demanda por memória espacial prévia/recuperação de pista (Fases 3 e 5). |
| **Quantidade de vias bloqueadas** | **faixa:** 0 a 3 corredores bloqueados por fase; **impacto:** nível de perturbação de rota e exigência de flexibilidade cognitiva para recalculo e busca de caminhos alternativos (Fases 4 e 5). |
| **Duração da fase / tentativa** | **faixa:** 30s a 60s (padrão: 30 segundos); **impacto:** regulação da carga atencional, limite de tolerabilidade e prevenção de fadiga sensorial/motora [GP-04]. |

*\*Observação: O número de entregas é um parâmetro dinâmico gerenciado pelo servidor `research.ciatec.org` e pode ser ajustado conforme a evolução do protocolo clínico.*


### 11.2  Critérios de Progressão, Regressão e Interrupção

| Evento | Critério |
| --- | --- |
| Avanço de fase | consistência de desempenho acima de 70% em 10 sessões consecutivas |
| Regressão de fase | queda de desempenho acima de 15%, aumento de tempo de resposta, sinais de frustração |
| Interrupção de sessão | fadiga, desconforto visual, confusão sobre a tarefa, eventos adversos |
| Interrupção do protocolo | aṕos 20 minutos de jogatina para evitar fadiga |

### 11.3  Faixas de Fase por Perfil

#### A. Tabela Resumo de Faixas por Perfil

| Perfil / Persona | Fase de Entrada | Faixa de Fases Recomendada | Nível de Perturbação Permitido | Tempo por Fase | Nível de Mediação |
| --- | --- | --- | --- | --- | --- |
| **Persona 1 (TEA S1)** | Fase 0 (Rápida) | **Fases 1 a 5** (Ciclo Completo) | Fumaça (0 a 100%) + Bloqueios (0 a 3 vias) | 30s a 45s | Uso autônomo / Supervisão indireta |
| **Persona 2 (TEA S2)** | Fase 0 (Guiada) | **Fases 1 a 3** (Avanço condicionado) | Fumaça leve (máx. 50%) / Sem bloqueios iniciais | 30s | Mediação presencial constante |
| **Perfil S3 (Ancoragem)** | Fase 0 (Estendida) | **Fases 0 a 1** (Simplificada) | Sem perturbação (0% fumaça / 0 bloqueios) | Sem limite rígido / 30s | Mediação clínica física e verbal intensa |

#### B. Detalhamento e Regras de Calibração por Perfil

##### 1. Persona 1 — Criança com TEA Nível de Suporte 1 (Perfil de Alta Autonomia)
* **Porta de Entrada:** **Fase 0 (Tutorial Prático)**. O usuário passa rapidamente pelo onboarding para validação de comandos (PC ou Mobile) e compreensão do objetivo de entrega.
* **Faixa de Progressão:** **Fases 1 a 5** (Acesso ao ciclo funcional completo).
* **Parâmetros Iniciais:**
  * **Setores Ativos:** Inicia com 3 setores (Fase 1) e expande até 5 setores (Fase 2).
  * **Perturbações Ambientais:** Progresso livre até a introdução de placas ocultas por fumaça (Fase 3), bloqueios de corredores (Fase 4) e perturbações combinadas (Fase 5).
  * **Suporte Adaptativo:** Caso o backend detecte hesitação excessiva ou recusa de rota em fases com bloqueio (comum em usuários com comorbidades TDAH/TOD), o sistema reduz a densidade da fumaça ou libera 1 via bloqueada silenciosamente (GP-03).
* **Objetivo Terapêutico na Faixa:** Maximizar o desafio de flexibilidade cognitiva e recalculo de rota, extraindo biomarcadores de eficiência e aceleração de trajetória.

##### 2. Persona 2 — Criança com TEA Nível de Suporte 2 (Perfil com Inflexibilidade e Sensibilidade)
* **Porta de Entrada:** **Fase 0 (Tutorial Demonstrativo)**. Requer demonstração guiada pelo mediador para assimilar a relação entre a cor da placa e o setor.
* **Faixa de Progressão:** **Fases 1 a 3** (Progressão conservadora).
* **Parâmetros Iniciais:**
  * **Setores Ativos:** Fixado em 3 setores ativos (Fase 1) por no mínimo 3 sessões consecutivas antes de expandir para 5 setores (Fase 2).
  * **Perturbações Ambientais:** Fumaça limitada a no máximo 50% de opacidade (Fase 3). **A Fase 4 (Bloqueio de Vias) é desativada por padrão no protocolo inicial**, pois o bloqueio abrupto de rotas habituais dispara reações de frustração e recusa comportamental.
  * **Configuração Sensorial Obrigatória:** Paleta de cores pré-ajustada no menu (sem cores aversivas) e música de fundo desligada (*SFX* ativos) [GP-05, GP-06].
* **Regra de Transição para Fases Avançadas:** A transição para as Fases 4 ou 5 somente é liberada se o participante demonstrar estabilidade emocional e consistência de acerto acima de 85% em 5 sessões consecutivas na Fase 3.

##### 3. Perfil de Ancoragem — TEA Nível de Suporte 3 (Adaptação Severa / Treino Pré-Jogo)
* **Porta de Entrada:** **Fase 0 Estendida (Protocolo de Treino Pré-Jogo)**.
* **Faixa de Progressão:** **Fases 0 e 1 Simplificada** (Foco na assimilação da causa e efeito).
* **Parâmetros Iniciais:**
  * **Abstração e Controles:** Devido à dificuldade de abstração visuomotora (tentativa de toque direto na tela), a interação ocorre com mediação física (movimento guiado mão sobre mão) ou via bastões concretos para sinalização de direção.
  * **Setores e Visibilidade:** Apenas 3 setores visíveis com cores primárias contrastantes. Placas 100% visíveis, sem fumaça e sem bloqueios de corredores.
* **Critério de Permanência:** O objetivo nesta faixa não é a medição de flexibilidade cognitiva, mas a inclusão e a promoção da causa e efeito (entregar o pacote produz um brilho suave e gratificante).


#### 12  REQUISITOS TÉCNICOS CONSOLIDADOS

| Domínio | Requisito | Prioridade | Origem |
| --- | --- | --- | --- |
| **Funcional / Core** | Navegação 3D egocêntrica com orientação por placas de cores em intersecções | **Alta** | Paradigma / GP-01 |
| **Funcional / Core** | Mecânica de entrega de pacotes nos setores fabris correspondentes à cor | **Alta** | Paradigma / GP-01 |
| **Funcional / Core** | Perturbação ambiental dinâmica (ocultação de placas por fumaça e bloqueio de corredores) | **Alta** | Paradigma / GP-03 |
| **Sensorial / Visual** | Fundo de tela 3D limpo/neutro (estilo cartoon sem distratores ou partículas piscantes) | **Alta** | PPI-TEA / GP-02 |
| **Sensorial / Visual** | Menu para seleção e restrição de paletas de cores (prevenção de aversão/hiperfoco por cores) | **Alta** | PPI-TEA / GP-05 |
| **Sensorial / Visual** | Feedback de acerto suave e focado (brilho direcionado no setor sem flashes piscantes) | **Alta** | PPI-TEA / GP-02 |
| **Sensorial / Auditivo** | Controle de volume independente para música de fundo (BGM) e efeitos sonoros (SFX) | **Alta** | PPI-TEA / GP-06 |
| **Sensorial / Auditivo** | Opção de desativação total da BGM mantendo apenas SFX de ação ativos | **Alta** | PPI-TEA / GP-06 |
| **Sensorial / Auditivo** | Eliminação total de alarmes de erro, buzinas e timbres estridentes em falhas | **Alta** | PPI-TEA / GP-02 |
| **Acessibilidade / UI** | Onboarding prático na Fase 0 exclusivamente por animação e demonstração visual (sem texto) | **Alta** | PPI-TEA / GP-01 |
| **Acessibilidade / UI** | Interface minimalista (HUD) com enquadramento exclusivamente positivo de pontos acumulados | **Alta** | PPI-TEA / GP-02 |
| **Acessibilidade / UI** | Suporte duplo a controles: Teclado (PC) e botões virtuais touchscreen amplos (Tablets) | **Alta** | PPI-TEA / GP-07 |
| **Progressão & Backend** | Recepção de parâmetros de fase (velocidade, fumaça, bloqueios) via servidor `research.ciatec.org` | **Alta** | Arquitetura CIATec / GP-03 |
| **Progressão & Backend** | Regressão silenciosa de dificuldade (redução de perturbação) sem telas de "Game Over" | **Alta** | PPI-TEA / GP-03 |
| **Telemetria / Dados** | Registro contínuo e silencioso de biomarcadores (hesitação, eficiência e suavidade de rota) | **Alta** | Paradigma / GP-02 |
| **Telemetria / Dados** | Geração automática de relatório quantitativo de desempenho pós-sessão para o terapeuta | **Média** | PPI-TEA / GP-02 |
| **Segurança & Clínica** | Tempo máximo de cada fase entre 20 a 30 minutos (programável) | **Alta** | Protocolo / GP-04 |
| **Segurança & Clínica** | Atalho de pausa e botão de interrupção de emergência de sessão pelo terapeuta | **Alta** | Protocolo / GP-04 |
| **Segurança & Clínica** | Definição e aplicação de critérios explícitos para interrupção de protocolo longitudinal | **Alta** | Protocolo / GP-04 |


## 13  LACUNAS E DECISÕES PENDENTES

| Lacuna / Decisão pendente | Impacto | Ação necessária | Responsável |
| --- | --- | --- | --- |
| **Amostragem reduzida para o Nível de Suporte 2 no ciclo de PPI** | **CRÍTICA:** Os requisitos para o Suporte 2 baseiam-se em apenas 1 participante e dados indiretos de cuidador/profissional, mantendo as Personas com ressalva clínica. | Realizar ciclo complementar de PPI com foco em participantes com TEA Nível de Suporte 2. | Pesquisador Responsável / Equipe de PPI |
| **Confirmação da posição formal no Triple Diamond do GLIDE** | Indefinição sobre o marco de maturidade formal da transição do 1º Diamante (Co-design/Conceito) para o 2º Diamante (Backlog e Desenvolvimento). | Alinhar o status formal de transição junto à coordenação do GLIDE. | Pesquisador Responsável |
| **Definição da arquitetura de exportação para Dispositivos Móveis (Unity vs. Flutter)** | **CRÍTICA:** O rascunho cita Unity para PC e Flutter para mobile; é preciso confirmar se haverá build nativa Unity para tablets ou cliente em Flutter. | Definir a arquitetura multiplataforma única antes da criação das tarefas do Backlog (Doc 2). | Equipe de Desenvolvimento |
| **Calibração dos limiares de latência para acionamento da Regressão Silenciosa** | Risco de acionamento inadequado (precoce ou tardio) do suporte adaptativo (redução de fumaça/bloqueios) por falta de limiares numéricos testados. | Conduzir estudo piloto técnico de calibração empírica dos tempos de hesitação nas intersecções. | Equipe de Ciência de Dados / Clínico |
| **Resiliência e sincronização de telemetria offline-first no cliente** | **CRÍTICA:** Oscilações de conexão no uso domiciliar podem ocasionar perda de pacotes de biomarcadores enviados ao servidor `research.ciatec.org`. | Implementar sistema de *buffer* local no cliente para armazenamento e sincronização posterior dos dados. | Equipe de Desenvolvimento |
| **Ausência de validação empírica em contexto exclusivamente domiciliar** | Dúvidas sobre a sustentação do engajamento e a autonomia no onboarding visual na rotina doméstica sem mediação presencial especializada. | Elaborar protocolo de teste de usabilidade domiciliar assistida por cuidadores para o próximo ciclo. | Pesquisador Responsável / Equipe Clínica |


## 13A  HIPÓTESES PARA VALIDAÇÃO

| H-ID | Hipótese | Guiding Principle | Será verificada no Doc 3 |
| --- | --- | --- | --- |
| H-01 | O onboarding visual permitirá uso autônomo sem necessidade de instrução presencial | GP-01 | Sim |
| H-02 | O feedback visual de falha reduzirá confusão e erros repetidos durante a tarefa | GP-02 | Sim |
| H-03 | A progressão gradual manterá engajamento ao longo das sessões do protocolo | GP-03 | Sim |
| H-04 | Os limites de duração e critérios de interrupção prevenirão fadiga excessiva | GP-04 | Sim |
| H-05 | Cores limpas e a paleta pastel tornará um ambiente fabril mais confortável de visualizar  | GP-05 | SIM |
| H-06 | Controle de volume para evitar desconforto auditivo | GP-06 | SIM |

| H-ID | Hipótese | Guiding Principle | Será verificada no Doc 3? |
| :--- | :--- | :---: | :---: |
| **H-01** | **Onboarding Visual e Autonomia:** O tutorial exclusivamente visual (Fase 0) por demonstração e ícones garantirá o entendimento das regras e o uso autônomo sem dependência de leitura. | **GP-01** | **Sim** |
| **H-02** | **Feedback Não Punitivo e Sustentação:** O feedback calibrado e neutro (brilho suave, retenção do pacote, sem alarmes vermelhos) reduzirá reações de ansiedade/frustração e aumentará o tempo de retenção. | **GP-02** | **Sim** |
| **H-03** | **Regressão Silenciosa e Engajamento:** O suporte adaptativo com redução silenciosa de perturbações em caso de hesitação manterá o engajamento longitudinal em crianças com TDAH/TOD associado. | **GP-03** | **Sim** |
| **H-04** | **Limites de Duração e Prevenção de Fadiga:** A trava de tempo por tentativa (30s) e pausas acionáveis pelo terapeuta prevenirão a fadiga atencional e a sobrecarga sensorial. | **GP-04** | **Sim** |
| **H-05** | **Conforto Estético e Seletividade de Cores:** O estilo cartoon com fundo limpo e o menu de restrição de paletas de cores evitarão distrações atencionais, hiperfoco ou recusa por aversão a cores. | **GP-05** | **Sim** |
| **H-06** | **Acomodação Auditiva e Conforto Sensorial:** O controle independente de volume com opção de desativar a BGM mantendo apenas SFX reduzirá o desconforto e o estresse por hipersensibilidade auditiva. | **GP-06** | **Sim** |
| **H-07** | **Acessibilidade Touchscreen em Tablets:** A interface com botões virtuais amplos e espaçados no móvel garantirá precisão de movimentação e taxa de conclusão equivalente ao PC. | **GP-07** | **Sim** |
| **H-08** | **Recalculo de Rota e Flexibilidade Cognitiva:** A introdução progressiva de fumaça e bloqueios imprevisíveis estimulará o recalculo de rota e a adaptação a mudanças de padrão. | **GP-08 / GP-03** | **Sim** |
| **H-09** | **Telemetria de Biomarcadores Digitais:** A extração silenciosa de métricas (hesitação angular, latência e eficiência de rota) produzirá um perfil fidedigno de navegação sem estresse de teste. | **GP-02 / GP-04** | **Sim** |
| **H-10** | **Construção de Mapa Cognitivo Topográfico:** A navegação egocêntrica guiada por placas coloridas favorecerá a formação de representação mental do espaço 3D (memória topográfica). | **GP-01 / GP-03** | **Sim** |