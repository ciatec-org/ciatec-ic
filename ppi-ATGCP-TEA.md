# Relatório de Patient and Public Involvement (PPI)

## Desenvolvimento de Jogo Terapêutico Digital para Transtorno do Espectro Autista (TEA)

Versão 1.0. Documento de acesso público.

| Campo | Conteúdo |
| --- | --- |
| Protocolo | Desenvolvimento de jogo digital terapêutico, fase de co-design e levantamento de requisitos |
| Condição de saúde | Transtorno do Espectro Autista (TEA) |
| Fase do projeto | Fase 1, co-design: definição de requisitos funcionais, sensoriais, de segurança e de progressão |
| Data do PPI | Abril a maio de 2026 |
| Elaborado por | Equipe de pesquisa. Dados coletados por profissional de saúde e pesquisador |
| Referência metodológica | GRIPP2 (Guidance for Reporting Involvement of Patients and the Public); NIHR PPI Framework; Person-Based Approach (Yardley et al., 2015) |

## Contextualização

### Demanda por jogos terapêuticos digitais no contexto do TEA

O Transtorno do Espectro Autista (TEA) é uma condição do neurodesenvolvimento caracterizada por padrões atípicos de comunicação social, comportamentos repetitivos e variações sensoriais que afetam o engajamento com o ambiente e com outras pessoas. A prevalência global estimada é de aproximadamente 1 em cada 100 crianças, com crescimento substancial nos registros diagnósticos nas últimas duas décadas, em parte reflexo de maior sensibilidade diagnóstica e ampliação dos critérios clínicos (WHO, 2023).

No Brasil, dados recentes indicam que o número de crianças com diagnóstico de TEA registradas em serviços públicos de saúde cresceu significativamente após a aprovação da Lei Berenice Piana (Lei nº 12.764/2012), que garantiu direitos específicos a pessoas com TEA. Apesar disso, o acesso a intervenções terapêuticas especializadas permanece desigual, com concentração nos centros urbanos e marcada escassez em municípios de pequeno e médio porte.

Nesse contexto, jogos digitais terapêuticos emergem como uma alternativa promissora para ampliar o acesso a intervenções estruturadas. Diferentemente de materiais clínicos convencionais, jogos digitais podem ser configurados para diferentes níveis de complexidade, oferecem feedback imediato e consistente, permitem registro automático de desempenho e podem ser utilizados em contextos clínicos e domiciliares. Para crianças com TEA especificamente, a familiaridade com dispositivos digitais, especialmente tablets e smartphones, e a tendência ao hiperfoco em interfaces interativas representam pontos de adesão potencialmente superiores aos de atividades terapêuticas tradicionais.

### Jogos com captura de movimento: potencial e desafios para o TEA

Jogos que utilizam captura de movimento corporal, nos quais o participante interage com a interface por meio de gestos, deslocamentos ou movimentos de membros, sem necessidade de toque direto na tela, apresentam características funcionais relevantes para objetivos terapêuticos como coordenação motora, atenção compartilhada, planejamento motor e integração visuomotora.

Para populações com TEA, esse formato introduz, simultaneamente, uma oportunidade e um desafio. A oportunidade reside na possibilidade de engajar o sistema motor de forma global, diferentemente do uso passivo de tablets, que concentra a interação nos dedos e na visão, estimulando movimentos de membros superiores, controle postural e resposta a estímulos visuais dinâmicos. O desafio reside na abstração inerente à tarefa: compreender que o computador "vê" o movimento sem contato físico exige uma capacidade de representação visuomotora que pode não estar consolidada em todos os perfis funcionais do espectro.

Essa tensão entre potencial terapêutico e barreira de abstração é central para o design de jogos com captura de movimento destinados a crianças com TEA. Ela implica que os requisitos funcionais, sensoriais e de onboarding variam substancialmente conforme o nível de suporte do participante, e que um jogo eficaz para o espectro não pode ser uniforme: precisa ser configurável, progressivo e clinicamente ancorado em dados reais de uso.

### Patient and Public Involvement (PPI) como base para o design

O Patient and Public Involvement (PPI) é uma abordagem metodológica que posiciona pacientes, cuidadores e público como parceiros ativos no processo de desenvolvimento de intervenções de saúde, não como sujeitos passivos de pesquisa, mas como informantes privilegiados de decisões de design. No contexto de jogos terapêuticos digitais, o PPI permite que requisitos funcionais, sensoriais e clínicos sejam derivados de dados reais de interação, em vez de pressuposições técnicas sobre o que o usuário precisa ou tolera.

Este relatório documenta um ciclo de PPI conduzido na fase de co-design de um jogo terapêutico digital com captura de movimento, destinado a crianças com TEA. O processo envolveu usuários finais com diferentes níveis de suporte, profissionais clínicos e cuidadores, e teve como objetivo central converter a perspectiva dos participantes em requisitos técnicos objetivos, orientando decisões sobre interface, progressão, parâmetros sensoriais, segurança e monitoramento clínico.

### Nota metodológica: níveis de suporte no TEA

O DSM-5 e a CID-11 classificam o TEA em três níveis de suporte, que descrevem a intensidade de apoio necessária para o funcionamento cotidiano:

- **Nível 1 (Suporte Pontual):** Dificuldades de comunicação social perceptíveis sem suporte, mas com capacidade de comunicação funcional. Comportamentos inflexíveis causam interferência mínima com apoio.
- **Nível 2 (Suporte Substancial):** Déficits marcados de comunicação verbal e não verbal. Inflexibilidade comportamental e dificuldades de adaptação frequentes, mesmo com suporte.
- **Nível 3 (Suporte Extenso):** Déficits severos de comunicação funcional. Grande dificuldade de adaptação a mudanças. Comportamentos interferem substancialmente no funcionamento em todas as áreas.

Os dados deste PPI cobrem participantes de Suporte 1, 2 e 3, com ênfase nos perfis 1 e 2 como população-alvo principal do design. O Suporte 3 está representado como perfil de ancoragem, delimitando os limites do design genérico e os requisitos de adaptação severa.

## 1. Finalidade do PPI

Este ciclo de Patient and Public Involvement (PPI) foi conduzido na fase inicial de desenvolvimento de um jogo terapêutico digital com captura de movimento corporal, destinado a crianças com Transtorno do Espectro Autista (TEA). O jogo utiliza câmera de computador para rastrear os movimentos dos membros superiores do participante, que interage com elementos visuais na tela sem necessidade de toque direto.

O PPI foi realizado antes da definição dos parâmetros matemáticos de progressão do jogo, especificamente antes da parametrização formal de velocidade dos alvos, tamanho dos elementos, duração das fases, critérios de avanço entre níveis e configurações sensoriais. Seu objetivo foi garantir que essas variáveis fossem definidas com base em evidências reais de como usuários com TEA interagem com esse tipo de interface, e não apenas em pressuposições técnicas ou clínicas.

O PPI pretendeu informar decisões sobre:

- Tempo máximo por fase e tolerância à duração da atividade por nível de suporte
- Velocidade e tamanho dos alvos visuais, calibração por perfil funcional
- Requisitos de onboarding: o que o jogo precisa comunicar antes e durante a primeira interação
- Parâmetros sensoriais: resposta ao feedback auditivo, preferências visuais, tolerância a estímulos simultâneos
- Critérios de progressão entre fases e gestão da frustração diante do aumento de dificuldade
- Sinais de interrupção clínica por nível de suporte, quando parar a atividade
- Nível de suporte físico e verbal necessário por perfil
- Viabilidade de uso domiciliar e requisitos de infraestrutura

A escolha pelo PPI como abordagem metodológica reflete o reconhecimento de que crianças com TEA não constituem um grupo homogêneo: as diferenças funcionais entre os níveis de suporte são suficientemente marcantes para que parâmetros adequados para um perfil sejam inapropriados ou inatingíveis para outro. O PPI foi, portanto, estruturado de forma a capturar essa heterogeneidade e convertê-la em requisitos técnicos diferenciados por perfil funcional.

## 2. Quem foi envolvido

O processo envolveu três categorias de participantes: usuários finais com TEA (crianças com diagnóstico confirmado), profissionais clínicos com experiência direta no atendimento terapêutico dessa população, e cuidadores (familiares). Os participantes foram recrutados em contexto de atendimento clínico especializado em TEA.

Para preservar a privacidade dos participantes e de seus responsáveis, todos os indivíduos são identificados por código ao longo deste documento. Dados clínicos são apresentados de forma agregada ou com nível de detalhe suficiente para orientar decisões de design, sem permitir identificação individual.

### Usuários finais, Suporte 1

| Código | Perfil demográfico | Diagnóstico adicional | Perfil tecnológico | Forma de participação |
| --- | --- | --- | --- | --- |
| U1-S1 | Feminino, 9 anos | TEA S1 | Usa tablet no cotidiano. Abriu e iniciou o jogo de forma autônoma. | Sessão de jogo e entrevista semiestruturada. |
| U2-S1 | Masculino, 5 anos | TEA S1 | Contato com computador via aulas de informática escolar. Não usa tablet no cotidiano. | Sessão de jogo e entrevista semiestruturada. |
| U3-S1 | Masculino, 8 anos | TEA S1 + TDAH + TOD | Usa tablet no cotidiano. Boa autonomia digital. | Sessão de jogo e entrevista semiestruturada. |

### Usuários finais, Suporte 2

| Código | Perfil demográfico | Diagnóstico adicional | Perfil tecnológico | Forma de participação |
| --- | --- | --- | --- | --- |
| U4-S2 | Masculino, cerca de 8 anos | TEA S2, verbal | Usa tablet com jogos de corrida (hiperfoco). Sem computador em casa. | Sessão de jogo observada. Dados complementados via cuidador (C1). |

### Usuários finais, Suporte 3 (perfil de ancoragem)

| Código | Perfil demográfico | Diagnóstico adicional | Perfil tecnológico | Forma de participação |
| --- | --- | --- | --- | --- |
| U5-S3 | Masculino, cerca de 8 anos | TEA S3 | Usa tablet para CAA e YouTube. Marcha independente com alterações de equilíbrio e coordenação. | Sessão de jogo com mediação clínica intensa. Dados via terapeuta responsável e observação. |
| U6-S3 | Masculino, 10 anos | TEA S3 + síndrome genética (hipotonia global, atraso motor) | Usa tablet para YouTube. Marcha independente com limitações funcionais e necessidade de suporte postural. | Sessão de jogo com mediação clínica intensa. Dados via terapeuta responsável e observação. |

### Profissionais clínicos

| Código | Área | Vínculo com usuário | Forma de participação |
| --- | --- | --- | --- |
| PC-A | Psicologia (ABA) | Terapeuta responsável por U5-S3 | Entrevista estruturada completa. Referência clínica para perfil S3. |
| PC-B | Pedagogia / Atendimento Terapêutico | Acompanhante de U4-S2 na sessão | Entrevista semiestruturada. Contribuições sobre uso do corpo inteiro e estratégias pedagógicas. |

### Cuidadores

| Código | Relação | Contexto familiar | Forma de participação |
| --- | --- | --- | --- |
| C1 | Mãe | Mãe de U4-S2 e de outra criança com TEA. Sem computador em casa, uso de tablet. | Entrevista semiestruturada completa. Foco em uso domiciliar e barreiras práticas. |

## 3. Diversidade e representatividade

**Condição de saúde:** TEA, diagnóstico confirmado (DSM-5 ou CID-11) para todos os usuários finais.

**Níveis de suporte:**

- Suporte 1: U1-S1, U2-S1, U3-S1. Dados primários robustos. Perfil-alvo principal do design.
- Suporte 2: U4-S2. Dados de sessão observada e entrevista com cuidador e profissional. Suporte secundário do design.
- Suporte 3: U5-S3, U6-S3. Dados clínicos detalhados via terapeuta e observação. Perfil de ancoragem, delimita limites do design genérico.

**Faixa etária:** 5 a 10 anos (usuários finais). Adultos: profissional clínico e cuidador.

**Comorbidades relevantes:**

- U3-S1: TDAH e Transtorno Opositivo Desafiador. Impacta tolerância à frustração e autorregulação.
- U6-S3: Síndrome genética com hipotonia global e atraso motor. Impacta postura, força e planejamento motor.

**Perfil tecnológico:** Todos os usuários finais têm contato prévio com algum dispositivo digital (tablet, computador ou eletrônicos educacionais). Diferença relevante: usuários S1 têm maior autonomia digital; usuários S3 dependem de mediação para qualquer interação com tecnologia nova.

**Limitações de representatividade:**

- Suporte 2: representado por um único participante, sem entrevista direta. Dados complementados por cuidador e observação.
- Suporte 3: dados sem interação autônoma com o jogo. Toda a participação ocorreu com mediação clínica intensa.
- Ausência de participantes de contexto exclusivamente domiciliar sem vínculo com serviço especializado.
- Faixa etária restrita a 5 a 10 anos. Requisitos podem diferir para adolescentes com TEA.

**Implicação para o design:** Os dados deste PPI são suficientemente robustos para orientar decisões de design para os perfis S1 e S2. Para S3, os dados delimitam com clareza os requisitos mínimos de adaptação e as barreiras que tornam o design genérico inaplicável sem modificações substanciais. O documento não recomenda um design único para todos os perfis. Recomenda um design configurável com parâmetros distintos por nível de suporte.

## 4. Etapa do processo em que o PPI ocorreu

O PPI foi conduzido na Fase 1 do projeto, antes da parametrização formal das variáveis do jogo e da definição dos critérios matemáticos de progressão entre fases. Esta etapa corresponde ao co-design inicial: o momento em que decisões estruturais sobre o funcionamento do jogo ainda estão em aberto e podem ser moldadas pela perspectiva dos usuários.

A escolha por realizar o PPI nesta fase, e não após o desenvolvimento de um protótipo mais consolidado, reflete o princípio metodológico de que é mais eficiente e eticamente mais coerente incorporar a perspectiva do usuário antes de decisões técnicas serem tomadas, do que corrigir um produto já desenvolvido. No contexto do TEA, essa escolha é especialmente relevante: as diferenças funcionais entre os níveis de suporte são suficientemente marcantes para que um jogo calibrado sem dados reais de interação possa ser inadequado para a maioria dos usuários pretendidos.

**Decisões diretamente informadas por este PPI:**

- Velocidade inicial e progressão de velocidade dos alvos, por nível de suporte
- Tamanho dos alvos visuais, configuração inicial e critérios de redução progressiva
- Duração máxima por fase, limites de tolerabilidade por perfil funcional
- Requisitos de onboarding, o que o jogo precisa comunicar antes e durante a primeira interação
- Configurações sensoriais, resposta ao som, preferência de fundo, quantidade de estímulos simultâneos
- Critérios de progressão entre fases, indicadores de prontidão e gestão da frustração
- Sinais de interrupção clínica, por nível de suporte
- Nível de suporte físico e verbal necessário por perfil, impacto no design de uso autônomo versus mediado
- Viabilidade de uso domiciliar, requisitos de infraestrutura e autonomia

As decisões listadas acima correspondem a parâmetros que, no contexto de jogos terapêuticos com captura de movimento, costumam ser definidos de forma arbitrária ou com base em dados de populações sem TEA. Este PPI fornece a base empírica para que essas definições sejam clinicamente fundamentadas e diferenciadas por perfil funcional.

**O que este PPI não pretendeu informar:**

- Eficácia terapêutica do jogo. Esta etapa é anterior a qualquer ensaio clínico.
- Validação de paradigmas cognitivos ou motores. O PPI informa o design, não valida o instrumento.
- Generalizações para outros diagnósticos. Os dados são específicos para TEA.

Estas questões serão objeto de fases subsequentes do projeto, após o desenvolvimento do jogo com base nos requisitos aqui levantados.

## 5. Método de contribuição

### 5.1 Formato geral

O PPI foi conduzido por meio de sessões individuais semiestruturadas, combinando demonstração prática do jogo com entrevista guiada. Cada sessão seguiu uma estrutura em dois momentos: (1) exposição ao jogo, o participante assistiu à demonstração e, quando possível, interagiu com o jogo; (2) coleta de dados, por meio de entrevista com perguntas abertas seguidas de perguntas específicas, cobrindo os eixos temáticos definidos no roteiro.

Para usuários com TEA de Suporte 3, a sessão foi adaptada: a interação com o jogo ocorreu com mediação clínica intensa, e os dados foram coletados predominantemente por observação estruturada e entrevista com o profissional responsável, em vez de entrevista direta com a criança. Para usuários de Suporte 1, a entrevista foi conduzida diretamente com a criança, com linguagem adaptada à faixa etária.

### 5.2 Estrutura da sessão

| Momento | Conteúdo | Duração estimada |
| --- | --- | --- |
| 1. Acolhimento e contexto | Apresentação do objetivo da sessão. Explicação de que o jogo é um protótipo e que a opinião do participante ajudará a melhorá-lo. | 5 min |
| 2. Perfil de uso de tecnologia | Perguntas abertas sobre experiência prévia com dispositivos digitais, jogos e aplicativos. | 5 a 10 min |
| 3. Demonstração do jogo | O jogo é demonstrado pelo facilitador antes de qualquer pergunta sobre ele. Para S1: participante joga em seguida. Para S3: participante observa e tenta com mediação. | 10 a 15 min |
| 4. Reação à demonstração | Perguntas estruturadas sobre compreensão da tarefa, sons, alvos, cores/contraste, animações. Reações espontâneas registradas pelo facilitador. | 15 a 20 min |
| 5. Bloco específico por perfil | Para profissionais clínicos e cuidadores: perguntas sobre efeitos na prática clínica, sinais de interrupção, indicadores de progresso, uso domiciliar. | 10 a 15 min |
| 6. Priorização final | "Quais três aspectos você considera mais importantes de ajustar ou aprimorar?" Respostas livres, sem sugestão. | 5 min |

### 5.3 Roteiro temático

O roteiro seguiu quatro eixos temáticos, adaptados ao perfil de cada participante:

| Eixo | Tópicos cobertos | Aplicado a |
| --- | --- | --- |
| 1. Requisitos Funcionais | Compreensão da tarefa; onboarding; progressão de dificuldade; fases e níveis; duração; postura durante o jogo; protocolo de ensino para novos usuários. | Todos os participantes |
| 2. Requisitos Sensoriais | Sons e música: papel, conforto, controle; cores dos alvos e fundo de tela; contraste; animações; elementos visuais simultâneos; feedback visual. | Todos os participantes |
| 3. Segurança e Interrupção | Sinais de desconforto; critérios de interrupção da atividade; nível de apoio necessário (físico e verbal); postura obrigatória por perfil. | Profissionais clínicos e cuidadores (S3 via PC-A; S2 via C1 e PC-B) |
| 4. Contexto de Uso | Uso domiciliar: infraestrutura, supervisão necessária, rotina; uso institucional: integração com a terapia, função como reforçador; barreiras práticas. | Cuidadores e profissionais clínicos |

### 5.4 Modalidade e registro

| Campo | Conteúdo |
| --- | --- |
| Modalidade | Presencial, contexto de atendimento clínico especializado em TEA. |
| Período de coleta | Abril a maio de 2026. Duas rodadas de coleta conduzidas por facilitadores distintos (pesquisador e profissional de saúde), com roteiro comum. |
| Duração média das sessões | 30 a 45 minutos por participante. Sessões com S3 tiveram duração mais variável devido à necessidade de adaptação contínua. |
| Registro | Áudio com transcrição automática (revisada manualmente); diário de campo narrativo por sessão; registro estruturado por participante com blocos temáticos e observações clínicas (para sessões conduzidas pelo profissional de saúde). |
| Facilitação | Dois facilitadores independentes, pesquisador e profissional de saúde (terapeuta ocupacional). Ambos utilizaram o mesmo roteiro temático. Sem observador externo independente, reconhecida como limitação metodológica deste ciclo. |
| Demonstração do jogo | O jogo foi demonstrado em todos os casos antes das perguntas sobre ele. Para S1, o participante jogou ativamente. Para S3, a interação ocorreu com auxílio físico e verbal da terapeuta responsável. |

### 5.5 Intercorrências registradas

**Falhas técnicas:** Em duas sessões, a câmera do computador apresentou defeito durante a demonstração, impedindo a captura de movimentos. Nessas sessões, o jogo foi demonstrado por vídeo e as perguntas foram mantidas. As respostas dessas sessões foram analisadas com a ressalva de que o participante não interagiu ativamente com o jogo.

**Interrupção de sessão:** Em uma sessão (U4-S2), a atividade foi interrompida pela terapeuta responsável antes da etapa de entrevista. Os dados foram complementados por entrevista posterior com o cuidador (C1) e com a profissional presente (PC-B).

**Travamento do sistema:** Em algumas sessões da primeira rodada de coleta, o jogo apresentou lentidão por limitação de hardware. O fato foi informado aos participantes antes do início, e as respostas sobre ritmo e velocidade dessas sessões foram interpretadas com cautela.

Essas intercorrências não inviabilizaram a coleta, mas devem ser consideradas ao interpretar respostas sobre ritmo, velocidade e compreensão da dinâmica do jogo nas sessões afetadas.

## 6. Principais temas identificados

Esta seção apresenta os temas emergentes das sessões de PPI, organizados nos quatro eixos definidos no roteiro. Para cada tema, são apresentados: o padrão identificado, a evidência que o sustenta (incluindo citações diretas quando disponíveis), os participantes que o originaram, e divergências quando presentes. Os temas são diferenciados por nível de suporte quando os dados indicam diferenças funcionalmente relevantes entre os perfis.

**Convenção de leitura desta seção:**

- S1, S2, S3: nível de suporte do participante
- Citações em itálico: fala direta ou paráfrase próxima do participante ou profissional
- Padrão convergente: identificado por dois ou mais participantes independentes
- Divergência: variação relevante entre participantes, registrada sem resolução

As observações clínicas do profissional de saúde (TO) que conduziu sessões com S3 são tratadas como dado primário de segunda camada. Não substituem a fala dos usuários, mas complementam e contextualizam os dados de observação.

### Eixo 1. Requisitos funcionais

#### 1.1 Compreensão da mecânica de captura de movimento

**Suporte 1. Padrão convergente: compreensão rápida e autônoma.**

Os três participantes S1 compreenderam a dinâmica do jogo sem necessidade de explicações repetidas. Todos perceberam espontaneamente a progressão de dificuldade, identificando que os alvos ficavam menores e mais rápidos ao longo das fases.

> "Compreendeu rapidamente o objetivo da tarefa e conseguiu iniciar o jogo sem necessidade de muitas explicações adicionais." Profissional de saúde, observação de U1-S1, U2-S1 e U3-S1

> "As bolinhas ficaram menores e mais rápidas." Percepção espontânea, relatada por U1-S1, U2-S1 e U3-S1 de forma independente

**Suporte 3. Padrão convergente: abstração como barreira central.**

Ambos os participantes S3 não compreenderam que o computador captura o movimento sem necessidade de toque na tela. Em diversas tentativas, aproximavam-se fisicamente do monitor para encostar nos alvos. A dificuldade não era motora, era de representação: compreender a relação entre o movimento do corpo e o efeito na tela.

> "O jogo pareceu abstrato para ele, que frequentemente tentava tocar diretamente nas bolinhas exibidas na tela ao invés de realizar o movimento corporal solicitado pela atividade." Profissional de saúde, U5-S3

> "A principal barreira é a falta de familiaridade com movimentos abstratos. Como o paciente está acostumado com o toque direto em tablets e celulares, ele não entende inicialmente como o computador 'vê' sua mão sem o contato físico com a tela." PC-A, sobre U5-S3

> "Em diversos momentos, realizava movimentos de braço sem direcionamento funcional apenas após comandos verbais, sem necessariamente compreender a finalidade da ação." Profissional de saúde, U6-S3

#### 1.2 Onboarding e protocolo de ensino

**S1:** Tutorial simples ou ausente é suficiente. Nenhum dos participantes S1 reportou dificuldade para iniciar o jogo. U1-S1 abriu e iniciou o jogo de forma completamente autônoma, sem instrução. Para U2-S1 e U3-S1, uma demonstração breve foi suficiente.

**S2:** Tutorial visual é recomendável. O cuidador C1 indicou que U4-S2 poderia ter dificuldade com a tela inicial, especialmente se os comandos não fossem visuais e concretos.

> "Uma explicação prévia com desenho. Às vezes tem jogos que antes mostram como fazer, né? Mas assim, dependendo do jogo, algo mais simples eles já conseguem." C1, sobre U4-S2

**S3:** Protocolo de ensino estruturado e pré-jogo. Para este perfil, não basta um tutorial. É necessária uma etapa de treino antes da atividade real, com suporte físico e sem contagem de pontos.

> "Seriam necessárias muitas tentativas prévias com alguém realizando o movimento físico do braço dele até que ele compreenda a lógica da atividade." PC-A, sobre U5-S3

> "Realizar sessões de ensino prévias sem marcação de pontos. Utilizar um bastão para a criança segurar, tornando o ato de estourar as bolinhas mais lúdico e concreto." PC-A

#### 1.3 Progressão de dificuldade e tolerância à frustração

A percepção da progressão de dificuldade foi clara para todos os participantes S1, que identificaram espontaneamente o aumento de velocidade e redução do tamanho dos alvos. A resposta emocional a essa progressão, no entanto, variou:

| Participante | Resposta à progressão | Implicação |
| --- | --- | --- |
| U1-S1 | Motivação mantida mesmo com aumento da dificuldade. Engajamento positivo durante toda a atividade. | Design pode progredir sem mecanismo de retorno. |
| U2-S1 | Dificuldade percebida (nota 9/10), mas interesse mantido. Relatou dificuldade quando o sistema estava lento. Dificuldade atribuída ao hardware, não ao jogo. | Latência do sistema afeta percepção de dificuldade. |
| U3-S1 | Irritabilidade e redução de tolerância à frustração com aumento de dificuldade. Solicitou retorno às fases mais fáceis. | Design deve prever opção de ajuste de dificuldade ou regressão facilitada, especialmente relevante para comorbidades como TDAH e TOD. |
| U4-S2 | Não aceitava pontuação baixa. Alta competitividade. Pedia jogar novamente para melhorar o resultado. | Progressão e pontuação visível podem amplificar frustração. Feedback de acerto deve ser reforçado. |

#### 1.4 Duração da fase e tolerabilidade

A fase com duração de 30 segundos foi percebida como adequada para todos os perfis. Participantes S1 demonstraram disposição para repetir a atividade várias vezes espontaneamente.

> "Eles são muito acelerados, a gente dá uma demanda, para eles é 10 minutos." C1, sobre U4-S2

> "Eu vou de novo!" U4-S2, após cada partida, relatado por observação

Para S3, a duração da fase é secundária: a variável crítica é o nível de mediação necessário, que tende a aumentar ao longo da sessão por fadiga do suporte, não do participante.

#### 1.5 Postura durante o jogo

Postura em pé foi identificada como mais efetiva para S1 e S2, permitindo maior amplitude de movimento e melhor captura corporal. Para S3, a postura foi condicionada pelo quadro clínico:

> "Acho que é melhor jogar em pé." Observação geral, confirmada por PC-B e C1

> "Gustavo demonstrou preferência por permanecer sentado no chão com o computador apoiado no colo, possivelmente devido à hipotonia postural e maior necessidade de estabilidade proximal." Profissional de saúde, U6-S3

> "A atividade deve ser realizada obrigatoriamente sentado, para garantir a segurança e o foco." PC-A, sobre U5-S3

### Eixo 2. Requisitos sensoriais

#### 2.1 Fundo de tela

**Padrão convergente S1:** preferência pelo fundo branco. Os três participantes S1 reportaram maior conforto visual e melhor atenção aos elementos do jogo com fundo branco ou neutro.

> "Letícia demonstrou preferência pelo fundo branco/neutro do jogo, relatando maior conforto visual dessa forma." Profissional de saúde, U1-S1

> "Lorenzo demonstrou preferência pelo fundo branco." Profissional de saúde, U2-S1 e U3-S1

Para S3, a preferência de fundo não foi determinante. A dificuldade de abstração dominou a experiência independente da configuração visual.

#### 2.2 Tamanho e velocidade dos alvos

**Padrão convergente (todos os perfis):** alvos maiores e velocidade inicial mais lenta facilitam o engajamento e a compreensão da mecânica.

> "O movimento deve começar mais lento e com bolinhas maiores." PC-A, sobre U5-S3

Crianças notaram diferença de tamanho dos alvos e responderam positivamente a alvos maiores. Observação do profissional de saúde, múltiplos participantes.

Para S1, a redução progressiva do tamanho foi percebida e aceita como aumento de desafio. Para S3, alvos menores eliminam a possibilidade de engajamento funcional dado o nível de mediação visuomotora necessário.

#### 2.3 Cores dos alvos

As cores dos alvos foram bem recebidas em todos os perfis. Houve interesse e atenção visual consistente aos elementos coloridos.

> "Crianças gostaram das cores das bolinhas." Observação do profissional de saúde, múltiplos participantes

**Divergência importante:** o cuidador de adultos institucionais apontou que crianças com hiperfoco podem rejeitar alvos de cores específicas, não por desconforto, mas por preferência seletiva, recusando-se a estourar determinadas cores intencionalmente.

> "Pode ser que você não tenha evolução no jogo porque ele não vai querer pegar a bolinha rosa, de propósito." Observação clínica, contexto institucional

#### 2.4 Feedback auditivo, som e música

O som foi avaliado de forma variada entre os participantes, com padrão mais claro emergindo quando cruzado com experiência prévia em jogos digitais:

| Perfil | Resposta ao som | Citação |
| --- | --- | --- |
| U1-S1 | Gostou do som. Sem desconforto sensorial. | "Os efeitos sonoros pareceram contribuir para tornar a experiência mais divertida." |
| U2-S1 | Sem desconforto. Preferência pessoal pelo jogo sem som, não por sensibilidade, mas por escolha. | "Para ele, a presença ou ausência do áudio não gerou diferença significativa." |
| U3-S1 | Gostou do som, especialmente do efeito de estouro das bolhas. | "Demonstrou gostar especialmente do som das bolinhas estourando." |
| U4-S2 | Gostou da música. Cuidador reforçou importância do controle de volume para outras crianças com sensibilidade auditiva. | "A música foi benéfica, mas para algumas crianças, principalmente as mais sensíveis, poderia prejudicar." |
| U5/U6-S3 | Sem desconforto observado. Som percebido como neutro, não interferiu positiva nem negativamente. | "Os estímulos auditivos pareceram neutros durante a experiência, sem sinais de irritação ou sobrecarga sensorial." |

**Convergência transversal:** controle de volume e opção de desativar o som foram recomendados por todos os adultos entrevistados, independentemente do perfil funcional do usuário que acompanham, reconhecendo variabilidade sensorial no espectro.

**Padrão observado:** crianças com experiência prévia em jogos digitais responderam de forma mais positiva ao som. Crianças com sensibilidade auditiva não demonstraram desconforto durante as sessões, possivelmente pela concentração na tarefa.

#### 2.5 Animações e elementos visuais simultâneos

As animações foram bem recebidas em todos os perfis. O nível de movimento na tela não gerou sobrecarga visual.

**Recomendação convergente:** evitar excesso de estímulos simultâneos. Fundo neutro, alvos coloridos e animação funcional (estourar o alvo) foi a configuração mais bem recebida. Elementos decorativos adicionais, estrelinhas, fundos animados, podem gerar distração ou hiperfoco dependendo do perfil.

> "Podia aparecer uns bichinhos, umas estrelinhas enquanto as bolinhas estão rodando." Adulto sem TEA, na sessão piloto

> "O autista não ia conseguir focar na bola. Para mim que não tenho autismo..." Mesma fonte, complementando a observação anterior

### Eixo 3. Segurança e sinais de interrupção

#### 3.1 Sinais de interrupção por nível de suporte

Os sinais de interrupção variam significativamente entre os perfis e devem ser tratados como parâmetros clínicos diferenciados no design do protocolo de uso:

| Perfil | Sinais de interrupção | Fonte |
| --- | --- | --- |
| S1 | Irritabilidade persistente, verbalização de recusa, saída da posição de jogo. | Observação, múltiplos participantes |
| S1 + TOD | Irritabilidade com aumento de dificuldade, solicitação repetida de retorno a fases anteriores, comportamento opositor. | Profissional de saúde, U3-S1 |
| S2 | Dispersão do olhar, desengajamento da tarefa, verbalização de frustração com pontuação. | Observação, U4-S2 |
| S3 | Maior agitação motora; vocalizações específicas (padrão individual); tentativa de levantar da posição; aproximação excessiva da tela; ausência de execução funcional dos movimentos. | PC-A, sobre U5-S3; profissional de saúde, U6-S3 |

> "A brincadeira deve ser interrompida se o paciente apresentar maior agitação, emitir sons (vocalizações) específicos ou tentar levantar para andar." PC-A, sobre U5-S3

> "Dificuldade persistente de compreensão da tarefa, perda de foco, aproximação excessiva da tela e ausência de execução funcional dos movimentos solicitados." Profissional de saúde, U6-S3

#### 3.2 Nível de suporte necessário

| Perfil | Suporte necessário |
| --- | --- |
| S1 | Uso autônomo após demonstração inicial. Suporte verbal pontual quando solicitado. |
| S2 | Demonstração inicial necessária. Supervisão próxima recomendável. Suporte verbal para início de cada fase nova. |
| S3 | Suporte físico e verbal constante. Auxílio físico no início (movimentação guiada do braço). Presença obrigatória de profissional ou cuidador treinado durante toda a sessão. |

> "Para o nível 3, o apoio constante é indispensável, inclusive com auxílio físico no início." PC-A

### Eixo 4. Contexto de uso e barreiras

#### 4.1 Uso domiciliar

O uso domiciliar foi avaliado como viável para S1 e potencialmente para S2, com as ressalvas abaixo. Para S3, o uso domiciliar sem suporte clínico especializado não é recomendado com base nos dados deste PPI.

> "Eu acho que seria muito bom, muito tranquilo. Até mesmo em questão de liberação de tela um pouquinho, que eu sou muito rígida com isso." C1, sobre U4-S2

> "Seria ideal tipo um data show, como acessível a todos, né? A gente colocar, põe ele na tela da sala ou do quarto, um ambiente maior." C1

**Barreiras domiciliares identificadas:**

- Ausência de computador em casa. A maioria dos usuários acessa tecnologia por tablet, que não suporta o sistema de captura de movimento.
- Necessidade de tela grande para uso corporal pleno. Tablets e monitores pequenos limitam a amplitude de movimento.
- Necessidade de supervisão adulta para S2 e S3. Limita uso autônomo.
- Configuração técnica (câmera, posicionamento) pode ser barreira para cuidadores sem suporte técnico.

#### 4.2 Uso institucional / clínico

O uso em contexto clínico foi avaliado positivamente por todos os profissionais entrevistados. Houve convergência na percepção do jogo como reforçador terapêutico, um elemento que pode aumentar a adesão a atividades terapêuticas precedentes.

> "Ele entra como um reforçador, porque eles são bem ligados nessa parte." PC-B

> "A atividade é considerada excelente para trabalhar atenção, foco e agitação motora." PC-A, sobre U5-S3

> "Valeria a pena incluir o jogo como um método de recompensa da terapia, assim estimulando a adesão da criança." PC-B

Sugestão convergente: relatório de desempenho por sessão (pontuação, evolução ao longo do tempo) foi solicitado por profissionais e gestores como ferramenta de acompanhamento clínico.

#### 4.3 Divergências registradas

As divergências abaixo foram identificadas entre participantes e não foram resolvidas. Refletem variabilidade real dentro do espectro e devem ser consideradas no design como variáveis configuráveis, não como contradições a eliminar:

| Tema | Divergência | Implicação para o design |
| --- | --- | --- |
| Som | U2-S1 preferiu sem som (preferência pessoal, sem sensibilidade). U3-S1 e U4-S2 gostaram do som. U1-S1 neutro. | Controle de som deve ser configurável pelo usuário ou responsável. |
| Tolerância à frustração | U1-S1 sem irritabilidade. U3-S1 (TDAH+TOD) com irritabilidade significativa. U4-S2 alta competitividade. | Progressão deve ser configurável. Opção de retorno a fases anteriores é requisito diferencial. |
| Postura | S1 e S2: em pé é melhor. U6-S3: preferiu sentado no chão. U5-S3: obrigatoriamente sentado por segurança. | O design não deve pressupor postura. O protocolo de uso deve orientar por perfil. |
| Complexidade visual | S1: animações extras são bem-vindas. S3: elementos adicionais geram distração ou hiperfoco. | Nível de complexidade visual deve ser parametrizável por perfil. |

## 7. Impacto do PPI nas decisões de design

Esta seção documenta a conexão rastreável entre cada contribuição identificada no PPI e a decisão técnica de design que ela informou. O objetivo é tornar explícito o percurso entre dado de usuário e parâmetro de jogo, garantindo que as escolhas de design sejam justificáveis e revisáveis à luz dos dados que as originaram.

A tabela de impacto é organizada por eixo temático. Para cada linha: a contribuição é apresentada em linguagem próxima à do participante; a decisão técnica é formulada em linguagem de requisito; o perfil indica para qual nível de suporte o requisito se aplica; e a justificativa explicita o raciocínio de conversão.

### 7.1 Requisitos derivados do PPI

#### Eixo 1. Requisitos funcionais

| Contribuição (dado PPI) | Fonte | Requisito técnico derivado | Perfil | Justificativa |
| --- | --- | --- | --- | --- |
| Crianças S1 compreenderam o jogo rapidamente e sem explicações repetidas. | Observação, U1-S1, U2-S1, U3-S1 | Tutorial opcional: o jogo deve ser iniciável sem tutorial obrigatório. | S1 | Exigir tutorial fixo prejudica a experiência de usuários com alta autonomia digital. |
| U4-S2 pode ter dificuldade com tela inicial se comandos não forem visuais e concretos. | C1 | Tutorial visual disponível: demonstração animada da mecânica de captura de movimento antes da primeira partida. | S2 | Usuários S2 se beneficiam de instrução visual concreta antes da interação livre. |
| Participantes S3 tentavam tocar a tela ao invés de realizar o movimento corporal. A abstração do movimento sem toque é a barreira central. | PC-A; profissional de saúde, U5-S3, U6-S3 | Modo de treino pré-jogo (sem pontuação): fase de calibração com movimentos guiados e feedback visual imediato, obrigatória para S3. | S3 | Para S3, o onboarding padrão é insuficiente. É necessária etapa estruturada de associação entre movimento e efeito na tela. |
| S3 precisa de auxílio físico no início, movimentação guiada do braço. | PC-A | O protocolo de uso deve indicar obrigatoriamente a presença de adulto para suporte físico em sessões S3. | S3 | Design de uso, não de interface. O jogo não pode assumir interação autônoma para S3. |
| U3-S1 (TDAH+TOD) apresentou irritabilidade com aumento de dificuldade e pediu retorno a fases anteriores. | Profissional de saúde, U3-S1 | Opção de regressão facilitada: botão ou gesto para retornar à fase anterior, sem penalização de pontuação. | S1 (com comorbidades) | Tolerância à frustração é variável dentro do espectro S1. Mecanismo de regressão preserva engajamento sem forçar progressão. |
| U4-S2 não aceitava pontuação baixa. Alta competitividade e frustração com derrota. | Observação, U4-S2; C1 | Feedback de acerto enfatizado: pontuação visível deve destacar acertos acumulados, não erros. Possibilidade de desativar contagem regressiva. | S2 | Para perfis com baixa tolerância à frustração, o enquadramento positivo da pontuação reduz abandono. |
| Postura em pé identificada como mais efetiva para S1 e S2; S3 requer sentado por segurança clínica. | PC-B; C1; PC-A | Protocolo de uso diferenciado por perfil: em pé recomendado para S1/S2; sentado obrigatório para S3. | Todos | O jogo não impõe postura. O protocolo de uso clínico deve orientar por perfil funcional. |
| Fase de 30 segundos percebida como adequada. Participantes S1 jogaram repetidamente sem fadiga. | Observação, múltiplos participantes | Duração padrão de fase: 30 segundos. Configurável para 20s (S3) ou 45s (S1 avançado). | Todos | 30s é o ponto de equilíbrio entre engajamento e tolerabilidade. Configurabilidade permite adaptação clínica. |

#### Eixo 2. Requisitos sensoriais

| Contribuição (dado PPI) | Fonte | Requisito técnico derivado | Perfil | Justificativa |
| --- | --- | --- | --- | --- |
| Três participantes S1 reportaram preferência pelo fundo branco; maior conforto visual e atenção aos alvos. | U1-S1, U2-S1, U3-S1 | Fundo branco como configuração padrão do jogo. | S1 | Padrão convergente robusto (3/3 participantes S1). Fundo neutro reduz competição visual com os alvos. |
| Alvos maiores e mais lentos facilitam o engajamento inicial em todos os perfis. | PC-A; profissional de saúde, múltiplos | Configuração inicial: alvos grandes (tamanho máximo), velocidade baixa. Redução progressiva conforme desempenho. | Todos | Consenso entre profissionais e corroborado por observação direta. Alvos pequenos eliminam possibilidade de engajamento funcional em S3. |
| Crianças com hiperfoco podem rejeitar alvos de cores específicas intencionalmente. | Observação clínica, contexto institucional | Configuração de cores dos alvos: possibilidade de restringir paleta ou fixar cor única por sessão. | S2, S3 | Hiperfoco em cor pode comprometer a progressão se o usuário recusar alvos de determinada cor. |
| Controle de volume e opção de desativar som recomendados por todos os adultos entrevistados. | PC-A, PC-B, C1 | Controle de volume ajustável (0 a 100%) e opção de desativar música de fundo, mantendo efeitos sonoros funcionais. | Todos | Variabilidade sensorial auditiva no espectro é alta. Configurabilidade é requisito de acessibilidade básico. |
| Crianças com experiência em jogos gostaram do som; crianças com sensibilidade não se incomodaram durante sessão. | Profissional de saúde, múltiplos | Som ativado por padrão, com acesso fácil ao controle de volume na tela principal. | Todos | Som contribui para engajamento de usuários com experiência digital. Controle acessível preserva adaptabilidade. |
| Elementos visuais decorativos adicionais (estrelinhas, fundos animados) podem causar distração ou hiperfoco em TEA. | Observação clínica, contexto institucional | Interface minimalista por padrão: fundo neutro, alvos coloridos, animação funcional de estouro. Sem elementos decorativos ativos por padrão. | S2, S3 | Redução de carga visual é requisito de acessibilidade para TEA. Elementos extras podem ser habilitados para S1 como personalização. |

#### Eixo 3. Segurança e interrupção

| Contribuição (dado PPI) | Fonte | Requisito técnico derivado | Perfil | Justificativa |
| --- | --- | --- | --- | --- |
| Sinais de interrupção variam significativamente entre S1 (irritabilidade verbal) e S3 (agitação motora, vocalização, aproximação da tela). | PC-A; profissional de saúde, U5-S3, U6-S3 | Guia de sinais de interrupção por perfil de suporte integrado ao protocolo de uso, não ao jogo. | Todos | Os sinais não são detectáveis pelo jogo automaticamente. Devem ser documentados para o profissional ou cuidador. |
| Para S3, apoio constante é indispensável, inclusive auxílio físico no início. | PC-A | Classificação do jogo como uso supervisionado obrigatório para S3 no protocolo clínico. | S3 | Design de uso: o jogo não deve ser prescrito para uso autônomo em S3. |

#### Eixo 4. Contexto de uso

| Contribuição (dado PPI) | Fonte | Requisito técnico derivado | Perfil | Justificativa |
| --- | --- | --- | --- | --- |
| Maioria dos usuários acessa tecnologia por tablet, sem computador em casa. | C1 | Requisito de compatibilidade: investigar versão para tablet com câmera frontal como via de acesso domiciliar. | S1, S2 | Barreira de infraestrutura compromete uso domiciliar se o jogo for exclusivo para computador. |
| Jogo percebido como reforçador terapêutico. Pode aumentar adesão a atividades precedentes. | PC-A, PC-B | Posicionamento clínico recomendado: jogo como atividade de encerramento ou recompensa da sessão terapêutica. | Todos | Uso como reforçador aumenta adesão sem comprometer o objetivo terapêutico da sessão. |
| Profissionais solicitaram relatório de desempenho por sessão para acompanhamento clínico. | PC-A, PC-B; gestores | Relatório de sessão: pontuação por partida, evolução ao longo do tempo, duração efetiva de jogo. | Uso clínico | Dado de desempenho é clinicamente relevante para ajuste de progressão e comunicação com equipe multiprofissional. |

### 7.2 Contribuições não incorporadas

As contribuições abaixo foram registradas mas não convertidas em requisitos técnicos nesta fase, com justificativa explícita:

| Contribuição | Motivo da não incorporação |
| --- | --- |
| Incluir letras ou elementos de alfabetização nos alvos (sugerido por PC-B). | Expande o escopo do jogo para além do paradigma de captura de movimento visuomotora. Pode ser considerado em versão futura com objetivo pedagógico específico. |
| Jogar em modo multiplayer, dois jogadores simultâneos (sugerido espontaneamente por PC-B). | Requer redesign significativo de interface e lógica de câmera. Fora do escopo da Fase 1. |
| Incluir personagens temáticos (dinossauros, carros) nos alvos em vez de bolinhas (sugerido por gestora institucional). | Personalização temática é desejável mas secundária à parametrização funcional. A ser considerado após validação dos parâmetros core. |

## 8. Reflexão crítica e limitações

Esta seção apresenta uma análise honesta das limitações metodológicas deste ciclo de PPI. O objetivo não é minimizar as contribuições do processo, mas garantir que as decisões de design derivadas sejam interpretadas com o grau de confiança adequado ao rigor da coleta.

**Tamanho e composição da amostra**

Seis usuários finais com TEA participaram, distribuídos entre S1 (n=3), S2 (n=1) e S3 (n=2). A amostra é pequena para generalização, mas adequada para a natureza qualitativa e exploratória do PPI nesta fase.

O Suporte 2 está representado por um único participante sem entrevista direta. Seus dados foram complementados por cuidador e profissional, introduzindo mediação que pode ter filtrado percepções relevantes.

**Ausência de observador independente**

Em ambas as rodadas de coleta, a facilitação e o registro de reações espontâneas foram realizados pela mesma pessoa. A ausência de observador independente aumenta o risco de viés de atenção seletiva. O facilitador pode ter registrado com maior precisão os comportamentos mais salientes.

**Intercorrências técnicas**

Falhas de câmera e travamento do sistema afetaram sessões da primeira rodada. As respostas sobre ritmo e velocidade nessas sessões foram coletadas em condições de uso diferentes das pretendidas, e devem ser interpretadas com cautela.

Em uma sessão (U4-S2), a entrevista direta não foi possível. Os dados dessa sessão têm validade reduzida para captar a perspectiva do próprio usuário.

**Dados mediados para S3**

Nenhum dos participantes S3 foi entrevistado diretamente. Todos os dados clínicos desse perfil passam pelo olhar do profissional responsável, que seleciona e interpreta o comportamento observado. Esse filtro é metodologicamente inevitável para este perfil, mas deve ser reconhecido como limitação.

**Contexto exclusivamente institucional**

Todos os participantes foram recrutados em contexto de atendimento clínico especializado. Crianças com TEA sem vínculo com serviços especializados, que podem ter perfis funcionais e de acesso à tecnologia distintos, não estão representadas neste PPI.

**Possíveis vieses**

O contexto institucional pode ter inibido avaliações negativas do jogo. Participantes e profissionais podem ter moderado críticas em função da relação com a equipe de pesquisa.

Um participante S1 com desempenho excepcionalmente alto (100 pontos) jogou em sessão com adultos presentes, o que pode ter influenciado positivamente a percepção geral do jogo pelos observadores.

**Representatividade e implicação**

Os dados são suficientemente robustos para orientar decisões de design para S1 e S2 nesta fase. Para S3, os dados delimitam barreiras e requisitos mínimos de adaptação, mas não sustentam afirmações sobre eficácia terapêutica ou generalização clínica.

Todas as decisões de design derivadas deste PPI devem ser tratadas como hipóteses a validar em ciclos subsequentes de teste com usuários.

## 9. Plano de continuidade

O presente PPI representa a Fase 1 de um processo contínuo de envolvimento de usuários no desenvolvimento do jogo. As decisões de design derivadas serão tratadas como hipóteses a serem validadas em ciclos subsequentes, conforme descrito abaixo.

**Próximo ciclo de PPI**

Fase 2, teste de protótipo: após o desenvolvimento do jogo com os requisitos levantados neste ciclo, um novo ciclo de PPI será conduzido com os mesmos perfis de participantes para avaliar se os requisitos foram adequadamente implementados e identificar novos ajustes.

**Validação dos requisitos**

Cada requisito técnico derivado da Tabela 7.1 será avaliado especificamente no próximo ciclo: os participantes interagirão com a versão implementada e reportarão se as adaptações correspondem às suas necessidades reais.

**Ampliação da amostra**

O próximo ciclo buscará incluir: (a) participante S2 com entrevista direta; (b) participantes de contexto domiciliar sem vínculo institucional; (c) ampliação da faixa etária para 10 a 14 anos.

**Devolutiva aos participantes**

Cada participante ou seu responsável receberá um sumário individual das contribuições que deu ao projeto e das decisões de design que foram informadas por sua participação. A devolutiva será apresentada em linguagem acessível, sem jargão técnico.

**Arquivamento**

Transcrições de áudio, diários de campo e registros estruturados de sessão estão arquivados em repositório institucional com acesso restrito à equipe de pesquisa. Os dados serão mantidos por cinco anos após o encerramento do projeto, conforme requisitos éticos.

## Referências metodológicas

- Crocker JC et al. Methods for conducting and reporting patient and public involvement in clinical trials: A systematic review. Health Expectations. 2018.
- Yardley L et al. The Person-Based Approach to Intervention Development. Journal of Medical Internet Research. 2015.
- NIHR. Guidance for reporting involvement of patients and public: GRIPP2 reporting checklists. BMJ Open. 2017.
- APA. Diagnostic and Statistical Manual of Mental Disorders, 5th ed. (DSM-5). American Psychiatric Association. 2013.

## Nota final: sobre o uso deste documento

Este relatório foi produzido como instrumento de transparência metodológica e rastreabilidade das decisões de design. Ele não substitui avaliação clínica individualizada, nem constitui evidência de eficácia terapêutica do jogo. As decisões de design aqui documentadas são baseadas em dados qualitativos de uma amostra pequena e devem ser revisadas à luz de evidências acumuladas em ciclos subsequentes de desenvolvimento e teste.
