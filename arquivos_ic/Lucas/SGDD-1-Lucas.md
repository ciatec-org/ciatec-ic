**CIATec — GLIDE Framework**

# DOC 1 — GAME DESIGN DOCUMENT CIENTÍFICO
*Scientific Game Design Document (SGDD)*

Template v1.0  |  2026  |  CIATec
*Game Lifecycle for Inclusive Development and Evaluation*

> ⚙ *Este é o template do Doc 1 do GLIDE — o Game Design Document Científico (SGDD).*
> ⚙ *Agnóstico de população e condição de saúde — serve para qualquer projeto dentro do GLIDE.*
> ⚙ *Instruções em azul explicam como preencher. Alertas em vermelho indicam lacunas típicas.*
> ⚙ *Mantenha a estrutura de seções. Adapte o conteúdo ao projeto específico.*
> ⚙ *Atualize a cada novo ciclo de PPI incorporado. Idioma: PT-BR. Acrônimos em inglês.*

## 1  IDENTIFICAÇÃO DO PROJETO

**Nome do jogo:** *a preencher*

**Versão do documento:** *v1.0 — ciclo PPI inicial*

**Projeto vinculado:** ATGCP — Adaptive Therapeutic Game Calibration Protocol

**Organização:** CIATec

**Posição no Triple Diamond:** Transição 1º para 2º Diamante

**Ciclos de PPI incorporados:** PPI-ATGCP-TEA

**Pesquisador responsável:** Carlos Monteiro

**Data de criação:** 21/09/2026

**Última atualização:** 21/09/2026

## 2  CONCEITO DO JOGO

Jogo baseado no paradigma *N-Back Task*, o qual possui como construto, de acordo com documento de paradigmas fornecido pelo **CIATec**,

*Foca em memória de trabalho, especificamente os processos de manutenção, atualização e controle atencional. O participante recebe uma sequência contínua de estímulos e deve indicar se o estímulo atual corresponde ao apresentado N posições antes.*

No caso, a jogabilidade consistirá em partidas onde, por ciclos determinados de tempo, haverão estímulos sonoros sequenciais enumerados, que poderão ser musicais ou não, dividos em *timestamps* delimitados por metrônomo. 

No que diz respeito às músicas, haverão diferentes gêneros para maior alcance de gostos pessoais.

Cada ciclo de tempo será cronometrado e, quando chegar ao fim, o jogador será questionado a respeito de algum(s) dos estímulos anteriores e deverá responder de maneira correta qual foi o som ou parcela de música que ocorreu em algum(s) *timestamp(s)* específico(s) anterior(es). Depois, haverão mais ciclos até que a sequência se encerre.

A partir do desempenho do jogador, o sistema por baixo dos panos se adaptará de maneira inteligente para melhor adequamento às necessidades que forem identificadas dinamicamente.

O público alvo são usuários finais jovens TEA. A construção do jogo levará em consideração, inicialmente, as necessidades relatadas em documento *PPI* fornecido pela organização, com relatos reais que envolvem pacientes, cuidadores e profissionais relacionados.

Teríamos, então, dificuldade adaptativa, uma interface amigável e um jogo capaz de manter os jogadores imersos.

### 2.1  Premissa

Realização de escuta ativa de sequência sonora, *active recall* de elementos específicos.

### 2.2  Gênero e Plataforma
**Gênero:** jogo eletrônico musical, *serious game* terapêutico;
**Plataforma:** web, desktop, mobile;
**Modo de jogo:** majoritariamente single player, podendo haver métodos multiplayer sendo desenvolvidos eventualmente;
**Tecnologia de interação:** Cliques com cursor de *mouse*, ou interação com *touchscreen*

### 2.3  Público-Alvo

1) Usuários finais dentro do espectro autista (TEA), primariamente perfis de Suporte 1 (S1) e Suporte 2 (S2), menores de 18 anos, com acompanhamento profissional.

2) Para usuários de Suporte 3 (S3), o jogo não tem expectativa de uso autônomo, exigindo mediação clínica intensa (auxílio físico e verbal constante) e atuando em níveis de dificuldade (N) adaptados ou reduzidos a zero (associação direta).

3) Responsáveis legais e profissionais mediadores clínicos (terapeutas, psicólogos) com experiência direta no atendimento dessa população, que utilizarão relatórios gerados pelo jogo para acompanhamento.

## 3  OBJETIVO TERAPÊUTICO E EDUCACIONAL

### 3.1  Objetivo Terapêutico Principal

O jogo tem como objetivo o exercício com relação à atenção e aos diferentes níveis de memória do paciente, auxiliando a identificar fragilidades e realizando práticas terapêuticas adequadas.

### 3.2  Objetivos Secundários

O jogo pode servir como ponto de conforto durante crises, ajudando na autoregulação do paciente ao proporcionar um ambiente confortável, com sons que não sobrecarregam a pessoa individualmente.

Além disso, a coleta de dados pode ser útil para mapear necessidades diversas do paciente.

### 3.3  Fora do Escopo

O ensino de teoria musical ou o desenvolvimento de habilidades rítmicas profissionais estão fora do escopo deste jogo. A seleção de músicas e estímulos sonoros serve como ferramenta para manter o engajamento, atuar como reforçador terapêutico e proporcionar conforto sensorial, não possuindo finalidade educacional musical.

## 3A  GUIDING PRINCIPLES
> ⚙ *Esta seção é derivada da síntese de evidências do PPI — não de relatos individuais de participantes.*
> ⚙ *Os Guiding Principles funcionam como a bússola do projeto. Cada decisão de design deve ser rastreável a um princípio.*
> ⚙ *Um mesmo princípio pode ser sustentado por múltiplas evidências do PPI: entrevistas, observações, literatura, workshops.*Desenvolvimento multiplataforma: para celulares e computadores 
> ⚙ *Formato: GP-ID | Evidência sintetizada do PPI | Objetivo de design | Funcionalidades previstas.*
> ⚙ *Esta seção é referenciada nas Seções 4, 8 e 13A, e nos documentos Doc 2 e Doc 3.*

| GP | Evidência sintetizada do PPI | Objetivo de design | Funcionalidades previstas |
| --- | --- | --- | --- |
| GP-01 | Nem todos os usuários utilizam *tablet* ou *smartphone* no cotidiano | Tornar acessível para diferentes tipos de usabilidade | Desenvolvimento multiplataforma: para celulares e computadores. Suporte a *Touchscreen*, *desktop* e *web* |
| GP-02 | Existe usuário inserido em mais de um transtorno psicológico (TEA + TDAH + TOD) | Evitar deixar o jogo inflexível, excludente e desestimulante | Coleta de dados referentes à atenção/memória por parte de sistema *backend*, adaptabilidade dos questionamentos durante *gameplay* e da dificuldade|
| GP-03 |Todos os usuários são TEA, logo existe a chance de sobrecarga sensorial e eventual crise | Tornar o jogo menos atritivo no quesito sensorial | Multipla escolha de gêneros musicais ou tipos de som, além de questionários sobre preferências pessoais para interface e afins |
| GP-04 | Sessões prolongadas ou sem controle de carga podem aumentar fadiga e reduzir adesão | Preservar segurança e tolerabilidade | Limite de duração e critérios de interrupção |
| GP-05 | A abstração da relação causa-efeito na tela é uma barreira severa para usuários de Suporte 3, exigindo treino antes da demanda cognitiva. | Garantir compreensão da mecânica antes de testar a memória | Modo "Treino Pré-Jogo" com associação direta (N=0) e sem limite de tempo. |

> ⚠ **Cada Guiding Principle deve ter pelo menos uma evidência rastreável ao relatório de síntese do PPI.**

## 4  MECÂNICAS CORE  —  MDA: MECHANICS

### 4.1  Mecânica Principal

*Active Recall*

**Descrição:**

Quando o tempo pré-estabelecido para exibição de som terminar, jogador deve selecionar corretamente dentre opções de áudio oferecidas em um painel para indicar qual som ocorreu durante um intervalo de tempo **N-Passos** atrás. A interação com o painel é através de cliques com *mouse ou touchscreen*.

**Justificativa clínica:**

A mecânica implementa diretamente o princípio proposto pelo paradigma **N-Back Task**, atuando no exercício da memória e concentração.

**Guiding Principle:**

GP-02 (Evitar deixar o jogo inflexível e desestimulante, especialmente para comorbidades) e GP-03 (Tornar o jogo menos atritivo no quesito sensorial para evitar crises).

**Hipótese de design:**

Acreditamos que a eliminação de feedbacks punitivos (como ruídos de erro ou flashes de cor) previne a desregulação emocional e a sobrecarga sensorial, especialmente em perfis com alta competitividade ou baixa tolerância à frustração (como o TEA associado a TOD e TDAH). Ao manter o erro neutro e superestimar visualmente e sonoramente apenas os acertos, mitigamos a associação do jogo a sentimentos aversivos, prolongando o engajamento do paciente na sessão terapêutica.

**Origem PPI:**

Evidências originadas da observação do usuário U4-S2, que demonstrou alta competitividade e necessidade de um feedback de acerto reforçado para não se frustrar com pontuações baixas, e do usuário U3-S1 (TEA + TDAH + TOD), que apresentou irritabilidade e redução da tolerância com o aumento do desafio. Além disso, o PPI reforça transversalmente o cuidado com o excesso de estímulos simultâneos.

### 4.2  Sistema de Feedback

- O jogo utilizará um sistema de feedback positivo enfatizado.   Acertos: Geram feedback visual imediato (animações de recompensa contidas, para evitar distração) e reforço sonoro agradável (ex: som funcional integrado à música). A pontuação na tela focará nos acertos acumulados.   

- Erros: O feedback para o erro será neutro. Não haverá distorções de áudio, mudança drástica de paleta de cores ou sons de "falha", a fim de evitar estímulos aversivos, gatilhos de sobrecarga sensorial ou aumento de irritabilidade em perfis com alta competitividade ou comorbidades como TDAH/TOD. O erro resultará apenas na ausência da recompensa visual e na não progressão da fase. O usuário terá controle sobre o volume ou a opção de desativar os sons inteiramente, respeitando a variabilidade sensorial do espectro. 

**Justificativa clínica:**

Minimizar a aversão ao erro é fundamental para manter a tolerância à frustração e o engajamento ao longo da sessão, evitando abandonos precoces.

**Guiding Principle:**

GP-02 (Evitar deixar o jogo inflexível e desestimulante, especialmente para comorbidades) e 
GP-03 (Tornar o jogo menos atritivo no quesito sensorial para evitar crises).

**Hipótese de design:**

Acreditamos que a eliminação de feedbacks punitivos (como ruídos aversivos de erro ou flashes de cor repentinos) previne a desregulação emocional e a sobrecarga sensorial. Isso é especialmente crítico em perfis com alta competitividade ou baixa tolerância à frustração (como o TEA associado a TOD e TDAH). Ao manter o erro neutro e superestimular visualmente e sonoramente apenas os acertos, mitigamos a associação da atividade a sentimentos aversivos, prolongando o engajamento do paciente na sessão terapêutica.   

**Origem PPI:**

Evidências originadas da observação do usuário U4-S2, que demonstrou alta competitividade e necessidade de um feedback de acerto reforçado para não se frustrar com pontuações baixas. Além disso, fundamenta-se no usuário U3-S1 (TEA + TDAH + TOD), que apresentou irritabilidade e redução da tolerância com o aumento do desafio. O PPI também reforça transversalmente o cuidado com o excesso de estímulos simultâneos para evitar sobrecarga.  

### 4.3  Sistema de Progressão

O avanço será obtido a partir dos acertos. No caso, cada conjunto de *timestamps* funcionará como uma "fase". Um conjunto de fases irá compor uma música, caso o usuário tenha escolhido. 

Para cada fase, teremos um ou mais questionamentos. 

Errar faz com que seja decrementado um contador de tentativas restantes. Você pode avançar de fase, caso o contador de tentativas restantes não esteja zerado. Caso o contador esteja zerado, será necessário escutar novamente o conjunto de *timestamps* atual e acertar o questionamento.

**Justificativa clínica:**

Progressão baseada em desempenho consistente, não em acerto bruto. Calibração terapêutica requer controle de intensidade.

**Guiding Principle:**

GP-02 (Evitar deixar o jogo inflexível e desestimulante) e GP-04 (Sessões prolongadas ou sem controle de carga podem aumentar fadiga).

**Hipótese de design:**

A interrupção completa do fluxo sonoro em caso de acúmulo de erros e a necessidade de repetir desde o começo pode ser desnecessariamente frustrante. A lógica de progressão proposta busca amenizar essa frustração e manter o usuário engajado na tarefa, trazendo benefícios a partir da permanência no exercício terapêutico.

**Origem PPI:**

Evidências derivadas do comportamento do usuário U3-S1, que apresentou redução de tolerância à frustração com o aumento da dificuldade, e da necessidade relatada pelo cuidador C1 de adequar o ritmo para manter a adesão sem gerar sobrecarga.   

### 4.4  Onboarding

- O processo de aprendizado do jogo variará conforme a necessidade do usuário:Para perfis autônomos (ex: Suporte 1): O tutorial será embutido e opcional. O design permitirá início rápido da partida, visto que esses usuários costumam compreender rapidamente as regras e a progressão visual.   

- Para perfis que requerem instrução (ex: Suporte 2): Será disponibilizada uma demonstração animada visual (sem dependência de texto longo) antes do início da primeira partida, mostrando exatamente o que deve ser clicado/tocado.   

- Para perfis com necessidade de mediação (Suporte 3): Haverá um modo de "Treino Pré-Jogo" sem contagem de pontuação ou regressiva, desenvolvido para uso com suporte físico e verbal do terapeuta, permitindo a compreensão da associação de causa e efeito na tela antes de introduzir qualquer desafio de memória.


**Guiding Principle:**

GP-05 (A abstração da relação causa-efeito na tela é uma barreira severa que exige treino antes da demanda cognitiva) e GP-01 (Tornar acessível para diferentes tipos de usabilidade).

**Hipótese de design:**

Acreditamos que a divisão do onboarding em três camadas atenderá à alta heterogeneidade funcional do espectro autista mapeada no PPI. Ao remover tutoriais forçados para perfis com autonomia digital (S1), evitamos o tédio e a perda de engajamento precoce. Para o perfil S2, a demonstração puramente visual contorna possíveis barreiras de leitura e interpretação de texto. Por fim, para o perfil S3, a remoção total da pressão temporal (cronômetro) e cognitiva (o construto N-Back) no "Treino Pré-Jogo" permite que o usuário e o mediador foquem inteiramente em quebrar a barreira primária de abstração — compreender a relação de causa e efeito dos cliques na interface.

## 5  DINÂMICAS  —  MDA: DYNAMICS

- O jogo se inicia com a avaliação do estado atual da criança e a seleção do estímulo auditivo preferido (músicas de diferentes gêneros ou ruídos específicos).   

- A sessão progride com a execução contínua do áudio (fases com duração padrão de 30 segundos, ajustáveis conforme tolerância).   

- A música pausa, o cronômetro entra em cena e o desafio N-Back é apresentado, exigindo o active recall.   

- Ao final de uma partida completa, a criança recebe a pontuação enfatizando os acertos e ganha a recompensa de escutar a música inteira sem pausas. 

### 5.1  Arco de uma Sessão Típica

- O jogo avalia o nível de memória de curto prazo (especialmente para usuários com TDAH associado).   

- A progressão de dificuldade se dá pelo aumento do número "N" de passos atrás que devem ser lembrados, ou pela complexidade/velocidade do timestamp musical.   

- Caso o contador de tentativas zere na fase, o jogo não emite telas punitivas; em vez disso, o usuário escuta o conjunto de timestamps novamente para consolidar o aprendizado.   

### 5.2  Progressão Longitudinal

- Variável N-Back: Distância do estímulo a ser lembrado (1-back, 2-back, etc.).

- Velocidade (BPM): Alteração no andamento da música ou ritmo do metrônomo.   

- Duração da fase: Tempo de exposição aos blocos sonoros antes da pausa, utilizando 30 segundos como base inicial e permitindo expansão se a criança estiver engajada.

### 5.3  Calibração de Intensidade Terapêutica

- Variável N-Back: Distância do estímulo a ser lembrado (1-back, 2-back, etc.).

- Velocidade (BPM): Alteração no andamento da música ou ritmo do metrônomo.   

- Duração da fase: Tempo de exposição aos blocos sonoros antes da pausa, utilizando 30 segundos como base inicial e permitindo expansão se a criança estiver engajada.

## 6  EXPERIÊNCIA PRETENDIDA  —  PLAYER EXPERIENCE (MDA: AESTHETICS)

As dimensões prioritárias para esta população são Sensation (Sensação) e um Challenge (Desafio) estritamente calibrado. A experiência pretendida deve servir como um "ponto de conforto" e ferramenta de autorregulação. O jogador deve se sentir estimulado pela música, mas em um ambiente seguro, onde os "atritos" ficam exclusivamente restritos ao exercício de memória e atenção, sem sobrecarga sensorial desnecessária. Para isso, a ausência de pressão punitiva por erro garantirá uma experiência lúdica fluida, com o jogador sentindo-se no controle da dificuldade.

## 7  ELEMENTAL TETRAD

### 7.1  Mechanics  —  Regras e Sistemas

- Execução musical pausada por ciclos cronometrados, onde o jogador realiza o *Active Recall* de estímulos anteriores (N-Back) e avança caso atinja a pontuação ou esgote as tentativas disponíveis.   

- Restrições da população: Erros não devem produzir punições sensoriais; deve haver mecanismo de regressão de dificuldade facilitado para mitigar a frustração (especialmente útil para TEA associado a TOD e TDAH).   

### 7.2  Story  —  Narrativa e Contexto

- O jogador assume o papel de um músico aprendiz.   

- Um "professor" narra os trechos tocados e, em seguida, realiza perguntas para testar a memória do aluno, o que justifica a narração de fundo e fornece um envelopamento narrativo amigável para o N-Back.  

### 7.3  Aesthetics  —  Visual, Som e Sensação

- Apresentação visual por meio de blocos de ondas sonoras ou notas musicais enfileiradas.   

- Restrições da população: Fundo de tela branco/neutro como padrão para conforto visual. Controle absoluto de volume musical, permitindo silenciamento se a criança desejar focar apenas no estímulo visual. As cores dos blocos devem ser customizáveis para evitar rejeição intencional por hiperfoco em cores específicas. 

### 7.4  Technology  —  Plataforma e Implementação

- Plataformas Web, Desktop e Mobile (abrangência multiplataforma).   

- Interação por meio de cliques de mouse ou touchscreen, democratizando o acesso e facilitando o uso domiciliar por perfis que não possuem computador (majoritariamente usuários de tablets).  

## 8  MAPEAMENTO LM-GM
> ⚙ *LM-GM: Learning Mechanics e Game Mechanics (Arnab et al., 2015). Seção exclusiva do GDD científico.*
> ⚙ *Para cada objetivo clínico ou educacional, identifique qual mecânica de jogo o operacionaliza e qual Guiding Principle sustenta essa relação.*
> ⚠ **Se um objetivo clínico não tiver mecânica correspondente, é lacuna de design. Registre na Seção 13.**

| Objetivo clínico / educacional | Mecânica de jogo | Como operacionaliza | GP |
| --- | --- | --- | --- |
| Desenvolver memória de trabalho (manutenção e atualização) | Active Recall (N-Back) | Exige que o jogador retenha a informação sonora e a acesse após N passos | GP-02 |
| Manter engajamento e tolerância à frustração | Feedback neutro para erros e regressão facilitada | Evita sobrecarga sensorial e permite que o jogador ajuste o desafio antes de desistir | GP-03 |
| Promover autorregulação (ponto de conforto) | Customização sensorial (volume, gênero musical, interface neutra) | Permite adequar o ambiente virtual ao perfil sensorial único do usuário, minimizando gatilhos | GP-03, GP-01 |

## 9  PERSONAS E REQUISITOS DERIVADOS
> ⚙ *Personas em formato sintético, derivadas do F03 do ciclo de PPI. Não reproduza o F03 completo aqui.*
> ⚙ *Cada persona deve gerar pelo menos três requisitos operacionalizáveis. Atualize a cada novo ciclo de PPI.*
> ⚙ *Personas não identificam participantes individuais. São perfis compostos derivados da síntese do PPI.*

### 9.1  Persona 1 — O Explorador Focado (Suporte 1)

**Identificação funcional:** Usuário autônomo digitalmente, compreende regras rapidamente, mas pode ter frustração rápida (ex: comorbidade TDAH/TOD).

**Ciclo PPI de origem:** PPI-ATGCP-TEA (Perfil U1-S1 a U3-S1)

**Contexto de uso:** Domiciliar ou clínico, sessões autônomas após primeira instrução.

**Requisitos derivados:** 

– Tutorial rápido e "pulável".
– Opção de regressão de fase voluntária ao sentir frustração.
– Fundo de tela branco/neutro como padrão.

**Guiding Principles relacionados:** GP-01, GP-02

**Impacto nas decisões:** Seções 4.4, 5.2, 11.2

**Status de validação:** Válida

### 9.2  Persona 2 — O Competidor Sensível (Suporte 2)

**Identificação funcional:** Baixa tolerância a falhas (alta competitividade), risco de rejeição por hiperfoco em cores/estímulos.

**Ciclo PPI de origem:** PPI-ATGCP-TEA (Perfil U4-S2)

**Contexto de uso:** Domiciliar com supervisão ou clínico.

**Requisitos derivados:** 

– Onboarding visual e concreto obrigatório na primeira vez.
– Feedback de erro estritamente neutro (sem sons punitivos).
– Customização de cores para os blocos de resposta.

**Guiding Principles relacionados:** GP-03, GP-04

**Impacto nas decisões:** Seções 4.2, 4.4, 10.1

**Status de validação:** Válida (com necessidade de mais testes domiciliares)

### 9.3  Persona 3 — O Aprendiz Mediado (Suporte 3)

**Identificação funcional:** Alta barreira de abstração (dificuldade em entender a relação causa-efeito na tela) e necessidade de mediação física.

**Ciclo PPI de origem:** PPI-ATGCP-TEA (Perfil U5-S3 e U6-S3)

**Contexto de uso:** Estritamente clínico, com mediação física e verbal constante.

**Requisitos derivados:**

– Modo de "Treino Pré-jogo" (associação direta, sem N-Back, sem cronômetro).
– Ritmo extremamente reduzido e controlável pelo mediador.
– Obrigatoriedade de jogar sentado por segurança postural.

**Guiding Principles relacionados:** GP-04

**Impacto nas decisões:** Seções 2.3, 4.4, 11.3

**Status de validação:** Válida

## 10  INTERFACE E ACESSIBILIDADE
> ⚙ *Acessibilidade está integrada à especificação de interface, não é seção separada.*
> ⚙ *Referência: WCAG 2.1, ISO 9241-210, UDL quando aplicável.*

### 10.1  Princípios de Interface

- A interface deve possuir mínimo de ruído visual (ex: evitar estrelinhas ou fundos excessivamente animados) para prevenir distração.   

- As opções de resposta devem reter o mesmo símbolo visual (bloco) apresentado inicialmente na sequência sonora, facilitando o reconhecimento padronizado. 

### 10.2  Requisitos de Acessibilidade por Domínio

**Visual:**

- Cronômetro posicionado de forma visível na parte superior; opção mandatória de fundo branco/neutro; disposição enfileirada clara da estrutura da música.

**Auditivo:**

- Opção de narração de fundo para os timestamps, facilitando o acompanhamento para pessoas com visão reduzida; controle ajustável de volume global (0 a 100%).

**Motor:**

- Área de clique (hitbox) dos blocos deve ser generosa para acomodar variações de coordenação motora fina fina em telas touchscreen; tempo de resposta ao N-Back ajustável.

**Linguístico:**

- Interface com mínimo de texto; foco em ícones universais (ex: play, pause, volume, recarregar).

**Cultural:**

- Uso de estímulos musicais familiares ou agradáveis à criança (ex: músicas infantis populares ou temas de interesse), sem imposição de gêneros específicos.

### 10.3  Telas e Fluxo de Navegação

1) Tela Inicial/Perfil: Avaliação rápida do estado atual (humor) e escolha do estímulo (música/ruído).   

2) Modo Treino (Onboarding): Demonstração visual ou modo sem pontuação.   

3) Tela de Jogo: Cronômetro no topo, visualização em cascata (blocos) da música; painel de resposta que surge apenas durante as pausas de questionamento.   

4) Tela de Sessão Finalizada: Pontuação destacando apenas acertos e botão para ouvir a música completa (reforçador).   

## 11  PARÂMETROS DE FASE E PROGRESSÃO
> ⚙ *Esta seção conecta o GDD científico ao protocolo clínico (ATGCP ou equivalente).*
> ⚙ *Inclua critérios explícitos de avanço, regressão e interrupção, não apenas progressão ascendente.*

### 11.1  Variáveis de Fase

| Variável | Descrição e faixa de valores |
| --- | --- |
| Distância do N-Back | faixa: 1 a 3 (ou modo de associação direta 0 para S3); impacto: demanda primária de memória de trabalho |
| Duração do clipe musical | faixa: 15s a 45s (padrão 30s); impacto: exigência de foco e risco de dispersão |
| Complexidade das opções | faixa: 2 a 4 blocos de resposta; impacto: confusão visual e taxa de erro |

### 11.2  Critérios de Progressão, Regressão e Interrupção

| Evento | Critério |
| --- | --- |
| Avanço de fase | Acerto consistente nos questionamentos de N-Passos no limite de tempo |
| Regressão de fase | Aumento de erros sequenciais ou solicitação ativa da criança (retorno a opções mais fáceis para evitar ataques de frustração). |
| Interrupção de sessão | Irritabilidade persistente com a dificuldade, dispersão de olhar frequente, desengajamento da tarefa ou vocalizações de recusa. |
| Interrupção do protocolo | Sinais consistentes de sobrecarga sensorial ou recusa persistente em participar ao longo de 3 sessões consecutivas. |

### 11.3  Faixas de Fase por Perfil

- Suporte 1 (S1): Entrada no N-Back = 1, duração de 30s. Progressão permitida até N=3 se engajado.

- Suporte 2 (S2): Entrada no N-Back = 1, duração de 20-30s. Foco na repetição antes de aumentar o N para evitar frustração.   

- Suporte 3 (S3): Associação direta (N=0) e sem limite de tempo punitivo. Foco apenas em entender a mecânica de resposta com mediação.

## 12  REQUISITOS TÉCNICOS CONSOLIDADOS
> ⚙ *Esta seção alimenta diretamente o Doc 2 — Backlog Ágil. Organize por domínio com prioridade e origem.*
> ⚠ **Requisitos sem prioridade definida bloqueiam o Doc 2. Não deixe em branco.**

| Domínio | Requisito | Prioridade | Origem |
| --- | --- | --- | --- |
| Funcional | Feedback visual neutro para erros (sem punição sonora/visual) | Alta | PPI-ATGCP (U4-S2) |
| Sensorial | Fundo de tela branco/neutro como padrão inicial | Alta | PPI-ATGCP (S1) |
| Sensorial | Controle mestre de volume (0-100%) acessível durante o jogo | Alta | PPI-ATGCP |
| Progressão | Botão de "regressão de fase" para manejo de frustração | Média | PPI-ATGCP (U3-S1)    |
| Interface | Modo "Treino Pré-Jogo" sem cronômetro ou contagem de erro | Alta | PPI-ATGCP (S3) |
| Acessibilidade | Tutorial rápido embutido com opção de "Pular" (Skip) | Média | Persona 1 (S1) |
| Funcional | O jogo não deve exigir postura em pé; deve ser jogável sentado. | Alta | Persona 3 (S3) / PPI-ATGCP |

## 13  LACUNAS E DECISÕES PENDENTES
> ⚙ *Seção viva, atualizada a cada ciclo de PPI e a cada iteração de desenvolvimento.*
> ⚙ *Para cada lacuna: descrição, impacto, ação necessária, responsável.*
> ⚠ **Lacunas que bloqueiam o Doc 2 devem ser marcadas como CRÍTICAS.**

| Lacuna / Decisão pendente | Impacto | Ação necessária | Responsável |
| --- | --- | --- | --- |
| Viabilidade real do uso domiciliar sem supervisão para perfil S2 | Risco de abandono do jogo por frustração sem mediador | Incluir testes puramente domiciliares (sem clínicos presentes) no próximo ciclo PPI | Pesquisador responsável |
| Direitos autorais das músicas | Limita o apelo do reforçador se as músicas favoritas da criança não puderem ser usadas | Pesquisar bibliotecas de áudio royalty-free ou permissões para uso em serious games | Equipe de desenvolvimento |
| Desempenho do jogo em tablets antigos / de baixo custo | Travamentos ou lentidão podem ser confundidos com aumento de dificuldade pela criança (como ocorreu com U2-S1 no PPI). | Realizar testes de framerate e latência de toque em dispositivos mobile de entrada. | Equipe de desenvolvimento |

## 13A  HIPÓTESES PARA VALIDAÇÃO
> ⚙ *Esta seção consolida todas as hipóteses de design dispersas na Seção 4.*
> ⚙ *Cada hipótese é uma aposta testável derivada de um Guiding Principle.*
> ⚙ *Esta seção é o ponto de entrada para a construção do protocolo no Doc 3.*
> ⚙ *Não define instrumentos ou métodos de validação. Isso pertence ao Doc 3.*

| H-ID | Hipótese | Guiding Principle | Será verificada no Doc 3 |
| --- | --- | --- | --- |
| H-01 | O feedback neutro de falha evitará o abandono prematuro por parte de usuários com baixa tolerância à frustração. | GP-02 | Sim |
| H-02 | O uso do jogo via tela touchscreen (tablet/celular) aumentará a adesão e o tempo de uso em comparação ao Desktop. | GP-01 | Sim |
| H-03 | A opção de ouvir a música inteira ao final da partida atuará como um reforçador positivo forte o suficiente para garantir a repetição do ciclo. | GP-03 | Sim |
| H-04 | O Modo "Treino Pré-Jogo" (Associação Direta N=0) permitirá que usuários S3 compreendam a relação de clique/toque na tela, possibilitando a futura introdução do N-Back. | GP-05 | Sim |

> ⚠ **Cada hipótese deve ser rastreável a um Guiding Principle. Hipóteses sem GP de origem indicam lacuna na Seção 3A.**
