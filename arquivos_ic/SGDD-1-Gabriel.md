# CIATec — GLIDE Framework

# DOC 1 — GAME DESIGN DOCUMENT CIENTÍFICO

*Scientific Game Design Document (SGDD)*

**Versão:** v1.0 — formalização inicial do conceito
**Framework:** GLIDE — Game Lifecycle for Inclusive Development and Evaluation
**Paradigma científico:** Mental Rotation / Shepard–Metzler

---

## 1. IDENTIFICAÇÃO DO PROJETO

**Nome do jogo:** *Meu Pequeno Reino*
**Versão do documento:** v1.0 — formalização inicial do SGDD
**Projeto vinculado:** CIATec — Plataforma Aberta de Jogos Adaptativos para Educação Inclusiva
**Organização:** CIATec
**Posição no Triple Diamond:** *a confirmar junto à coordenação do GLIDE*. O jogo encontra-se atualmente em fase de co-design e definição conceitual, anterior à consolidação do protótipo e de seus parâmetros experimentais.
**Ciclos de PPI incorporados:** Relatório PPI TEA v1.0 — Fase 1 de co-design, abril a maio de 2026, incorporado de forma contextual e parcial
**Pesquisador responsável:** Gabriel Milagres
**Data de criação:** 15/09/2026
**Última atualização:** 21/09/2026

### Nota sobre o PPI utilizado

O PPI disponível foi realizado com seis crianças com TEA, entre 5 e 10 anos, além de profissionais clínicos e cuidador, e buscou orientar decisões de design relacionadas a um jogo terapêutico baseado em captura de movimento.

Como o jogo descrito neste SGDD utiliza outro paradigma e outra forma de interação, os achados não são tratados como validação direta desta proposta. Foram incorporadas apenas evidências consideradas transferíveis ao desenho de experiências digitais para o público em questão, principalmente aquelas relacionadas a onboarding, variabilidade sensorial, tolerância à frustração, quantidade de estímulos simultâneos, necessidade de configurabilidade e heterogeneidade entre usuários.

## O próprio relatório reconhece que o PPI informa decisões de design, mas não valida paradigmas cognitivos, e que suas decisões devem permanecer como hipóteses a serem testadas em ciclos posteriores.

## 2. CONCEITO DO JOGO

### 2.1. Premissa

O jogo será desenvolvido para o público infantil e terá como cenário uma pequena vila ou reino em processo de crescimento. O jogador assume uma posição de responsabilidade nesse espaço e participa de seu desenvolvimento ao analisar peças e materiais apresentados pelos habitantes para diferentes construções.

Cada habitante traz uma peça que acredita pertencer a determinado projeto. Consultando o **Grande Livro de Projetos**, o jogador observa a estrutura necessária e decide se a peça apresentada corresponde ao mesmo objeto visto em outra orientação ou se possui uma estrutura diferente.

As decisões fazem parte do cotidiano do reino e contribuem para seu crescimento, permitindo o surgimento de novas construções, habitantes, atividades e regiões exploráveis. A intenção é que a criança perceba sua experiência principalmente como a construção e o cuidado de um mundo próprio, enquanto a tarefa cognitiva permanece incorporada à própria jogabilidade.

---

### 2.2. Gênero e Plataforma

**Gênero:** serious game científico/avaliativo com elementos de construção de mundo, exploração, inspeção e puzzle visuoespacial.

**Plataforma:** a definir. Há possibilidade de desenvolvimento voltado a dispositivos móveis, potencialmente utilizando Flutter/Flame, mas Unity permanece como alternativa técnica e nenhuma tecnologia é considerada definitiva nesta etapa.

**Modo de jogo:** single player.

**Contexto de uso:** ainda não definido entre contexto escolar, supervisionado ou outros contextos possíveis.

**Tecnologia de interação:** interação digital simples, baseada principalmente em seleção de respostas. A implementação específica dependerá da plataforma escolhida.

---

### 2.3. Público-Alvo

O jogo será desenvolvido para estudantes dos anos iniciais do Ensino Fundamental, incluindo crianças com diferentes perfis de desenvolvimento e com atenção especial à inclusão de crianças com Transtorno do Espectro Autista.

A proposta não pressupõe a criação de um jogo separado ou de um “modo TEA”. A intenção é que diferentes crianças compartilhem o mesmo núcleo de gameplay, enquanto recursos de acessibilidade e a demanda cognitiva possam ser ajustados conforme necessidades funcionais e desempenho observado.

A escolha do paradigma também não parte da suposição de que crianças autistas possuam uma vantagem geral em Mental Rotation. Meta-análise sobre habilidades visuoespaciais encontrou pequenas vantagens médias em tarefas como *Block Design* e *Figure Disembedding*, mas não identificou diferença clara entre grupos especificamente em Mental Rotation.

Há, por outro lado, estudos de eye-tracking que identificaram, em um subgrupo de crianças autistas muito pequenas, maior atenção relativa a estímulos geométricos dinâmicos quando apresentados ao lado de estímulos sociais. O achado é relevante como contexto para pesquisas sobre atenção visual no TEA, mas não pode ser generalizado para todas as crianças autistas e não implica melhor habilidade de rotação mental.

---

## 3. OBJETIVO TERAPÊUTICO E EDUCACIONAL

### 3.1. Objetivo Terapêutico Principal

O jogo **não possui objetivo terapêutico definido nesta etapa**.

Seu objetivo principal é científico e avaliativo: desenvolver uma implementação gamificada e adaptável do paradigma de Mental Rotation capaz de provocar e registrar decisões baseadas em transformação visuoespacial dentro de uma experiência adequada ao público infantil.

No paradigma clássico de Shepard e Metzler, o participante deve reconhecer se duas representações correspondem à mesma estrutura tridimensional observada em diferentes orientações. O estudo original encontrou aumento do tempo necessário para reconhecer objetos equivalentes conforme aumentava a diferença angular entre suas orientações.

A proposta deste jogo não consiste em reproduzir diretamente o teste clássico, mas em incorporar sua operação cognitiva central a uma mecânica que possua significado dentro de um contexto lúdico.

---

### 3.2. Objetivos Secundários

O jogo pretende:

* preservar Mental Rotation como operação necessária para solucionar a mecânica principal;
* permitir coleta futura de indicadores comportamentais relacionados ao desempenho na tarefa, sem atribuir significado clínico automaticamente a esses dados;
* reduzir dependência de alfabetização, linguagem verbal, percepção cromática e habilidade motora fina;
* permitir adaptação da demanda cognitiva conforme o comportamento observado;
* preservar uma experiência positiva mesmo quando a criança apresenta dificuldades;
* sustentar motivação por meio da construção e transformação persistente do reino;
* oferecer escolhas lúdicas que permitam autonomia sem modificar necessariamente o núcleo científico;
* permitir que crianças com diferentes perfis utilizem o mesmo universo de jogo.

A gamificação será tratada como parte relevante da própria implementação, e não como camada metodologicamente neutra. Em um estudo com 100 crianças de 6 a 9 anos, uma versão gamificada de uma tarefa de Mental Rotation produziu desempenho diferente da versão básica, reforçando a necessidade de validar a implementação resultante como instrumento próprio.

---

### 3.3. Fora do Escopo

Nesta etapa, o jogo:

* não diagnostica TEA;
* não constitui instrumento clínico validado;
* não substitui avaliação neuropsicológica;
* não pretende medir capacidade intelectual;
* não pressupõe uma habilidade visuoespacial característica de todas as pessoas autistas;
* não possui eficácia terapêutica estabelecida;
* não pretende ensinar formalmente geometria;
* não atribui significado clínico isolado a acertos, erros ou tempos de resposta;
* não considera diagnóstico suficiente para determinar automaticamente o nível de dificuldade de um jogador.

---

## 3A. GUIDING PRINCIPLES

Os Guiding Principles abaixo utilizam apenas evidências que podem ser rastreadas ao PPI já realizado. Como esse PPI foi desenvolvido para outro jogo, sua aplicação ao presente projeto permanece como hipótese a ser verificada em ciclos específicos deste protótipo.

| GP                                                | Evidência sintetizada do PPI                                                                                                                                                    | Objetivo de design                                                                                             | Funcionalidades previstas                                                                     |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| **GP-01 — Instrução concreta e multimodal**       | Participantes com diferentes níveis de suporte apresentaram necessidades distintas de instrução; para alguns, demonstrações visuais e concretas foram consideradas importantes. | Fazer com que a regra possa ser compreendida sem depender de leitura extensa ou explicação verbal abstrata.    | Tutorial visual, demonstração animada, símbolos, áudio complementar e texto simples.          |
| **GP-02 — Configurabilidade sensorial**           | Houve respostas distintas ao áudio, com recomendação convergente de controle de volume e possibilidade de desativá-lo.                                                          | Permitir que características sensoriais não essenciais sejam ajustadas.                                        | Controle de áudio, possibilidade de reduzir efeitos e animações não essenciais.               |
| **GP-03 — Progressão com baixa punição**          | Participantes demonstraram respostas distintas ao aumento da dificuldade, incluindo irritabilidade e frustração com desempenho ou pontuação.                                    | Evitar que dificuldade cognitiva produza perda significativa de progresso ou sensação persistente de fracasso. | Feedback positivo, ausência de perda de progresso e regressão de dificuldade sem penalização. |
| **GP-04 — Adaptação à heterogeneidade funcional** | O PPI encontrou diferenças relevantes entre participantes e concluiu que um design uniforme não seria adequado para todos os perfis.                                            | Permitir que a experiência responda ao usuário, em vez de presumir um perfil único associado ao diagnóstico.   | Ajustes de acessibilidade e adaptação de dificuldade com base na interação e no desempenho.   |
| **GP-05 — Controle da carga visual**              | O PPI recomendou evitar excesso de elementos simultâneos, pois elementos decorativos adicionais poderiam competir pela atenção.                                                 | Manter o momento experimental visualmente legível sem empobrecer o restante do mundo.                          | Redução de movimento e estímulos não essenciais durante a comparação das peças.               |
| **GP-06 — Possibilidade de interrupção**          | O PPI mostrou que sinais de desconforto e necessidade de interrupção variam entre indivíduos.                                                                                   | Não obrigar a criança a permanecer em uma atividade quando deseja interrompê-la.                               | Pausa e saída acessíveis, sem penalização por interrupção voluntária.                         |

### Princípios de Design específicos deste jogo

Como nem todas as decisões do projeto têm origem no PPI, são registrados separadamente os seguintes **Design Principles (DP)**:

| DP        | Princípio                                                                                                                                           |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **DP-01** | A rotação mental deve ser necessária para responder; o jogador não poderá rotacionar livremente o objeto durante o trial.                           |
| **DP-02** | A cor poderá compor a estética, mas não deverá determinar a resposta experimental.                                                                  |
| **DP-03** | Personagens podem sustentar a narrativa, mas comportamento social, expressão ou personalidade não poderão fornecer pistas sobre a resposta correta. |
| **DP-04** | Desempenho científico e progresso lúdico não serão equivalentes: maior dificuldade na tarefa não deve impedir a criança de desenvolver o reino.     |
| **DP-05** | Construções devem modificar a experiência e desbloquear atividades, não funcionar apenas como indicadores abstratos de progresso.                   |
| **DP-06** | A adaptação deverá responder ao desempenho e às necessidades funcionais, não ao diagnóstico de forma isolada.                                       |

---

## 4. MECÂNICAS CORE — MDA: MECHANICS

### 4.1. Mecânica Principal — Inspeção de Peças

**Descrição:**

Um habitante chega trazendo uma peça destinada a determinada construção. O jogador consulta o **Grande Livro de Projetos**, observa a estrutura necessária e compara visualmente a referência com a peça apresentada.

A decisão consiste em determinar se a peça corresponde à mesma estrutura observada sob outra orientação ou se possui uma configuração estrutural incompatível.

O fluxo central é:

**habitante chega**
→ **apresenta uma peça**
→ **jogador consulta o projeto**
→ **compara as estruturas**
→ **decide se correspondem**
→ **a peça recebe um destino**
→ **o reino progride**

Uma peça incompatível não significa necessariamente que o personagem tentou enganar o jogador. Ela pode ter sido confundida durante transporte, fabricada de forma incorreta, destinada a outra construção ou simplesmente ser semelhante à peça procurada.

**Justificativa científica:**

A comparação entre estruturas em diferentes orientações busca preservar a operação central do paradigma de Mental Rotation. Entretanto, os estímulos ainda precisarão ser validados para evitar estratégias alternativas baseadas em características locais ou detalhes salientes, em vez de transformação espacial propriamente dita.

**Guiding Principle:** decisão de design específica — DP-01; interface relacionada também a GP-01 e GP-05.

**Hipótese de design:**

Inserir a comparação espacial em uma tarefa funcional do reino pode fazer com que Mental Rotation seja percebido como parte da própria jogabilidade, reduzindo a sensação de repetição de um teste convencional.

**Origem PPI:** não derivada do PPI. Mecânica fundamentada no paradigma científico e no processo de design deste jogo.

---

### 4.2. Sistema de Feedback

Quando a criança classifica corretamente uma peça, ela funciona de acordo com o projeto e pode ser incorporada ao processo de construção. Acertos consecutivos alimentam uma **streak**, que poderá aumentar multiplicadores de pontos ou moedas e funcionar como recompensa adicional.

Caso a classificação esteja incorreta, a peça simplesmente não funcionará para aquela finalidade. A streak é interrompida, mas a criança não perde construções, moedas já adquiridas ou progresso acumulado no reino.

O feedback deverá enfatizar o resultado da ação no mundo, e não apresentar a resposta como falha pessoal. Não se pretende utilizar repreensão dos personagens, mensagens agressivas de erro ou punições que comprometam o progresso.

**Justificativa científica e de acessibilidade:**

O PPI registrou frustração relacionada ao aumento da dificuldade e à percepção de pontuação baixa em alguns participantes, recomendando enquadramento mais positivo do desempenho.

**Guiding Principle:** GP-03; DP-04.

**Hipótese de design:**

Uma recompensa adicional por sequências de acertos poderá preservar sensação de domínio para quem apresenta bom desempenho sem transformar erros em perdas significativas para crianças que encontrem maior dificuldade.

**Origem PPI:** GP-03 deriva do PPI; streak e multiplicadores são decisões específicas do presente jogo.

> **Ponto de validação:** feedback explícito após cada trial pode produzir aprendizagem ao longo da sessão. A influência desse feedback sobre a medida de Mental Rotation deverá ser avaliada posteriormente.

---

### 4.3. Sistema de Progressão

A progressão será dividida em três dimensões que não devem ser confundidas entre si.

#### Progressão lúdica

O jogador desenvolve o reino, desbloqueia construções, encontra personagens e acessa novas experiências. Essa progressão deverá depender principalmente da participação no jogo, e não de desempenho cognitivo elevado.

#### Adaptação da demanda cognitiva

Caso a criança apresente erros recorrentes e tempos de resposta elevados, o jogo poderá reduzir a complexidade das estruturas e evitar transformações espaciais mais exigentes. Caso a tarefa esteja sistematicamente simples, a demanda poderá aumentar gradualmente.

Não serão definidos nesta etapa percentuais, limiares ou valores angulares específicos.

#### Adaptação de acessibilidade

Características que não fazem parte do construto, como volume, intensidade de animações ou quantidade de estímulos ambientais, poderão ser ajustadas sem que isso seja tratado como avanço ou regressão cognitiva.

**Guiding Principles:** GP-02, GP-03, GP-04; DP-04 e DP-06.

**Hipótese de design:**

Separar essas três dimensões deverá permitir que o jogo responda às necessidades individuais sem transformar cada adaptação de acessibilidade em alteração da dificuldade científica.

---

### 4.4. Onboarding

O tutorial deverá ensinar a ideia central da tarefa por demonstração.

Inicialmente, uma peça poderá ser apresentada enquanto gira fisicamente, mostrando que sua orientação muda sem que sua estrutura deixe de ser a mesma. Em seguida, será apresentado um exemplo de estrutura realmente diferente. A criança então realiza tentativas simples até demonstrar compreensão da regra.

A rotação explícita é apropriada no tutorial porque o objetivo nessa etapa é explicar o conceito. Durante a tarefa principal, porém, o jogador não deverá rotacionar livremente a peça, pois isso poderia externalizar a transformação que se pretende que ocorra mentalmente.

O onboarding deverá utilizar demonstração visual, símbolos, áudio complementar e texto simples, sem tornar a leitura obrigatória.

As diretrizes UDL 3.0 recomendam oferecer múltiplas formas de representação e destacam que nenhuma modalidade é ideal para todos os aprendizes.

**Guiding Principle:** GP-01; DP-01.

**Hipótese de design:**

Uma demonstração concreta da regra poderá reduzir a dependência de explicações verbais e permitir que crianças em diferentes estágios de alfabetização compreendam a mecânica inicial.

---

## 5. DINÂMICAS — MDA: DYNAMICS

### 5.1. Arco de uma Sessão Típica

Uma sessão deverá alternar momentos de exploração/narrativa com momentos de comparação visuoespacial.

Um fluxo possível é:

**entrada no reino**
→ **visualização do estado atual da vila**
→ **chegada de um habitante**
→ **apresentação da necessidade de uma construção**
→ **comparação de peças**
→ **feedback e recompensa**
→ **avanço de uma construção**
→ **possibilidade de exploração ou interação no mundo**
→ **novo conjunto de situações**

A duração total da sessão e a quantidade de trials ainda não estão definidas.

A criança deverá ter acesso a pausa ou encerramento voluntário e não deverá ser pressionada a concluir uma quantidade fixa de trials quando deseja interromper a atividade.

---

### 5.2. Progressão Longitudinal

O reino deverá persistir entre sessões, permitindo que a criança reconheça construções desenvolvidas anteriormente e observe o impacto acumulado de sua participação.

As construções poderão estabelecer relações entre si. Uma fazenda pode posteriormente se relacionar a um moinho e a uma padaria; uma ponte pode abrir uma nova região; um observatório pode permitir uma atividade noturna de observação do céu.

O desenvolvimento do mundo também poderá oferecer escolhas, de modo que jogadores diferentes construam reinos distintos sem que isso necessariamente altere a tarefa científica.

A adaptação cognitiva ocorrerá paralelamente a essa progressão, mas não deverá ser representada como uma sequência explícita de “níveis de inteligência” ou capacidade.

---

### 5.3. Calibração da Demanda Cognitiva

Como não há objetivo terapêutico definido, esta subseção é utilizada para descrever a futura **calibração da demanda cognitiva**.

As duas dimensões inicialmente consideradas mais relevantes são:

* complexidade estrutural dos objetos;
* magnitude da transformação espacial.

Quando o sistema identificar dificuldade persistente, com combinação de erros e respostas significativamente demoradas em relação ao próprio histórico do participante, poderá apresentar estímulos estruturalmente mais simples e reduzir a exposição a rotações mais exigentes.

Não serão estabelecidos nesta versão limiares matemáticos.

Estudos com crianças mostram que características do estímulo e magnitude da rotação afetam substancialmente o desempenho; em uma amostra de 6 a 9 anos, por exemplo, rotações de 180° apresentaram maior dificuldade, e estímulos abstratos também mostraram efeitos distintos de estímulos mais concretos.

Isso sustenta a necessidade de calibração infantil, mas não define automaticamente quais valores deverão ser usados neste jogo.

---

## 6. EXPERIÊNCIA PRETENDIDA — PLAYER EXPERIENCE

### MDA: AESTHETICS

O framework MDA diferencia as regras e sistemas implementados das dinâmicas que emergem durante a interação e da experiência percebida pelo jogador.

Para este jogo, as dimensões mais relevantes são:

**Fantasy:** assumir responsabilidade sobre um reino em construção e acompanhar sua transformação.

**Discovery:** encontrar novos espaços, construções, atividades e habitantes ao longo das sessões.

**Expression:** influenciar o desenvolvimento do reino por meio de escolhas de construção e, futuramente, personalização.

**Challenge:** solucionar comparações visuoespaciais que permaneçam adequadas ao nível atual do jogador, sem pressão temporal explícita.

**Narrative:** reencontrar habitantes, acompanhar pequenas histórias e compreender por que determinada construção é necessária.

**Sensation:** observar um mundo progressivamente mais vivo, com mudanças ambientais, animações e uso das estruturas construídas.

A experiência pretendida é que a criança perceba que está ajudando o reino dela a crescer, e não estar realizando uma bateria de testes.

---

## 7. ELEMENTAL TETRAD

### 7.1. Mechanics — Regras e Sistemas

O loop principal é composto por apresentação de uma peça, consulta ao projeto, comparação mental, decisão e consequência no reino.

Mecânicas complementares incluem:

* construção progressiva;
* recursos e moedas;
* streak de acertos;
* exploração;
* escolha entre possíveis construções;
* desbloqueio de novas atividades;
* adaptação gradual de dificuldade.

**Restrições da população e do paradigma:**

* leitura não pode ser requisito para compreender a mecânica;
* cor não pode revelar a resposta experimental;
* interação motora deverá ser simples;
* não haverá cronômetro visível pressionando a criança;
* a peça não poderá ser livremente rotacionada durante o trial;
* a resposta não poderá depender da interpretação social de um personagem.

---

### 7.2. Story — Narrativa e Contexto

O jogador participa do desenvolvimento de uma pequena comunidade. Habitantes chegam com materiais e peças encontradas, fabricadas ou transportadas para as obras do reino.

Uma peça incorreta não significa necessariamente que o personagem está mentindo. A narrativa poderá explicar incompatibilidades por confusão, erro de fabricação, transporte ou semelhança entre estruturas.

Isso permite que personagens mantenham identidade e personalidade sem criar uma mecânica baseada em suspeita social.

**Restrições da população:**

A narrativa não deverá depender de leitura extensa, compreensão de ironia ou interpretação correta de expressões sociais para que a tarefa principal seja executada.

---

### 7.3. Aesthetics — Visual, Som e Sensação

O reino deverá ser visualmente convidativo e colorido, permitindo que construções e regiões apresentem identidade própria. Durante a comparação experimental, entretanto, o campo visual deverá se tornar mais controlado, reduzindo movimento e elementos competitivos. Uma ideia de identidade visual pode ser inspirada no jogo *Grow Island*, um jogo de navegador de 2007. Essa escolha vem de uma combinação estética muito amigável para crianças, já comprovada pelo jogo ser admirado por isso. Além disso, é um design muito simples para aplicação.

A cor poderá contribuir amplamente para a estética, mas não para identificar a resposta. Estudos infantis mostram que diferenças de cor entre alvo e distratores podem facilitar a discriminação em tarefas de Mental Rotation, alterando a dificuldade da tarefa.

O W3C também recomenda que cor não seja utilizada como único meio visual de transmitir informação.

O áudio deverá enriquecer o ambiente e o feedback, mas poderá ser reduzido ou desativado.

**Restrições da população:**

* contraste visual adequado;
* controle de volume;
* ausência de informação indispensável exclusivamente sonora;
* redução de estímulos simultâneos durante a tarefa;
* efeitos ambientais configuráveis quando possível.

---

### 7.4. Technology — Plataforma e Implementação

**Plataforma:** a definir.

**Alternativas atualmente consideradas:** desenvolvimento mobile, potencialmente com Flutter/Flame, ou implementação em Unity.

**Modo:** single player.

**Interação:** seleção discreta por interface, adaptada ao dispositivo final.

A tecnologia escolhida deverá ser compatível com o sistema de configuração e coleta de dados do CIATec e permitir registrar de forma consistente as condições apresentadas em cada interação.

**Restrições:**

* framework não deve ser escolhido antes da consolidação dos requisitos de acessibilidade e interação;
* tempos de resposta, caso utilizados cientificamente, dependerão de caracterização técnica da plataforma;
* configurações de acessibilidade que possam alterar a experiência experimental deverão ser identificáveis no registro de sessão.

---

## 8. MAPEAMENTO LM-GM

O modelo LM-GM propõe mapear objetivos de aprendizagem ou avaliação às mecânicas que efetivamente os operacionalizam, evitando que o conteúdo científico fique separado da experiência de jogo.

| Objetivo científico / educacional     | Mecânica de jogo                                     | Como operacionaliza                                                                         | Princípio     |
| ------------------------------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------- |
| Evocar transformação visuoespacial    | Comparação entre projeto e peça                      | O jogador precisa decidir se duas representações correspondem à mesma estrutura sob rotação | DP-01         |
| Evitar dependência de leitura         | Tutorial demonstrativo e interface pictográfica      | A regra pode ser aprendida observando exemplos e ações                                      | GP-01         |
| Reduzir interferência sensorial       | Configurações de áudio e foco visual durante o trial | Estímulos não essenciais podem ser reduzidos sem alterar a regra                            | GP-02 / GP-05 |
| Manter engajamento diante do erro     | Progressão sem perda acumulada                       | Erros encerram a streak, mas não destroem o progresso do reino                              | GP-03 / DP-04 |
| Ajustar demanda ao indivíduo          | Progressão adaptativa                                | Dificuldade pode diminuir diante de erros persistentes e respostas demoradas                | GP-04 / DP-06 |
| Sustentar motivação longitudinal      | Construção persistente                               | Trials contribuem para mudanças permanentes no mundo                                        | DP-05         |
| Favorecer autonomia                   | Escolha de construções e exploração                  | O jogador influencia o desenvolvimento do próprio reino                                     | DP-05         |
| Evitar demanda social não relacionada | Separação entre interação com NPC e comparação       | Personagem contextualiza a tarefa, mas não fornece a resposta                               | DP-03         |

---

## 9. PERSONAS E REQUISITOS DERIVADOS

As personas abaixo são perfis funcionais sintetizados a partir do PPI disponível. Como o PPI investigou outro jogo, elas são consideradas **personas contextuais provisórias** e deverão ser revisadas após testes específicos deste protótipo.

### 9.1. Persona 1 — Criança com maior autonomia digital

**Identificação funcional:** criança com TEA com boa autonomia em dispositivos digitais e capacidade de compreender regras simples após pouca ou nenhuma demonstração.

**Ciclo PPI de origem:** PPI TEA v1.0 — Fase 1.

**Contexto de uso:** no PPI original, participantes S1 utilizaram tecnologia com maior autonomia e compreenderam rapidamente a mecânica apresentada.

**Requisitos derivados:**

* não obrigar tutorial longo quando a criança já demonstra compreensão;
* oferecer acesso rápido ao gameplay;
* permitir aumento gradual de desafio sem retirar possibilidade de ajuste;
* manter personalização sensorial disponível mesmo para usuários autônomos.

**Guiding Principles relacionados:** GP-01, GP-02, GP-04.

**Impacto nas decisões:** Seções 4, 5, 10 e 11.

**Status de validação:** válida como perfil contextual do PPI; ainda não validada no jogo de Mental Rotation.

---

### 9.2. Persona 2 — Criança que se beneficia de instrução concreta e maior controle de frustração

**Identificação funcional:** criança com necessidade maior de demonstração visual e que pode apresentar frustração diante de dificuldade ou pontuação percebida como baixa.

**Ciclo PPI de origem:** PPI TEA v1.0 — Fase 1.

**Contexto de uso:** o PPI registrou recomendação de instrução visual mais concreta para o participante S2 e elevada competitividade/frustração com pontuação em uma sessão.
**Requisitos derivados:**

* tutorial demonstrativo disponível;
* feedback positivo e compreensível;
* evitar perda significativa de progresso após erro;
* possibilidade de diminuir a demanda quando a dificuldade estiver persistentemente elevada.

**Guiding Principles relacionados:** GP-01, GP-03, GP-04.

**Impacto nas decisões:** Seções 4, 5, 10 e 11.

**Status de validação:** válida como perfil contextual; requer avaliação específica neste jogo.

---

### 9.3. Persona 3 — Criança com necessidade elevada de suporte e redução de estímulos

**Identificação funcional:** criança que pode necessitar de maior mediação para compreender uma atividade nova e apresentar maior sensibilidade à complexidade da interação ou do ambiente.

**Ciclo PPI de origem:** PPI TEA v1.0 — Fase 1.

**Contexto de uso:** participantes S3 do PPI original necessitaram de mediação intensa. É importante ressaltar que parte dessa dificuldade estava diretamente associada à abstração da captura de movimento e, portanto, não pode ser automaticamente transferida para uma tarefa baseada em seleção simples.

**Requisitos derivados transferíveis:**

* fornecer demonstração clara antes da atividade;
* reduzir estímulos simultâneos durante o núcleo da tarefa;
* permitir interrupção e pausa sem penalização;
* manter configurações sensoriais acessíveis.

**Guiding Principles relacionados:** GP-01, GP-02, GP-05, GP-06.

**Impacto nas decisões:** Seções 4, 10 e 11.

**Status de validação:** válida apenas como perfil de referência contextual; a adequação deste jogo a participantes com necessidade elevada de suporte ainda precisa ser investigada.

---

## 10. INTERFACE E ACESSIBILIDADE

### 10.1. Princípios de Interface

A interface deverá procurar remover barreiras que não fazem parte do construto de Mental Rotation.

A compreensão da tarefa não deverá depender exclusivamente de leitura, áudio, cor ou precisão motora. Durante os trials, a interface deverá favorecer a percepção das estruturas que realmente precisam ser comparadas, enquanto elementos narrativos e ambientais assumem menor saliência.

Essa abordagem se aproxima dos princípios de UDL, que recomendam múltiplos meios de representação, e do design centrado no ser humano descrito pela ISO 9241-210:2019.

---

### 10.2. Requisitos de Acessibilidade por Domínio

**Visual:**

* contraste suficiente entre peças e fundo;
* objetos grandes o bastante para inspeção confortável;
* referência e candidato claramente identificáveis;
* ausência de cor como única informação necessária;
* redução de movimento e elementos competitivos durante a comparação;
* evitar detalhes locais que permitam solucionar a tarefa sem transformação mental.

Mental Rotation permanece, contudo, uma tarefa essencialmente visuoespacial. A versão atual não deverá ser apresentada como plenamente acessível a pessoas cegas; uma versão tátil ou baseada em outra modalidade exigiria investigação própria.

**Auditivo:**

* áudio não será indispensável;
* instruções importantes terão equivalente visual;
* volume poderá ser ajustado ou silenciado;
* efeitos sonoros funcionarão como complemento.

**Motor:**

* interação baseada em controles simples;
* áreas de seleção suficientemente grandes;
* ausência de necessidade de movimentos rápidos;
* ausência de arraste preciso, desenho ou manipulação motora fina como requisito para a decisão principal.

**Linguístico:**

* português simples;
* textos curtos;
* instruções apoiadas por demonstração;
* mecânica principal executável por criança ainda não plenamente alfabetizada.

**Social e cognitivo:**

Habitantes serão importantes para a identidade do mundo, mas nenhuma resposta dependerá de expressão facial, contato visual, emoção, direção do olhar, tom de voz ou percepção de mentira.

Meta-análise de estudos de eye-tracking encontrou diferenças médias na distribuição da atenção para estímulos sociais em participantes autistas, especialmente em cenas de maior conteúdo social, embora revisões também ressaltem que essas diferenças são dependentes do contexto e não universais.

Assim, a decisão não é remover pessoas do jogo, mas impedir que processamento social seja necessário para solucionar Mental Rotation.

**Cultural:**

Ainda não há evidência específica do PPI suficiente para definir requisitos culturais deste universo narrativo. Representação visual, linguagem, personagens e referências culturais deverão ser avaliados em ciclos posteriores.

---

### 10.3. Telas e Fluxo de Navegação

O fluxo conceitual principal é:

**Reino / vila**
↓
visualização do progresso e escolha de atividades

**Interação com habitante**
↓
apresentação breve da necessidade

**Grande Livro de Projetos / bancada**
↓
referência e peça candidata tornam-se o centro da interface

**Comparação e decisão**
↓
resposta do jogador

**Feedback**
↓
peça funciona ou não funciona; streak é mantida ou reiniciada

**Retorno ao reino**
↓
construção avança, recursos são atualizados e novas possibilidades podem surgir.

Wireframes e organização espacial das telas ainda serão produzidos em etapa posterior.

---

## 11. PARÂMETROS DE FASE E PROGRESSÃO

### 11.1. Variáveis de Fase

Nesta versão, as variáveis são descritas conceitualmente, sem valores quantitativos ainda não validados.

| Variável                        | Descrição e faixa atual                                                                      |
| ------------------------------- | -------------------------------------------------------------------------------------------- |
| **Complexidade estrutural**     | Graduação de estruturas mais simples a mais complexas; definição formal ainda pendente       |
| **Magnitude da rotação**        | Diferentes níveis de transformação espacial; valores exatos ainda serão definidos            |
| **Densidade visual do trial**   | Mantida baixa por padrão durante a comparação; elementos narrativos retornam após a resposta |
| **Feedback de desempenho**      | Acerto mantém/aumenta streak; erro encerra streak sem retirar progresso acumulado            |
| **Multiplicador de recompensa** | Cresce com sequência de acertos; valores ainda a definir                                     |
| **Configurações sensoriais**    | Volume e outros estímulos não essenciais deverão possuir possibilidade de ajuste             |
| **Duração da sessão**           | Ainda não definida; jogador terá possibilidade de pausa e saída                              |
| **Quantidade de trials**        | Ainda não definida                                                                           |

---

### 11.2. Critérios de Progressão, Regressão e Interrupção

| Evento                          | Critério conceitual atual                                                                                                                                                         |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Avanço de demanda**           | Desempenho consistentemente confortável, com boa acurácia e ausência de sinais de dificuldade prolongada. Critério quantitativo ainda a definir.                                  |
| **Manutenção**                  | Desempenho compatível com desafio adequado, sem evidência suficiente para aumentar ou reduzir a demanda.                                                                          |
| **Regressão de demanda**        | Erros recorrentes combinados a respostas muito demoradas poderão levar à redução da complexidade e à apresentação de rotações menos exigentes.                                    |
| **Interrupção voluntária**      | A criança poderá pausar ou encerrar a sessão quando desejar, sem perda de progresso.                                                                                              |
| **Interrupção por desconforto** | Em contextos supervisionados, sinais relevantes de desconforto ou desengajamento deverão justificar encerramento da atividade. Critérios formais dependem do protocolo posterior. |
| **Interrupção do protocolo**    | A definir no documento de protocolo/Doc 3.                                                                                                                                        |

Não haverá contagem regressiva visível exigindo respostas rápidas. Caso tempo de resposta seja utilizado como dado científico, será registrado sem transformar velocidade em uma obrigação explícita para o jogador.

---

### 11.3. Faixas de Fase por Perfil

Não serão estabelecidas faixas de dificuldade fixas com base somente em diagnóstico ou nível de suporte.

A criança não deverá receber automaticamente uma tarefa mais simples por possuir TEA, nem uma tarefa mais difícil por não possuir diagnóstico.

A futura calibração deverá utilizar o desempenho observado e necessidades funcionais. Informações de PPI poderão orientar configurações iniciais de acessibilidade, mas não devem ser tratadas como equivalentes a capacidade cognitiva individual.

---

## 12. REQUISITOS TÉCNICOS CONSOLIDADOS

| Domínio        | Requisito                                                                                   | Prioridade | Origem                    |
| -------------- | ------------------------------------------------------------------------------------------- | ---------- | ------------------------- |
| Funcional      | Permitir comparação entre estrutura de referência e peça apresentada                        | Crítica    | Paradigma / DP-01         |
| Funcional      | Impedir rotação livre do estímulo durante o trial                                           | Crítica    | DP-01                     |
| Funcional      | Implementar Grande Livro de Projetos como referência narrativa e funcional                 | Alta       | Decisão de design         |
| Funcional      | Permitir construção e persistência do reino                                                 | Alta       | DP-05                     |
| Funcional      | Construções devem desbloquear experiências ou modificações perceptíveis do mundo            | Alta       | DP-05                     |
| Feedback       | Implementar streak com bônus/multiplicador de pontos ou moedas                              | Média      | Decisão de design         |
| Feedback       | Erro reinicia streak sem retirar progresso acumulado                                        | Alta       | GP-03 / DP-04             |
| Acessibilidade | Onboarding não pode depender exclusivamente de leitura                                      | Alta       | GP-01                     |
| Acessibilidade | Informações essenciais não podem depender exclusivamente de áudio                           | Alta       | GP-02                     |
| Acessibilidade | Cor não pode determinar a resposta correta                                                  | Crítica    | DP-02 / WCAG              |
| Acessibilidade | Permitir controle de áudio                                                                  | Alta       | GP-02                     |
| Acessibilidade | Reduzir estímulos visuais simultâneos durante a tarefa                                      | Alta       | GP-05                     |
| Motor          | Resposta deve exigir interação simples e de baixa precisão                                  | Alta       | Decisão de acessibilidade |
| Social         | NPC não pode fornecer pistas sobre a resposta pela aparência ou comportamento               | Crítica    | DP-03                     |
| Progressão     | Adaptação de dificuldade não pode ser determinada apenas por diagnóstico                    | Crítica    | GP-04 / DP-06             |
| Progressão     | Erros persistentes e respostas demoradas devem permitir redução da demanda                  | Alta       | GP-03 / GP-04             |
| Autonomia      | Jogador deve poder pausar ou interromper sem perda de progresso                             | Alta       | GP-06                     |
| Científico     | Configurações que alteram a dificuldade devem ser identificáveis para futura análise        | Crítica    | Integridade científica    |
| Tecnológico    | Plataforma e framework devem permanecer independentes do SGDD até decisão técnica posterior | Média      | Decisão atual             |
| Científico     | Trials de treinamento devem ser distinguíveis dos trials utilizados para análise            | Alta       | Integridade científica    |

---
## 13. LACUNAS E DECISÕES PENDENTES

| Lacuna / Decisão pendente | Impacto | Ação necessária | Responsável |
| --- | --- | --- | --- |
| **Posição formal no Triple Diamond** | Campo obrigatório do GLIDE ainda incerto | Confirmar classificação com coordenação do framework | Pesquisador responsável / coordenação |
| **PPI específico do jogo de Mental Rotation** | PPI atual informa população, mas foi conduzido em outro jogo | Realizar ciclo específico com o protótipo | Equipe de pesquisa |
| **Plataforma final** | Afeta interface, desempenho e estratégia de distribuição | Comparar alternativas mobile/Flutter e Unity | Equipe de desenvolvimento |
| **Contexto de uso** | Afeta autonomia, supervisão e protocolo | Definir se uso prioritário será escolar, supervisionado, domiciliar ou híbrido | Coordenação científica |
| **Forma final dos estímulos** | Pode comprometer validade se permitir atalhos perceptivos | Desenvolver e testar conjunto infantil de estímulos | Pesquisador responsável / equipe científica |
| **Complexidade dos objetos** | Necessária para adaptação de dificuldade | Definir níveis após prototipagem e piloto | Equipe científica |
| **Magnitude das rotações** | Afeta diretamente a demanda cognitiva | Definir condições experimentais após revisão e piloto | Equipe científica |
| **Algoritmo de adaptação** | Progressão ainda é conceitual | Definir métricas, janelas de desempenho e limiares | Equipe científica / dados |
| **Duração das sessões** | Pode afetar fadiga, engajamento e quantidade de dados | Avaliar em piloto com crianças | Equipe científica |
| **Quantidade de trials** | Afeta confiabilidade e tolerabilidade | Definir no protocolo | Equipe científica |
| **Efeito do feedback explícito** | Pode provocar aprendizagem entre trials | Testar e definir estratégia final | Equipe científica |
| **Efeito da streak na frustração** | Pode incentivar engajamento ou aumentar competitividade | Avaliar em PPI/teste de protótipo | Equipe de pesquisa |
| **Validade da gamificação** | Gamificação pode modificar desempenho em Mental Rotation | Comparar com tarefa de referência em etapa posterior | Equipe científica |
| **Acessibilidade para deficiência visual severa** | Paradigma possui dependência visuoespacial intrínseca | Delimitar escopo e estudar alternativas, se aplicável | Coordenação científica |
| **Requisitos culturais** | Ainda não avaliados com usuários | Incorporar ao próximo PPI | Equipe de pesquisa |
| **Precisão temporal da plataforma** | Necessária caso RT seja usado cientificamente | Caracterizar após escolha tecnológica | Equipe de desenvolvimento |                 |

---

## 13A. HIPÓTESES PARA VALIDAÇÃO

Para preservar rastreabilidade, hipóteses derivadas do PPI utilizam **GP**, enquanto hipóteses específicas do novo jogo utilizam **DP**, evitando atribuir ao PPI decisões que ele não investigou.

| H-ID     | Hipótese                                                                                                                                                         | Princípio de origem | Será verificada no Doc 3 |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ------------------------ |
| **H-01** | O onboarding visual permitirá que a regra principal seja compreendida sem dependência de leitura extensa                                                         | GP-01               | Sim                      |
| **H-02** | Configurações de som e estímulos sensoriais permitirão acomodar preferências diferentes sem modificar o núcleo da tarefa                                         | GP-02               | Sim                      |
| **H-03** | Um sistema no qual o erro encerra apenas a streak, sem perda acumulada, reduzirá impacto negativo da falha sobre a experiência                                   | GP-03               | Sim                      |
| **H-04** | A adaptação baseada em desempenho observado será mais adequada à heterogeneidade dos usuários do que progressão fixa por diagnóstico                             | GP-04               | Sim                      |
| **H-05** | Reduzir elementos visuais não essenciais durante a comparação facilitará a manutenção do foco no estímulo relevante                                              | GP-05               | Sim                      |
| **H-06** | Permitir pausa e saída voluntárias favorecerá autonomia sem comprometer o retorno futuro ao jogo                                                                 | GP-06               | Sim                      |
| **H-07** | Impedir rotação manual durante o trial favorecerá a necessidade de transformação mental da peça                                                                  | DP-01               | Sim                      |
| **H-08** | Manter cor fora da lógica da resposta reduzirá pistas perceptivas alternativas e barreiras cromáticas                                                            | DP-02               | Sim                      |
| **H-09** | Retirar o personagem do foco durante a comparação reduzirá interferência social sem eliminar seu papel narrativo                                                 | DP-03               | Sim                      |
| **H-10** | Separar desempenho científico de progresso no reino permitirá que crianças com maior dificuldade continuem percebendo evolução significativa                     | DP-04               | Sim                      |
| **H-11** | Construções que desbloqueiam atividades e novas regiões sustentarão melhor o interesse longitudinal do que recompensas exclusivamente numéricas                  | DP-05               | Sim                      |
| **H-12** | O mesmo núcleo de jogo poderá atender crianças com diferentes perfis quando dificuldade, acessibilidade e personalização forem tratadas como dimensões distintas | DP-06               | Sim                      |

---

# REFERÊNCIAS TEÓRICAS DE APOIO

ARNAB, S.; LIM, T.; CARVALHO, M. B.; et al. **Mapping learning and game mechanics for serious games analysis.** *British Journal of Educational Technology*, v. 46, n. 2, p. 391–411, 2015. DOI: 10.1111/bjet.12113.

CAST. **CAST Universal Design for Learning Guidelines version 3.0.** Wakefield, MA: CAST, 2024.

CHITA-TEGMARK, M. **Social attention in ASD: A review and meta-analysis of eye-tracking studies.** *Research in Developmental Disabilities*, v. 48, p. 79–93, 2016. DOI: 10.1016/j.ridd.2015.10.011.

HUNICKE, R.; LEBLANC, M.; ZUBEK, R. **MDA: A Formal Approach to Game Design and Game Research.** AAAI Workshop on Challenges in Game AI, 2004.

IACHINI, T.; RUGGIERO, G.; BARTOLO, A.; RAPUANO, M.; RUOTOLO, F. **The Effect of Body-Related Stimuli on Mental Rotation in Children, Young and Elderly Adults.** *Scientific Reports*, 2019. DOI: 10.1038/s41598-018-37729-7.

ISO. **ISO 9241-210:2019 — Ergonomics of human-system interaction — Part 210: Human-centred design for interactive systems.** Geneva: International Organization for Standardization, 2019. Versão confirmada em 2025.

LÜTKE, N.; LANGE-KÜTTNER, C. **Keeping It in Three Dimensions: Measuring the Development of Mental Rotation in Children with the Rotated Colour Cube Test.** *International Journal of Developmental Science*, v. 9, n. 2, p. 95–114, 2015. DOI: 10.3233/DEV-14154.

MUTH, A.; HÖNEKOPP, J.; FALTER, C. M. **Visuo-spatial performance in autism: a meta-analysis.** *Journal of Autism and Developmental Disorders*, v. 44, n. 12, p. 3245–3263, 2014. DOI: 10.1007/s10803-014-2188-5.

PIERCE, K.; CONANT, D.; HAZIN, R.; STONER, R.; DESMOND, J. **Preference for geometric patterns early in life as a risk factor for autism.** *Archives of General Psychiatry*, v. 68, n. 1, p. 101–109, 2011. DOI: 10.1001/archgenpsychiatry.2010.113.

SHEPARD, R. N.; METZLER, J. **Mental Rotation of Three-Dimensional Objects.** *Science*, v. 171, n. 3972, p. 701–703, 1971. DOI: 10.1126/science.171.3972.701.

W3C. **Web Content Accessibility Guidelines — WCAG 2.2.** World Wide Web Consortium.

WEN, T. H.; CHENG, A.; ANDREASON, C.; et al. **Large scale validation of an early-age eye-tracking biomarker of an autism spectrum disorder subtype.** *Scientific Reports*, v. 12, 4253, 2022. DOI: 10.1038/s41598-022-08102-6.

ZAKRZEWSKI, S.; MERRILL, E.; YANG, Y. **Can gamification improve children's performance in mental rotation?** *Journal of Experimental Child Psychology*, v. 252, 106169, 2025. DOI: 10.1016/j.jecp.2024.106169.
