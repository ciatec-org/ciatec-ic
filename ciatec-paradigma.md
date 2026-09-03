# CIATEC Game Paradigm Pack

## Bateria de Avaliação Cognitiva Gamificada para Neurodivergência

## Objetivo

Este documento descreve o desenvolvimento de uma bateria de 20 jogos sérios fundamentados em paradigmas experimentais validados da psicologia cognitiva e neurociência, com foco na avaliação de perfis neurodivergentes. Cada jogo implementa ao menos um paradigma central com duas variáveis manipuláveis, permitindo a coleta sistemática de biomarcadores digitais cognitivos e motores.

A bateria tem como objetivo primário a identificação, classificação e mensuração de perfis cognitivos, com aplicação em contextos escolares, clínicos e domésticos, sem mediação obrigatória de profissional especializado na fase de coleta. A intenção subsequente de uso para intervenção terapêutica constitui uma segunda fase do projeto, não abordada neste documento.

Cada jogo é desenvolvido como um esqueleto de execução de mecânicas: recebe a configuração de nível estruturada pelo sistema research.ciatec.org, executa o gameplay conforme os parâmetros recebidos e devolve os dados brutos de telemetria para o backend. A lógica de avaliação, progressão adaptativa e geração de relatórios reside no servidor, não no cliente.

## Problema Científico e Hipótese Central

A avaliação cognitiva digital contemporânea enfrenta uma tensão estrutural não resolvida: instrumentos com alta fidelidade psicométrica tendem a produzir experiências de baixo engajamento, enquanto aplicações com alta jogabilidade frequentemente carecem de validade de construto ou de sensibilidade clínica. Baterias como o Cambridge Neuropsychological Test Automated Battery (CANTAB) e o NIH Toolbox Cognition Battery são metodologicamente robustas, mas operam como testes computadorizados com interface mínima, sem qualquer estrutura de jogo que sustente engajamento longitudinal em populações não clínicas.

O campo dos aplicativos de treino cognitivo comercial percorreu o caminho oposto: interfaces ricas, loops de progressão elaborados e retenção elevada, porém com evidências fracas ou contestadas de validade de construto e transferência para habilidades do mundo real.

A hipótese central deste projeto é que a tensão entre fidelidade psicométrica e jogabilidade não é irredutível, mas resulta de uma escolha de design equivocada: tratar o paradigma como conteúdo a ser apresentado dentro do jogo, em vez de tratá-lo como a própria mecânica do jogo. Quando a mecânica central de um jogo emerge diretamente da estrutura do paradigma experimental, e não é sobreposta a ela, é possível preservar os biomarcadores digitais de interesse sem sacrificar o engajamento do usuário.

Uma segunda hipótese derivada é que paradigmas de controle motor, como a Lei de Fitts e a Lei das Dois Terços, produzem biomarcadores de maior densidade informacional e menor suscetibilidade a estratégias conscientes de resposta do que paradigmas puramente decisionais, tornando-os especialmente valiosos em baterias voltadas a populações neurodivergentes.

## Stack Tecnológica

A bateria é desenvolvida sobre uma arquitetura de separação estrita entre lógica de avaliação e execução de gameplay. O jogo cliente não sabe o que está medindo: recebe uma configuração de nível, executa as mecânicas e devolve telemetria bruta. Toda a inteligência avaliativa reside no servidor. Isso garante que novos algoritmos de análise possam ser aplicados retroativamente ao dataset já coletado, sem exigir novas sessões.

**Clientes de jogo:** Unity para paradigmas que exigem captura cinemática contínua, renderização 3D e deployment web/desktop. Usa o ciatec-pose-server. Flutter com Flame para paradigmas baseados em eventos discretos e deployment mobile-first. A divisão reflete uma diferença de demanda de coleta: paradigmas motores como Fitts e Power Law requerem streaming de coordenadas acima de 60Hz, paradigmas decisionais operam satisfatoriamente com timestamps de evento.

**API:** FastAPI os endpoints de sessão, recepção de telemetria e geração de configurações de nível. A separação entre cliente e servidor é mediada inteiramente por esta camada, o que permite que diferentes clientes (Unity, Flutter, futuras interfaces web) consumam a mesma lógica avaliativa sem duplicação.

**Armazenamento:** PostgreSQL como banco relacional principal, com esquema orientado à telemetria de eventos temporais. Cada sessão gera um log de eventos brutos com timestamps em milissegundos, coordenadas de posição e metadados de tentativa. A granularidade do log é o evento individual, não o agregado por tentativa.

**Ontologia semântica:** A camada semântica é construída sobre RDF/OWL com serialização em Turtle, usando como vocabulários de referência BFO, PROV-O, FOAF, DCTERMS e Schema.org, alinhados ao framework FAIR (Findable, Accessible, Interoperable, Reusable). Os construtos cognitivos, paradigmas, variáveis e biomarcadores são organizados como entidades da ontologia com relações tipadas. Isso permite que o research.ciatec.org componha baterias dinamicamente por consultas SPARQL: por exemplo, todos os paradigmas que compartilham o construto de flexibilidade cognitiva podem ser agrupados e seus resultados cruzados automaticamente no perfil do usuário, sem acoplamento rígido entre cliente e lógica avaliativa. A ontologia é processada via rdflib e visualizada como grafo dirigido com NetworkX e PyVis.

**Servidor:** research.ciatec.org é o sistema central. Recebe a telemetria bruta via FastAPI, computa os biomarcadores, mantém a ontologia e administra a progressão adaptativa. O acesso ao modelo de linguagem para geração de relatórios e adaptação dinâmica é mediado por Graph-RAG ancorado em consultas SPARQL, o que restringe as respostas do modelo ao grafo semântico construído e elimina alucinações clínicas. A interface de visualização de perfis, relatórios e administração da bateria é construída em React com componentes Shadcn/ui, consumindo os endpoints FastAPI diretamente.

## Acessibilidade e Design Inclusivo

A bateria é desenvolvida sob três frameworks complementares, aplicados em diferentes camadas do sistema. O UDL orienta decisões relacionadas à interação, representação e engajamento; o HCD estrutura o processo de desenvolvimento e avaliação com usuários; e as diretrizes W3C orientam os requisitos técnicos de acessibilidade das interfaces digitais.

**Universal Design for Learning (UDL):** O framework UDL do CAST organiza o design em torno de três princípios: múltiplos meios de representação, múltiplos meios de ação e expressão e múltiplos meios de engajamento. Na bateria, esses princípios orientam a oferta de alternativas de interação e resposta, a apresentação multimodal de instruções e feedback e a possibilidade de adaptação da experiência às diferentes necessidades dos participantes. A versão atual do framework é a **UDL Guidelines 3.0**, lançada pelo CAST em 2024. ([UDL Guidelines][1])

**Referências:**

- [https://udlguidelines.cast.org](https://udlguidelines.cast.org)
- [https://doi.org/10.1080/20473869.2021.1900505](https://doi.org/10.1080/20473869.2021.1900505)
- [https://doi.org/10.1080/17483107.2026.2676788](https://doi.org/10.1080/17483107.2026.2676788)

**Human-Centred Design (HCD):** O desenvolvimento segue os princípios da ISO 9241-210:2019, que estabelece requisitos e recomendações para princípios e atividades de design centrado no ser humano ao longo do ciclo de vida de sistemas interativos. A participação de usuários com diferentes perfis funcionais é incorporada ao processo de avaliação, permitindo identificar barreiras de interação que não podem ser previstas exclusivamente por inspeção técnica ou avaliação com usuários típicos. ([ISO][2])

**Referências:**

- [https://www.iso.org/standard/77520.html](https://www.iso.org/standard/77520.html)
- [https://doi.org/10.3389/fresc.2023.1238158](https://doi.org/10.3389/fresc.2023.1238158)
- [https://doi.org/10.1080/10447318.2022.2163568](https://doi.org/10.1080/10447318.2022.2163568)

**W3C Accessibility:** As WCAG 2.2 orientam a acessibilidade das interfaces web da plataforma, incluindo o research.ciatec.org e aplicações web associadas. A WCAG2ICT fornece orientação para a aplicação dos princípios e critérios WCAG 2.2 a software não-web, sendo relevante para clientes desenvolvidos em Unity e Flutter. A WCAG 3.0 permanece como Working Draft e será acompanhada como referência para futuras decisões de acessibilidade, sem substituir atualmente as WCAG 2.2 como referência principal. ([W3C][3])

**Referências:**

- [https://www.w3.org/TR/WCAG22/](https://www.w3.org/TR/WCAG22/)
- [https://www.w3.org/TR/wcag2ict-22/](https://www.w3.org/TR/wcag2ict-22/)
- [https://www.w3.org/WAI/standards-guidelines/wcag/wcag3-intro/](https://www.w3.org/WAI/standards-guidelines/wcag/wcag3-intro/)
- [https://doi.org/10.1007/s10209-023-00967-2](https://doi.org/10.1007/s10209-023-00967-2)

**Game Accessibility Guidelines:** Como complemento às diretrizes gerais de acessibilidade digital, o Game Accessibility Guidelines fornece recomendações específicas para jogos, organizadas em níveis básico, intermediário e avançado. Para a bateria, essas recomendações podem orientar requisitos relacionados à acessibilidade cognitiva, motora, visual e auditiva, especialmente nos paradigmas que apresentam maior demanda atencional ou de memória. Embora não exista uma base sistemática equivalente que valide especificamente essas guidelines em populações neurodivergentes, revisões sistemáticas sobre intervenções baseadas em jogos oferecem evidências relevantes sobre sua aplicação em populações com transtornos do neurodesenvolvimento.

**Referências:**

- [https://gameaccessibilityguidelines.com](https://gameaccessibilityguidelines.com)
- [https://doi.org/10.3389/fped.2025.1498563](https://doi.org/10.3389/fped.2025.1498563)
- [https://pubmed.ncbi.nlm.nih.gov/36597046/](https://pubmed.ncbi.nlm.nih.gov/36597046/)

## Atrito entre Psicometria e Jogabilidade: Análise por Paradigma

A análise a seguir examina, para cada paradigma, onde reside a tensão entre preservar o construto científico e produzir uma experiência de jogo genuína. O grau de atrito não é fixo: é uma função das decisões de design. O objetivo desta seção é tornar explícitas essas decisões para que possam ser tomadas de forma informada.

### 1. Simple Reaction Time (SRT)

**Construto:** velocidade de resposta sensório-motora. Um estímulo aparece e o participante deve responder o mais rapidamente possível. As principais medidas são tempo de reação médio, variabilidade intraindividual, distribuição dos tempos e ocorrência de respostas antecipadas.

**Variáveis para o jogo:**

- V1: modalidade do estímulo (visual, auditivo, audiovisual)
- V2: incerteza temporal (intervalos fixos vs. intervalos aleatórios entre estímulos)

**Atrito psicometria-jogabilidade:** baixo. A mecânica de reagir a um estímulo é intrinsecamente simples e não exige wrapper conceitual complexo. O risco está no sentido oposto: o paradigma é simples demais para sustentar engajamento prolongado sem progressão narrativa ou variação de contexto. A solução está no envelope do jogo, não na mecânica. A variabilidade intraindividual (IIV) é um biomarcador sensível para TDAH e deve ser preservada: intervalos fixos entre estímulos permitem que o usuário antecipe e reduzem a variabilidade artificialmente. Intervalos aleatórios são metodologicamente preferíveis.

**Referência:**

- Kahveci, S. et al. (2025). Reaction-time task reliability is more accurately computed with permutation-based split-half correlations than with Cronbach's alpha. https://doi.org/10.3758/s13423-024-02597-y
- Loushy Kay, T. et al. (2025). A novel reaction time assessment in virtual reality: Advantages over computerized tests. https://doi.org/10.3758/s13428-025-02752-w
- Mritunjay, Singh & Kashyap (2025). Assessment Tools for Evaluating Reaction Time: A Comprehensive Review of Methods and Applications. https://doi.org/10.7860/JCDR/2025/80478.21715

### 2. Choice Reaction Time (CRT)

**Construto:** velocidade de processamento e seleção de resposta. O participante recebe diferentes estímulos e precisa selecionar a resposta correspondente a cada um deles, exigindo identificação, seleção e execução.

**Variáveis para o jogo:**

- V1: número de alternativas de resposta (2, 4 ou 8 opções)
- V2: compatibilidade estímulo-resposta (mapeamento natural vs. arbitrário)

**Atrito psicometria-jogabilidade:** baixo a médio. A estrutura de escolha entre alternativas é um componente natural de jogos. O risco está na compatibilidade estímulo-resposta: mapeamentos naturais (apertar à esquerda para estímulo à esquerda) produzem RTs menores e menos variabilidade do que mapeamentos arbitrários. Se o design visual priorizar clareza e intuitividade, pode inadvertidamente tornar o mapeamento mais natural do que o pretendido, reduzindo a sensibilidade da medida.

**Referência:**

- Ferreira et al. (2024). Validity and reliability of a ruler drop test to measure dual-task reaction time, choice reaction time and discrimination reaction time. https://doi.org/10.1007/s40520-024-02726-6
- Loushy Kay et al. (2025). A novel reaction time assessment in virtual reality: Advantages over computerized tests. https://doi.org/10.3758/s13428-025-02752-w
- Gazzanigo et al. (2025). Cellphone separation modulates the effects of working memory load on ex-Gaussian parameters of choice reaction time. https://doi.org/10.1186/s41235-025-00684-9

### 3. Go/No-Go Task

**Construto:** controle inibitório prepotente. O participante deve responder rapidamente aos estímulos Go e inibir a resposta diante dos estímulos No-Go. As medidas centrais são erros de comissão, erros de omissão, tempo de reação e acurácia.

**Variáveis para o jogo:**

- V1: frequência dos estímulos No-Go (10%, 25% ou 50% das tentativas)
- V2: natureza do estímulo (neutro vs. emocionalmente saliente)

**Atrito psicometria-jogabilidade:** baixo. A regra simples de agir ou inibir é facilmente integrável a qualquer tema de jogo. O atrito central está na frequência dos No-Go: aumentar a proporção de No-Go para tornar o jogo mais desafiante muda fundamentalmente o que está sendo medido. Com 50% de No-Go, o paradigma mede discriminação e não mais inibição prepotente. A frequência baixa de No-Go (10 a 25%) é a que preserva o construto, mas exige que o jogo sustente atenção em longos períodos de resposta Go repetitiva, o que é um desafio de design legítimo.

**Referência:**

- Aziz-Safaie et al. (2024). The effect of task complexity on the neural network for response inhibition: An ALE meta-analysis. https://doi.org/10.1016/j.neubiorev.2024.105544
- Zhang et al. (2024). Dissociation of prepotent response inhibition and interference control in problematic internet use: evidence from the Go/No-Go and Flanker tasks. https://doi.org/10.1186/s40359-024-01698-6
- The influence of emotional stimuli on response inhibition: a systematic review in non-clinical adults (2025). https://doi.org/10.3389/fpsyg.2025.1577486

### 4. Stroop Task

**Construto:** processamento de conflito e controle cognitivo. O participante deve responder a uma dimensão relevante do estímulo ignorando uma dimensão automática e conflitante. O Stroop effect, medido pela diferença entre condições congruentes e incongruentes em RT e erros, é a variável de interesse.

**Variáveis para o jogo:**

- V1: tipo de conflito (cor/palavra clássico, numérico, emocional, espacial)
- V2: proporção de tentativas incongruentes (predominância congruente vs. predominância incongruente)

**Atrito psicometria-jogabilidade:** alto. O Stroop clássico depende de leitura, o que exclui parte do público neurodivergente de interesse, especialmente pessoas com dislexia. Variantes que não dependem de leitura existem, mas cada uma mede um construto parcialmente diferente. A decisão sobre qual variante usar precisa preceder o design. A proporção de tentativas incongruentes afeta o efeito de forma significativa (efeito de proporção de congruência, PCP) e deve ser mantida constante entre usuários para comparabilidade.

**Referência:**

- Müller et al. (2025). Not All Stroop-Type Tasks Are Alike: Assessing the Impact of Stimulus Material, Task Design, and Cognitive Demand via Meta-analyses Across Neuroimaging Studies. https://doi.org/10.1007/s11065-024-09647-1
- Cipriani et al. (2025). Executive control from healthy ageing to cognitive impairment: A systematic review of stroop and simon effects using psychophysiological and imaging techniques. https://doi.org/10.1016/j.neubiorev.2025.106121
- Vasta, Mulatti & Treccani (2026). A qualitative systematic review of individual differences in Stroop task performance among healthy adults. https://doi.org/10.1007/s00426-025-02224-y

### 5. Eriksen Flanker Task

**Construto:** atenção seletiva e controle de interferência. O participante deve responder ao estímulo-alvo ignorando distratores adjacentes que podem ser congruentes ou incongruentes. O Flanker Effect é a diferença de RT e erros entre condições.

**Variáveis para o jogo:**

- V1: distância espacial entre alvo e distratores
- V2: valência dos distratores (neutros, congruentes, incongruentes)

**Atrito psicometria-jogabilidade:** médio. O Flanker depende de layout espacial preciso. O distrator deve estar próximo o suficiente para produzir interferência, mas a definição de "próximo" não é arbitrária e tem parâmetros estabelecidos na literatura. Jogos que movem, animam ou variam dinamicamente os distratores podem destruir o efeito ou introduzir variância não controlada. O desafio de design é criar variação visual interessante sem alterar as propriedades espaciais que definem o construto.

**Referência:**

- Mittelstädt et al. (2025). Under pressure in the Eriksen flanker task. https://doi.org/10.1016/j.biopsycho.2025.108986
- Dignath et al. (2025). Dynamic modulation of spatial selection: Online and anticipatory adjustments in the flanker task. https://doi.org/10.3758/s13414-025-03026-5
- Strommer, Okon-Singer & Gabay (2024). The subcortical role in executive functions: Neural mechanisms of executive inhibition in the flanker task. https://doi.org/10.3758/s13415-024-01215-7

### 6. Simon Task

**Construto:** controle de interferência e seleção de resposta. O participante deve responder a uma característica relevante do estímulo ignorando sua localização espacial. O Simon Effect emerge da incompatibilidade entre a localização do estímulo e o lado da resposta requerida.

**Variáveis para o jogo:**

- V1: tipo de conflito espacial (horizontal, vertical, profundidade)
- V2: compatibilidade da sequência de tentativas (efeito de sequência de congruência, CSE)

**Atrito psicometria-jogabilidade:** médio a alto. O Simon é o paradigma mais sensível à manipulação de layout. O efeito depende especificamente da relação entre a posição do estímulo e o lado da resposta: qualquer redesign visual que altere essa relação espacial altera o que está sendo medido. Jogos que introduzem movimento do estímulo, perspectiva isométrica ou layouts não cartesianos precisam mapear cuidadosamente como a posição do estímulo se traduz na percepção de localização pelo usuário.

**Referência:**

- Pastötter et al. (2024). The interplay of cognitive control and feature integration: insights from theta oscillatory dynamics during conflict processing. https://doi.org/10.1093/cercor/bhae326
- Velasquez et al. (2024). Music training is related to late ERP modulation and enhanced performance during Simon task but not Stroop task. https://doi.org/10.3389/fnhum.2024.1384179
- Spatiotemporal dynamics of mouse tracking reveal general and selective control mechanisms of the congruency sequence effect in Simon tasks (2025). https://doi.org/10.1016/j.cognition.2025.106259

### 7. Psychomotor Vigilance Task (PVT)

**Construto:** vigilância sustentada e alerta. Um estímulo aparece em intervalos imprevisíveis e o participante deve responder o mais rapidamente possível. As medidas principais são RT, variabilidade, lapses (respostas lentas acima de 500ms) e falsos inícios.

**Variáveis para o jogo:**

- V1: duração da sessão (versões de 3, 10 e 20 minutos com diferentes curvas de decaimento)
- V2: custo de falso início (ausência de penalidade vs. penalidade progressiva)

**Atrito psicometria-jogabilidade:** médio. O PVT é paradoxalmente o paradigma mais simples em termos de mecânica e um dos mais difíceis de gamificar genuinamente. Sua força como instrumento vem exatamente da sua monotonia: é a degradação do desempenho ao longo do tempo que revela o perfil de vigilância. Qualquer elemento de design que reduza a monotonia, como variações estéticas, narrativa progressiva ou feedback frequente, pode mascarar a curva de decaimento que é o biomarcador central. A tensão aqui é entre manter a sensibilidade ao decaimento e sustentar engajamento suficiente para que o usuário complete a sessão.

**Referência:**

- Vigilance Decrement: Its First 75 Years (2025). https://doi.org/10.3389/fcogn.2025.1632885
- Bistable stochastic model quantifies performance degradation during sleep deprivation (2025). https://doi.org/10.1093/sleep/zsaf205
- Forecasting psychomotor vigilance test performance from facial videos (2025). https://doi.org/10.1093/sleep/zsaf220

### 8. N-Back Task

**Construto:** memória de trabalho, especificamente os processos de manutenção, atualização e controle atencional. O participante recebe uma sequência contínua de estímulos e deve indicar se o estímulo atual corresponde ao apresentado N posições antes.

**Variáveis para o jogo:**

- V1: nível de N (1-back, 2-back, 3-back, com ajuste adaptativo)
- V2: modalidade do estímulo (visuoespacial, auditivo, dual)

**Atrito psicometria-jogabilidade:** muito alto. O N-Back é o paradigma com maior tensão nesta bateria. A mecânica exige que o usuário mantenha uma janela temporal ativa na memória enquanto processa estímulos novos: qualquer elemento de jogo que distribua a atenção para além dessa janela contamina a medida. Tentativas de gamificação existentes, como os aplicativos de Dual N-Back, são funcionalmente testes com interface visual melhorada, não jogos. O desafio de design é encontrar um envelope narrativo que seja suficientemente presente para motivar sem ser suficientemente saliente para desviar o processamento da janela N. Uma abordagem promissora é usar o contexto do N-Back como mecânica de controle de um personagem (o N determina qual ação tomar), tornando a janela temporal funcionalmente relevante dentro do mundo do jogo.

**Referência:**

- Huang et al. (2025). Exploring the n-back task: insights, applications, and future directions. https://doi.org/10.3389/fnhum.2025.1721330
- Ni & Ma (2024). A computational approach to the N-back task. https://doi.org/10.1038/s41598-024-80537-5
- Byrne et al. (2024). Evidence for separate backward recall and n-back working memory factors: a large-scale latent variable analysis. https://doi.org/10.1080/09658211.2024.2393388

### 9. Continuous Performance Task (CPT)

**Construto:** atenção sustentada. Uma sequência contínua de estímulos é apresentada e o participante deve responder aos alvos e inibir respostas aos não-alvos. Permite observar degradação do desempenho ao longo do tempo com telemetria rica: RT, variabilidade, omissões, comissões, sensibilidade (d') e viés de resposta.

**Variáveis para o jogo:**

- V1: razão alvo/não-alvo (frequência de alvos: 10%, 25%, 50%)
- V2: duração e estrutura temporal da sessão (blocos fixos vs. sessão contínua com variação de ritmo)

**Atrito psicometria-jogabilidade:** médio. O CPT compartilha com o PVT o problema da monotonia necessária: a degradação ao longo do tempo é o sinal de interesse, e reduzir a monotonia comprime o sinal. No entanto, o CPT tem mais graus de liberdade de design que o PVT, pois a natureza dos estímulos alvo e não-alvo pode ser tematizada sem alterar a estrutura da tarefa. O risco principal é que elementos visuais salientes associados a alvos criem uma distinção que não depende da atenção sustentada, mas de saliência perceptual, o que altera o construto sendo medido.

**Referência:**

- MacKay-Brandt et al. (2025). cpCST: a new continuous performance test for high-precision assessment of attention across the lifespan. https://doi.org/10.3389/fpsyg.2025.1640417
- Shelat, Schooler & Giesbrecht (2024). Predicting attentional lapses using response time speed in continuous performance tasks. https://doi.org/10.3389/fcogn.2024.1460349
- Sustained attention can be measured using a brief computerized attention task (2024). https://doi.org/10.1038/s41598-024-68093-4

### 10. Task-Switching Paradigm

**Construto:** flexibilidade cognitiva. O participante alterna entre duas ou mais regras conforme uma pista. O switch cost, aumento de RT e erros nas tentativas de mudança em relação às tentativas de repetição, é o indicador central.

**Variáveis para o jogo:**

- V1: previsibilidade da alternância (sequência alternada vs. sequência aleatória)
- V2: intervalo de preparação entre pista e estímulo (curto: 100ms, longo: 1000ms)

**Atrito psicometria-jogabilidade:** médio. O Task-Switching tem boa gamificabilidade porque a alternância de regras é um componente natural de muitos jogos. O risco está na previsibilidade: tornar a alternância surpresa demais para criar tensão narrativa prejudica a separação entre switch cost e custo de reorientação atencional inespecífico. O intervalo de preparação entre pista e estímulo é uma variável metodologicamente importante que não pode ser eliminada em nome de ritmo mais acelerado.

**Referência:**

- Radović et al. (2025). Cognitive flexibility in aging: the impact of age range and task difficulty on local switch costs in task switching. https://doi.org/10.3389/fnagi.2025.1619441
- Viviani et al. (2025). Exploring semantic and executive flexibility interplay in task switching. https://doi.org/10.1038/s41598-025-09639-y
- Geddert et al. (2025). Modeling of control over task-switching and cross-task interference supports a two-dimensional model of cognitive stability and flexibility. https://doi.org/10.3758/s13423-025-02712-7

### 11. Wisconsin Card Sorting Test (WCST)

**Construto:** flexibilidade cognitiva, formação de conceitos e descoberta de regras. O participante infere uma regra implícita a partir do feedback e precisa abandoná-la quando ela muda sem aviso. As medidas incluem erros perseverativos, categorias completadas, eficiência na mudança de regra e erros totais.

**Variáveis para o jogo:**

- V1: número de dimensões de classificação disponíveis (2, 3 ou 4 dimensões)
- V2: sinal da mudança de regra (sem aviso vs. com sinal ambiental implícito)

**Atrito psicometria-jogabilidade:** baixo. O WCST é o paradigma com maior fit natural para gamificação nesta bateria, e ao mesmo tempo o mais negligenciado em jogos sérios existentes. Sua estrutura já é um loop de jogo: descobrir uma regra, dominá-la, perceber que ela mudou, descobrir a nova. Isso mapeia diretamente para mecânicas de progressão e desbloqueio. A diferença crítica em relação ao Task-Switching é que a regra precisa ser descoberta, não apenas seguida, o que adiciona um componente de inferência indutiva que é cognitivamente mais rico e narrativamente mais interessante. O risco está na introdução de feedback excessivamente explícito: se o design clarifica demais por que a resposta estava errada, reduz a demanda de inferência que define o construto.

**Referência:**

- Alotaibi et al. (2025). Preliminary psychometric evaluation of the online Wisconsin Card Sorting Inspired Test (WCSIT). https://doi.org/10.1016/j.actpsy.2025.105514
- Granato et al. (2025). Assessing executive functions and metacognition: translational potential of the Metacognitive Wisconsin Card Sorting Test for developmental neuropsychology. https://doi.org/10.3389/fnbeh.2025.1655310
- Zhang & Ye (2025). Bridging Species Differences in Rule Switching: How Humans and Monkeys Solve the Same Wisconsin Card Sorting Task. https://doi.org/10.1523/JNEUROSCI.2288-24.2025

### 12. Tower of London

**Construto:** planejamento e resolução de problemas. O participante precisa transformar uma configuração inicial em uma configuração-alvo seguindo regras específicas, utilizando o menor número possível de movimentos. Versões computadorizadas permitem medir separadamente tempo de planejamento, tempo de execução, sequência de decisões e erros.

**Variáveis para o jogo:**

- V1: profundidade mínima de planejamento necessária (2 a 7 movimentos)
- V2: presença ou ausência de limite de tempo por movimento

**Atrito psicometria-jogabilidade:** baixo. Jogos de puzzle são uma categoria estabelecida com alta retenção natural. O Tower of London já é estruturalmente um puzzle, o que torna a gamificação relativamente direta. O risco está na distinção entre planejamento e execução: jogos de puzzle tipicamente não registram o tempo que o usuário passa observando antes de agir, mas esse intervalo de planejamento pré-execução é uma das medidas mais informativas do paradigma. A arquitetura de coleta de dados precisa capturar o momento em que o usuário inicia o primeiro movimento, não apenas quando completa o problema.

**Referência:**

- Schumacher et al. (2025). A novel index to measure pre-planning in the Tower of London task: Test-retest reliability and known-group validity. https://doi.org/10.1111/bjop.70044
- Kavanaugh et al. (2025). The Tower of London task in children and adolescents with neuropsychiatric disorders. https://doi.org/10.1080/09297049.2024.2360224
- Ventura, Fogel & Northoff (2025). From Planning to Execution: Temporal Signatures of Cognitive and Motor Processes in the Tower of Hanoi Task. https://doi.org/10.48550/arXiv.2510.XXXXX

### 13. Serial Reaction Time Task (SRTT)

**Construto:** aprendizagem implícita e memória procedural. O participante responde repetidamente a estímulos que seguem uma sequência regular sem saber que existe estrutura previsível. A aprendizagem é inferida pela redução progressiva do RT para sequências regulares em comparação com sequências aleatórias.

**Variáveis para o jogo:**

- V1: comprimento e estrutura da sequência (sequências de 6, 10 ou 12 elementos com diferentes estruturas de repetição)
- V2: consciência explícita induzida (condição ingênua vs. condição com dica pós-bloco sobre existência de sequência)

**Atrito psicometria-jogabilidade:** muito baixo. O SRTT é o paradigma mais naturalmente gamificável desta bateria e ao mesmo tempo o mais negligenciado em baterias existentes. A razão é contraintuitiva: o que o SRTT mede é implícito, o usuário não sabe que está aprendendo uma sequência. Isso significa que é possível construir um jogo completo, com narrativa, estética e progressão, enquanto o paradigma opera de forma invisível por baixo da experiência. O biomarcador emerge da curva de RT sem que o usuário precise saber o que está sendo avaliado. Isso é metodologicamente vantajoso e narrativamente libertador. O único cuidado é garantir que o design não introduza regularidades adicionais que possam ser aprendidas paralelamente à sequência experimental.

**Referência:**

- Barth, Stahl & Haider (2025). How Implicit Sequence Learning and Explicit Sequence Knowledge Are Expressed in a Serial Response Time Task. https://doi.org/10.5334/joc.439
- Oliveira, Hayiou-Thomas & Henderson (2024). Reliability of the serial reaction time task: If at first you don't succeed, try, try, try again. https://doi.org/10.1177/17470218241232347
- Broeckelmann, Martin & Glazebrook (2025). Auditory Cues and Feedback in the Serial Reaction Time Task: Evidence for Sequence Acquisition and Sensory Transfer. https://doi.org/10.1080/00222895.2024.2448130

### 14. Probabilistic Reversal Learning (PRL)

**Construto:** aprendizagem por reforço, tomada de decisão e flexibilidade cognitiva. O participante escolhe entre alternativas com diferentes probabilidades de recompensa; após aprender qual opção é mais vantajosa, as contingências mudam sem aviso. As medidas incluem número de reversões, perseveração, win-stay/lose-shift e parâmetros de modelos computacionais de aprendizagem.

**Variáveis para o jogo:**

- V1: probabilidade de recompensa da opção vantajosa (70%, 80% ou 90%)
- V2: critério de reversão (número fixo de tentativas vs. critério baseado em desempenho)

**Atrito psicometria-jogabilidade:** baixo. O PRL é estruturalmente próximo de mecânicas de jogos de exploração e coleta de recursos. A incerteza probabilística é um componente natural de jogos, e a reversão de contingências mapeia para eventos de mundo que mudam as regras sem aviso. O risco está na transparência das contingências: se o design torna muito evidente quando uma reversão ocorreu, o usuário pode perceber o padrão e responder estrategicamente, o que reduz a validade do perfil de aprendizagem capturado.

**Referência:**

- MacDonald et al. (2025). Computational Modeling of Reversal Learning Impairments in Schizophrenia and Bipolar Disorder Reveals Shared Failure to Exploit Rewards. https://doi.org/10.1037/abn0000944
- Koloski et al. (2025). Beta and High Gamma Oscillations in the Cortico-striatal Network Reflect Reward Certainty on a Probabilistic Reversal Learning Task. https://doi.org/10.1523/JNEUROSCI.0858-25.2025
- Griffin et al. (2024). Distinct alterations in probabilistic reversal learning across at-risk mental state, first episode psychosis and persistent schizophrenia. https://doi.org/10.1038/s41598-024-68004-7

### 15. Iowa Gambling Task (IGT)

**Construto:** tomada de decisão sob incerteza e risco. O participante escolhe repetidamente entre alternativas com diferentes combinações de recompensas e perdas, algumas vantajosas a longo prazo e outras desvantajosas. O paradigma avalia aprendizagem por feedback, sensibilidade a recompensa e punição, preferência por risco e evolução das estratégias ao longo do tempo.

**Variáveis para o jogo:**

- V1: transparência das contingências (opacas vs. parcialmente sinalizadas pelo ambiente)
- V2: tipo de feedback (imediato vs. diferido em tempo)

**Atrito psicometria-jogabilidade:** baixo. O IGT é literalmente um jogo de escolha de cartas com ganhos e perdas, o que torna a gamificação quase trivial do ponto de vista estrutural. O risco está no sentido oposto: tornar as contingências narrativamente muito explícitas pode eliminar a ambiguidade que define o construto. Um personagem que visivelmente parece confiável ou suspeito introduz pistas externas que não estavam no paradigma original e que podem alterar o perfil decisional registrado.

**Referência:**

- Latibeaudiere, Butler & Owens (2025). Decision-making and performance in the Iowa Gambling Task: recent ERP findings and clinical implications. https://doi.org/10.3389/fpsyg.2025.1492471
- Zanini, Picano & Spitoni (2025). The Iowa Gambling Task: Men and Women Perform Differently. A Meta-analysis. https://doi.org/10.1007/s11065-024-09637-3
- Salice, Antonietti & Colautti (2024). The effect of transcranial Direct Current Stimulation on the Iowa Gambling Task: a scoping review. https://doi.org/10.3389/fpsyg.2024.1454796

### 16. Delay Discounting / Intertemporal Choice

**Construto:** tomada de decisão intertemporal. A pessoa escolhe entre uma recompensa menor disponível imediatamente e uma recompensa maior disponível após um atraso. A medida central é o parâmetro k, que representa o grau de desvalorização da recompensa com o tempo. Maiores valores de k indicam maior impulsividade intertemporal.

**Variáveis para o jogo:**

- V1: domínio da recompensa (recursos do jogo, itens colecionáveis, moeda narrativa)
- V2: estrutura dos atrasos (hiperbólica vs. exponencial, com atrasos de minutos a dias reais)

**Atrito psicometria-jogabilidade:** baixo. A troca de dinheiro real por recompensas do jogo é metodologicamente viável e amplamente usada em pesquisa experimental com adolescentes. O risco está no valor percebido das recompensas: o parâmetro k depende de que o usuário perceba as recompensas como genuinamente valiosas. Recompensas dentro de um jogo podem não ativar os mesmos sistemas de valoração que recompensas reais, o que exige calibração cuidadosa do design econômico do jogo. O uso de atrasos reais (horas ou dias) em vez de atrasos hipotéticos é metodologicamente mais robusto, mas exige que o jogo sustente engajamento entre sessões.

**Referência:**

- Gelino et al. (2024). A systematic review and meta-analysis of test-retest reliability and stability of delay and probability discounting. https://doi.org/10.1002/jeab.910
- Macías-Navarrete & dos Santos (2024). Effects of delay sequence in a delay discounting task. https://doi.org/10.1016/j.beproc.2024.105046
- Domínguez Rojas & Velo Higueras (2025). Delay discounting and anxiety: a systematic review on current evidence for clinical and non-clinical population. https://doi.org/10.3389/fpsyg.2025.1645442

### 17. Spatial Navigation Task (Morris Water Maze Virtual)

**Construto:** aprendizagem espacial e memória espacial. O participante aprende a localizar um objetivo em um ambiente usando pistas espaciais. As medidas incluem distância percorrida, eficiência da trajetória, tempo até o objetivo, erros e estratégia de navegação.

**Variáveis para o jogo:**

- V1: tipo de pistas disponíveis (alocêntricas vs. egocêntricas vs. mistas)
- V2: presença do objetivo durante testes de memória (visível vs. ausente, forçando recordação)

**Atrito psicometria-jogabilidade:** baixo a médio. Jogos de exploração de ambientes são uma categoria com alta retenção. O Morris Water Maze virtual é quase indistinguível de um jogo de exploração, o que o torna um dos paradigmas mais facilmente gamificáveis desta bateria. O risco está na padronização do ambiente: variações estéticas no cenário podem introduzir pistas adicionais não controladas que facilitam ou dificultam a navegação de forma não intencional. O ambiente precisa ser controlado em termos de número, posição e saliência das pistas, mesmo sendo visualmente elaborado.

**Referência:**

- Thornberry et al. (2026). Virtual Morris Water Task: Procedures and Protocols for the Assessment of Spatial Navigation and Memory. https://doi.org/10.1002/cpph.70011
- Zaitoon et al. (2025). The virtual Morris water maze for cognitive function assessment in adolescents with type 1 diabetes. https://doi.org/10.1007/s00125-025-06598-x
- Age- and sex-related differences in landmark recall following a virtual spatial navigation task (2025). https://doi.org/10.3389/fnagi.2025.1602945

### 18. Mental Rotation Task (Shepard-Metzler)

**Construto:** cognição espacial e transformação visuoespacial. O participante determina se dois objetos são iguais ou diferentes após imaginar a rotação de um deles. O indicador principal é a relação entre ângulo de rotação e tempo de resposta, classicamente linear.

**Variáveis para o jogo:**

- V1: ângulo de rotação (0°, 60°, 120°, 180°)
- V2: complexidade do objeto (figuras 2D simples vs. estruturas 3D compostas)

**Atrito psicometria-jogabilidade:** médio. A tarefa de rotação mental tem um fit natural com jogos de puzzle e manipulação de objetos. O risco está na introdução de estratégias analíticas não rotacionais: usuários mais experientes com jogos 3D podem aprender a comparar features locais dos objetos em vez de realizar a rotação mental, o que altera o processo cognitivo sendo avaliado sem alterar a acurácia. O design precisa usar objetos que resistam a estratégias de comparação local, o que é um problema metodológico já documentado na literatura.

**Referência:**

- Negen (2025). Mental rotation, perspective taking, and performance profiling. https://doi.org/10.1007/s10339-025-01269-6
- Dong et al. (2025). Long-term cognitive and neurophysiological effects of mental rotation training. https://doi.org/10.1038/s41539-025-00309-2
- Arnold et al. (2025). Mental rotation is a weak measure of people's propensity to visualise. https://doi.org/10.1016/j.concog.2025.103907

### 19. Visual Search Task

**Construto:** atenção visual seletiva. O participante localiza um alvo entre distratores. A dificuldade é manipulada pelo número de elementos, similaridade entre alvo e distratores e tipo de busca. As medidas principais são tempo de busca, acurácia e relação entre RT e número de distratores (slope).

**Variáveis para o jogo:**

- V1: tipo de busca (pop-out por feature simples vs. busca conjuntiva por combinação de features)
- V2: número de distratores (tamanho do display: 4, 8, 16 ou 24 elementos)

**Atrito psicometria-jogabilidade:** baixo. Jogos de busca visual, como encontrar um elemento escondido em uma cena, são uma mecânica familiar com alta acessibilidade. O paradigma de busca visual se integra naturalmente a contextos de exploração, coleta e identificação que são comuns em jogos. O risco está na introdução de heterogeneidade visual não controlada: em um ambiente de jogo rico, distratores podem variar em saliência por razões narrativas ou estéticas independentes das variáveis experimentais, contaminando a relação entre número de distratores e RT que define o slope de busca.

**Referência:**

- Godwin et al. (2025). A sharing practices review of the visual search and eye movements literature reveals recommendations for our field and others. https://doi.org/10.3758/s13428-025-02759-3
- Sherman, Clarke & Hughes (2025). Designing a test battery for real-world visual search. https://doi.org/10.1038/s41598-025-23111-x
- Becker, Hamblin-Frohman & Amarasekera (2025). Visual search is relational without prior context learning. https://doi.org/10.1016/j.cognition.2025.106132

### 20. Controle Visuomotor: Lei de Fitts e Lei das Dois Terços

**Construto:** controle visuomotor, cinemática do movimento e compromisso velocidade-precisão. A Lei de Fitts descreve a relação entre tempo de movimento, tamanho do alvo e distância até ele. A Lei das Dois Terços descreve a relação entre velocidade e curvatura durante movimentos contínuos: quanto maior a curvatura, menor a velocidade. O conjunto permite avaliar tanto a eficiência de aquisição de alvos quanto a organização cinemática da trajetória.

**Variáveis para o jogo:**

- V1: índice de dificuldade de Fitts (manipulação sistemática de tamanho do alvo e distância de movimento)
- V2: tipo de trajetória requerida (linear vs. curvilínea, com diferentes perfis de curvatura)

**Atrito psicometria-jogabilidade:** muito baixo, com uma ressalva técnica importante.

Do ponto de vista da mecânica, qualquer jogo que use toque, mouse ou stylus e exija mover o cursor ou o dedo até um alvo já executa o paradigma de Fitts. Jogos de traçar trajetórias já geram dados da Lei das Dois Terços. O usuário está jogando e o paradigma opera de forma invisível, o que representa o menor grau de atrito desta bateria.

A ressalva técnica é que o biomarcador não é um número por tentativa, mas uma série temporal contínua. A captura de coordenadas de posição, velocidade e aceleração em alta frequência (idealmente acima de 60Hz) exige uma infraestrutura de coleta diferente da usada para registrar timestamps de clique. A análise da Power Law especificamente requer atenção metodológica na estimativa dos parâmetros, pois filtragem inadequada do sinal e escolhas de regressão podem produzir estimativas enviesadas, conforme documentado pela literatura recente.

A relevância clínica para neurodivergência é direta e subestimada. O trabalho de Fourie et al. (2025) demonstra que o perfil cinemático em pessoas autistas é estruturalmente diferente, não apenas mais lento: o desvio da Lei das Dois Terços funciona como um biomarcador motor do TEA independente de velocidade geral. Para TDAH, a variabilidade intraindividual da cinemática é candidata a biomarcador mais robusta que o RT isolado. A combinação de Fitts e Power Law representa o paradigma com maior densidade informacional por unidade de tempo de coleta desta bateria, e o único que acessa biomarcadores motores além de biomarcadores decisionais.

**Referência:**

- Fraser, Di Luca & Cook (2025). Biological kinematics: a detailed review of the velocity-curvature power law calculation. https://doi.org/10.1007/s00221-025-07065-0
- Fourie et al. (2025). Motor Control Adherence to the Two-thirds Power Law Differs in Autistic Development. https://doi.org/10.1007/s10803-024-06240-6
- Hornbæk, Kristensson & Oulasvirta (2025). Motor control. https://doi.org/10.1093/oso/9780192864543.003.0004

## Nota sobre Validade e Limitações

Este documento não implica que os jogos descritos sejam equivalentes às versões clínicas dos paradigmas que os fundamentam. A gamificação introduz inevitavelmente variáveis de confusão relacionadas ao engajamento, experiência prévia com jogos e resposta a recompensas virtuais que não estão presentes nas versões laboratoriais. O objetivo desta bateria é produzir biomarcadores digitais com validade de construto suficiente para identificação e classificação de perfis cognitivos em contextos ecológicos, não substituir avaliações neuropsicológicas completas conduzidas por profissionais.

A validação de cada jogo como instrumento de medida requer estudos de validade convergente com as versões clínicas dos paradigmas, estudos de confiabilidade teste-reteste e estudos de sensibilidade em populações com diagnósticos confirmados. Essa agenda de validação constitui uma etapa subsequente ao desenvolvimento descrito neste documento.

*CIATEC, research.ciatec.org*

*Documento de trabalho para iniciação científica e financiamento. Versão 0.1*
