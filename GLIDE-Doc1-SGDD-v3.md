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
> ⚙ *Preencha os campos abaixo. Mantenha a versão atualizada a cada ciclo de PPI incorporado.*
> ⚙ *O campo Posição no Triple Diamond indica em qual fase do GLIDE este documento foi gerado.*

**Nome do jogo:** *a preencher*
**Versão do documento:** *ex: v1.0 — ciclo PPI inicial*
**Projeto vinculado:** *ex: ATGCP — Adaptive Therapeutic Game Calibration Protocol*
**Organização:** *CIATec*
**Posição no Triple Diamond:** *ex: Transição 1º para 2º Diamante*
**Ciclos de PPI incorporados:** *ex: PPI-surdos-v1 | PPI-neurologico-v1*
**Pesquisador responsável:** *a preencher*
**Data de criação:** *a preencher*
**Última atualização:** *a preencher*

## 2  CONCEITO DO JOGO
> ⚙ *Descreva o jogo como faria em um GDD de mercado. A população clínica é parte do público-alvo, não nota de rodapé.*

### 2.1  Premissa
*[Descreva o jogo em 2 a 3 frases. O que o jogador faz? Qual o contexto? O que torna a experiência singular?]*

### 2.2  Gênero e Plataforma
**Gênero:** *ex: jogo de captura / serious game terapêutico*
**Plataforma:** *ex: web, mobile, desktop com câmera obrigatória*
**Modo de jogo:** *ex: single player, sessão supervisionada, uso domiciliar*
**Tecnologia de interação:** *ex: visão computacional com rastreamento de mãos por câmera*

### 2.3  Público-Alvo
> ⚙ *Liste todos os perfis de usuário: usuário final, profissionais mediadores e cuidadores quando relevantes.*
*[Descreva os perfis de público-alvo. Ex: usuários com condição X, faixa etária Y, profissionais mediadores Z.]*

## 3  OBJETIVO TERAPÊUTICO E EDUCACIONAL
> ⚙ *Esta seção não existe em GDDs de mercado. É a primeira camada exclusivamente científica.*
> ⚙ *Use linguagem compatível com MRC Framework. Diferencie objetivo terapêutico de objetivo de engajamento.*

### 3.1  Objetivo Terapêutico Principal
*[Descreva o desfecho clínico ou funcional que o jogo visa produzir.]*

### 3.2  Objetivos Secundários
*[Liste objetivos secundários: funcionais, de engajamento, de acessibilidade, de coleta de dados.]*

### 3.3  Fora do Escopo
> ⚙ *Delimitar o escopo evita expectativas clínicas incorretas. Ex: o jogo não substitui avaliação clínica formal.*
*[Liste explicitamente o que está fora do escopo terapêutico ou educacional deste jogo.]*

## 3A  GUIDING PRINCIPLES
> ⚙ *Esta seção é derivada da síntese de evidências do PPI — não de relatos individuais de participantes.*
> ⚙ *Os Guiding Principles funcionam como a bússola do projeto. Cada decisão de design deve ser rastreável a um princípio.*
> ⚙ *Um mesmo princípio pode ser sustentado por múltiplas evidências do PPI: entrevistas, observações, literatura, workshops.*
> ⚙ *Formato: GP-ID | Evidência sintetizada do PPI | Objetivo de design | Funcionalidades previstas.*
> ⚙ *Esta seção é referenciada nas Seções 4, 8 e 13A, e nos documentos Doc 2 e Doc 3.*

| GP | Evidência sintetizada do PPI | Objetivo de design | Funcionalidades previstas |
| --- | --- | --- | --- |
| GP-01 | ex: Usuários apresentam barreiras de compreensão quando a interação depende de texto escrito | Permitir uso autônomo sem leitura | Tutorial visual + instrução em Libras ou equivalente |
| GP-02 | ex: Usuários precisam compreender imediatamente a causa dos erros para manter o engajamento | Tornar o estado do jogo imediatamente compreensível | Feedback visual explícito para acerto e falha |
| GP-03 | ex: Usuários respondem melhor à progressão gradual do que a saltos bruscos de dificuldade | Manter engajamento ao longo das sessões | Progressão adaptativa por desempenho consistente |
| GP-04 | ex: Sessões prolongadas ou sem controle de carga podem aumentar fadiga e reduzir adesão | Preservar segurança e tolerabilidade | Limite de duração e critérios de interrupção |
| [adicionar] |  |  |  |

> ⚠ **Cada Guiding Principle deve ter pelo menos uma evidência rastreável ao relatório de síntese do PPI.**

## 4  MECÂNICAS CORE  —  MDA: MECHANICS
> ⚙ *Descreva cada mecânica como faria em um GDD de mercado.*
> ⚙ *Para cada mecânica, preencha: justificativa clínica, Guiding Principle correspondente, hipótese de design e origem no PPI.*
> ⚙ *A hipótese de design responde à pergunta: por que acreditamos que essa decisão ajudará essa população?*
> ⚙ *Mecânicas sem rastreabilidade ao PPI devem ser marcadas como decisão de design sem origem PPI.*

### 4.1  Mecânica Principal
*[Nome da mecânica principal]*
**Descrição:**
*[Como funciona, regras, controles, o que o jogador faz.]*
**Justificativa clínica:**
*[Por que essa mecânica serve ao objetivo terapêutico.]*
**Guiding Principle:**
*[ex: GP-01 / decisão de design sem Guiding Principle]*
**Hipótese de design:**
*[Por que acreditamos que essa decisão ajudará essa população? Ex: a demonstração visual reduzirá a dependência de leitura, aumentando autonomia e compreensão inicial.]*
**Origem PPI:**
*[Evidência sintetizada que originou essa decisão / decisão de design]*

### 4.2  Sistema de Feedback
*[Descreva todos os tipos de feedback: visual, sonoro, háptico. Para cada tipo: o que acontece, quando acontece, o que comunica ao jogador.]*
**Justificativa clínica:**
Feedback imediato e compreensível é requisito terapêutico. Erro sem causa compreensível rompe engajamento e calibração.
**Guiding Principle:**
*[ex: GP-02]*
**Hipótese de design:**
*[Por que acreditamos que esse sistema de feedback ajudará essa população?]*
**Origem PPI:**
*[a preencher por ciclo]*

### 4.3  Sistema de Progressão
*[Como o jogador avança. Critérios de progressão, regressão e interrupção. Parâmetros que mudam entre fases.]*
**Justificativa clínica:**
Progressão baseada em desempenho consistente, não em acerto bruto. Calibração terapêutica requer controle de intensidade.
**Guiding Principle:**
*[ex: GP-03]*
**Hipótese de design:**
*[Por que acreditamos que essa lógica de progressão ajudará essa população?]*

### 4.4  Onboarding
> ⚙ *Para populações com barreira de leitura (surdos, baixa escolaridade, crianças), o onboarding visual não é acessibilidade opcional. É requisito de mecânica.*
*[Como o jogador aprende a jogar. Demonstração, tutorial, suporte visual. Sem dependência de leitura quando relevante.]*
**Guiding Principle:**
*[ex: GP-01]*
**Hipótese de design:**
*[Por que acreditamos que esse onboarding será suficiente para essa população?]*

## 5  DINÂMICAS  —  MDA: DYNAMICS
> ⚙ *Descreva como as mecânicas geram experiência ao longo de uma sessão e ao longo do tempo.*

### 5.1  Arco de uma Sessão Típica
*[Descreva o fluxo de uma sessão do início ao fim: entrada, aquecimento, progressão, encerramento. Duração esperada por sessão e por fase.]*

### 5.2  Progressão Longitudinal
*[Como o jogo evolui ao longo de múltiplas sessões. Como o sistema ajusta dificuldade. Critérios de avanço entre sessões.]*

### 5.3  Calibração de Intensidade Terapêutica
> ⚙ *Esta subseção é exclusiva do GDD científico. Descreva como a intensidade terapêutica é controlada pelo sistema.*
*[Descreva as variáveis que controlam intensidade terapêutica: velocidade, tempo de resposta, área de alvo, duração, frequência. Limites de segurança.]*

## 6  EXPERIÊNCIA PRETENDIDA  —  PLAYER EXPERIENCE (MDA: AESTHETICS)
> ⚙ *Descreva a experiência que o jogo pretende provocar, não o visual, mas a sensação.*
> ⚙ *MDA Aesthetics: sensation, fantasy, narrative, challenge, fellowship, discovery, expression, submission.*
> ⚙ *Para populações clínicas, a experiência pretendida deve ser calibrada à condição e ao contexto de uso.*
> ⚙ *Referência: Hunicke, LeBlanc e Zubek (2004). O termo Aesthetics no MDA refere-se à experiência do jogador, não ao visual.*
*[Descreva a experiência pretendida. Quais dimensões do MDA Aesthetics são prioritárias para esta população e este objetivo terapêutico?]*

## 7  ELEMENTAL TETRAD
> ⚙ *O Elemental Tetrad (Jesse Schell) estrutura o jogo em quatro elementos: Mechanics, Story, Aesthetics, Technology.*
> ⚙ *Para cada elemento: descrição padrão de GDD mais restrições explícitas da população incorporadas.*

### 7.1  Mechanics  —  Regras e Sistemas
*[Síntese das mecânicas principais. Regras do jogo. Loop de jogo. Referência à Seção 4 para detalhamento.]*
**Restrições da população:**
*[Ex: ausência de feedback sonoro como requisito; contraste visual como parâmetro crítico; duração máxima de sessão como limite de segurança.]*

### 7.2  Story  —  Narrativa e Contexto
*[Contexto narrativo do jogo, se existir. Pode ser mínima em jogos terapêuticos abstratos.]*
**Restrições da população:**
*[Ex: narrativa não pode depender de texto; elementos culturais relevantes para a população devem ser incorporados quando possível.]*

### 7.3  Aesthetics  —  Visual, Som e Sensação
*[Direção visual, paleta de cores, estilo gráfico, design de som. Referência à Seção 6.]*
**Restrições da população:**
*[Ex: alto contraste como requisito; ausência de áudio como característica esperada; campo visual limpo.]*

### 7.4  Technology  —  Plataforma e Implementação
*[Plataforma, tecnologia de interação, requisitos técnicos de hardware. Limitações de infraestrutura do contexto de uso.]*
**Restrições da população:**
*[Ex: funcionar em hardware doméstico de baixo custo; câmera padrão sem sensor de profundidade; conectividade limitada.]*

## 8  MAPEAMENTO LM-GM
> ⚙ *LM-GM: Learning Mechanics e Game Mechanics (Arnab et al., 2015). Seção exclusiva do GDD científico.*
> ⚙ *Para cada objetivo clínico ou educacional, identifique qual mecânica de jogo o operacionaliza e qual Guiding Principle sustenta essa relação.*
> ⚠ **Se um objetivo clínico não tiver mecânica correspondente, é lacuna de design. Registre na Seção 13.**

| Objetivo clínico / educacional | Mecânica de jogo | Como operacionaliza | GP |
| --- | --- | --- | --- |
| ex: desenvolver coordenação motora fina | ex: captura de alvos por rastreamento de mãos | ex: o alvo exige precisão de posicionamento dentro de janela temporal | ex: GP-03 |
| ex: manter engajamento terapêutico | ex: progressão gradual de dificuldade | ex: dificuldade aumenta conforme consistência, evitando frustração e tédio | ex: GP-03 |
| [adicionar linhas conforme necessário] |  |  |  |

## 9  PERSONAS E REQUISITOS DERIVADOS
> ⚙ *Personas em formato sintético, derivadas do F03 do ciclo de PPI. Não reproduza o F03 completo aqui.*
> ⚙ *Cada persona deve gerar pelo menos três requisitos operacionalizáveis. Atualize a cada novo ciclo de PPI.*
> ⚙ *Personas não identificam participantes individuais. São perfis compostos derivados da síntese do PPI.*

### 9.1  Persona 1 — [Nome funcional]
**Identificação funcional:** *ex: Usuário adulto com limitação motora e alta motivação lúdica*
**Ciclo PPI de origem:** *ex: PPI-surdos-v1*
**Contexto de uso:** *ex: uso domiciliar, sessões curtas, autonomia limitada*
**Requisitos derivados:** *listar abaixo*
–  ex: feedback visual explícito para falha de colisão
–  ex: onboarding por demonstração visual sem dependência de texto
–  ex: fundo escuro como opção ou padrão
**Guiding Principles relacionados:** *ex: GP-01, GP-02*
**Impacto nas decisões:** *ex: Seções 4, 10, 11*
**Status de validação:** *ex: Válida / Válida com ressalva — especificar lacuna*

### 9.2  Persona 2 — [Nome funcional]
**Identificação funcional:** *a preencher*
**Ciclo PPI de origem:** *a preencher*
**Contexto de uso:** *a preencher*
**Requisitos derivados:** *listar abaixo*
*[requisito 1]*
*[requisito 2]*
*[requisito 3]*
**Guiding Principles relacionados:** *a preencher*
**Impacto nas decisões:** *a preencher*
**Status de validação:** *a preencher*

### 9.3  Persona 3 — [Nome funcional]
**Identificação funcional:** *a preencher*
**Ciclo PPI de origem:** *a preencher*
**Contexto de uso:** *a preencher*
**Requisitos derivados:** *listar abaixo*
*[requisito 1]*
*[requisito 2]*
*[requisito 3]*
**Guiding Principles relacionados:** *a preencher*
**Impacto nas decisões:** *a preencher*
**Status de validação:** *a preencher*

## 10  INTERFACE E ACESSIBILIDADE
> ⚙ *Acessibilidade está integrada à especificação de interface, não é seção separada.*
> ⚙ *Referência: WCAG 2.1, ISO 9241-210, UDL quando aplicável.*

### 10.1  Princípios de Interface
*[Descreva os princípios que guiam as decisões de UI/UX. Ex: mínimo de texto, feedback visual prioritário, campo visual limpo.]*

### 10.2  Requisitos de Acessibilidade por Domínio
**Visual:**
*[ex: alto contraste obrigatório; opção de fundo escuro; tamanho mínimo de alvo]*
**Auditivo:**
*[ex: todos os comandos de áudio com equivalente visual; ausência de áudio não é limitação]*
**Motor:**
*[ex: tempo mínimo de resposta ajustável; área de interação compatível com amplitude de movimento da população]*
**Linguístico:**
*[ex: português simples; evitar estrangeirismos; onboarding sem dependência de leitura]*
**Cultural:**
*[ex: elementos culturais relevantes para a população incorporados; validados no PPI]*

### 10.3  Telas e Fluxo de Navegação
*[Descreva as telas principais e o fluxo de navegação. Pode ser complementado com wireframes em documento anexo.]*

## 11  PARÂMETROS DE FASE E PROGRESSÃO
> ⚙ *Esta seção conecta o GDD científico ao protocolo clínico (ATGCP ou equivalente).*
> ⚙ *Inclua critérios explícitos de avanço, regressão e interrupção, não apenas progressão ascendente.*

### 11.1  Variáveis de Fase

| Variável | Descrição e faixa de valores |
| --- | --- |
| ex: velocidade do alvo | faixa: X a Y; impacto: demanda de tempo de reação |
| ex: destroy_time | faixa: X a Y; impacto: pressão temporal por alvo |
| ex: tamanho do alvo | faixa: X a Y; impacto: demanda de precisão motora |
| ex: duração da fase | faixa: X a Y; impacto: carga por sessão e fadiga |
| [adicionar variáveis] |  |

### 11.2  Critérios de Progressão, Regressão e Interrupção

| Evento | Critério |
| --- | --- |
| Avanço de fase | ex: consistência de desempenho acima de X% em Y sessões consecutivas |
| Regressão de fase | ex: queda de desempenho acima de X%, aumento de tempo de resposta, sinais de frustração |
| Interrupção de sessão | ex: fadiga, desconforto visual, confusão sobre a tarefa, eventos adversos |
| Interrupção do protocolo | ex: critérios clínicos definidos no protocolo derivado |

### 11.3  Faixas de Fase por Perfil
> ⚙ *Defina faixas de entrada por perfil de usuário, não uma progressão linear universal.*
*[Descreva faixas de fase recomendadas por persona ou grupo clínico. Ex: Persona 1 entrada conservadora, níveis X a Y.]*

## 12  REQUISITOS TÉCNICOS CONSOLIDADOS
> ⚙ *Esta seção alimenta diretamente o Doc 2 — Backlog Ágil. Organize por domínio com prioridade e origem.*
> ⚠ **Requisitos sem prioridade definida bloqueiam o Doc 2. Não deixe em branco.**

| Domínio | Requisito | Prioridade | Origem |
| --- | --- | --- | --- |
| Funcional | ex: feedback visual explícito para falha de colisão | Alta | PPI-surdos-v1 / GP-02 |
| Sensorial / Visual | ex: fundo escuro como opção ou padrão | Alta | PPI-surdos-v1 / GP-01 |
| Acessibilidade | ex: onboarding sem dependência de texto em português | Alta | PPI-surdos-v1 / GP-01 |
| Acessibilidade | ex: instrução em Libras no onboarding | Alta | PPI-surdos-v1 / GP-01 |
| Interface | ex: recorte ou máscara visual, exibir apenas mãos | Média | PPI-surdos-v1 / GP-02 |
| Progressão | ex: progressão por parâmetro dominante único por transição | Alta | Decisão de design / GP-03 |
| Segurança | ex: critérios explícitos de interrupção de sessão | Alta | Protocolo clínico / GP-04 |
| [adicionar] | [a preencher] | [prioridade] | [origem] |

## 13  LACUNAS E DECISÕES PENDENTES
> ⚙ *Seção viva, atualizada a cada ciclo de PPI e a cada iteração de desenvolvimento.*
> ⚙ *Para cada lacuna: descrição, impacto, ação necessária, responsável.*
> ⚠ **Lacunas que bloqueiam o Doc 2 devem ser marcadas como CRÍTICAS.**

| Lacuna / Decisão pendente | Impacto | Ação necessária | Responsável |
| --- | --- | --- | --- |
| ex: Bloco 5.1 do PPI sem respostas — expectativas clínicas incompletas | Eixo 3 do PPI incompleto. Personas 1 e 3 com ressalva clínica. | Coletar bloco 5.1 em próximo ciclo de PPI | Pesquisador responsável |
| ex: delay/latência no rastreamento — causa não confirmada | Pode ser limitação de hardware de teste ou do jogo | Investigação técnica antes de decisão | Equipe de desenvolvimento |
| [adicionar lacunas] |  |  |  |

## 13A  HIPÓTESES PARA VALIDAÇÃO
> ⚙ *Esta seção consolida todas as hipóteses de design dispersas na Seção 4.*
> ⚙ *Cada hipótese é uma aposta testável derivada de um Guiding Principle.*
> ⚙ *Esta seção é o ponto de entrada para a construção do protocolo no Doc 3.*
> ⚙ *Não define instrumentos ou métodos de validação. Isso pertence ao Doc 3.*

| H-ID | Hipótese | Guiding Principle | Será verificada no Doc 3 |
| --- | --- | --- | --- |
| H-01 | ex: O onboarding visual permitirá uso autônomo sem necessidade de instrução presencial | GP-01 | Sim |
| H-02 | ex: O feedback visual de falha reduzirá confusão e erros repetidos durante a tarefa | GP-02 | Sim |
| H-03 | ex: A progressão gradual manterá engajamento ao longo das sessões do protocolo | GP-03 | Sim |
| H-04 | ex: Os limites de duração e critérios de interrupção prevenirão fadiga excessiva | GP-04 | Sim |
| [adicionar] |  |  |  |

> ⚠ **Cada hipótese deve ser rastreável a um Guiding Principle. Hipóteses sem GP de origem indicam lacuna na Seção 3A.**
