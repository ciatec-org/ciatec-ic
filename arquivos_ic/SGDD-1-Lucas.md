# SGDD - Lucas

## Jogo baseado em N-Back Task

> Construto: memória de trabalho, especificamente os processos de manutenção, atualização e controle atencional. O participante recebe uma sequência contínua de estímulos e deve indicar se o estímulo atual corresponde ao apresentado N posições antes.

De acordo com documento disponilizado que trata de paradigmas, o desafio de design seria encontrar um envelope narrativo adequado.

Segue uma formulação simples de um jogo:

### Os estímulos poderiam ser músicas

**Músicas de diferentes gêneros**. Dependendo da criança, elas podem ter diferentes alinhamentos de gosto musical, ou ainda não terem definido um **"gênero musical favorito"**. 

É necessário levar em conta que **o espectro autista é amplo**. Dessa maneira, podemos ter pessoas autistas com **hiperfoco** em gênero musical específico, ou bandas específicas. Ao mesmo tempo, parte das crianças podem ser mais flexíveis com relação a isso, podendo variar de gênero musical dependendo do contexto. 

> Um problema poderia ser o fato de que não teríamos licenciamento de bandas famosas ou algo do tipo. Mas, existem diversas músicas sem direitos autorais que podem ser utilizadas gratuitamente e podemos selecionar diferentes tipos delas.

Além disso, talvez algumas nem gostem de música ativamente. Então, poderíamos deixar disponível diferentes estímulos auditivos, como ruídos específicos para diferentes gostos. 


A parte de acessibilidade poderia ser melhorada a partir de um questionário rápido a respeito de **como a criança está se sentindo no momento** e qual é o **tipo de estímulo que ela gostaria de receber**.

### É importante levar em consideração momentos de crises

Obviamente, o jogo diz respeito à questão atencional e à memória. Porém, é importante garantir que os "atritos" existentes devem permanecer unicamente entorno desses pontos. É importante evitar estímulos que podem gerar crises ou agravar uma.

### Jogabilidade

Uma música poderia ser apresentada e mapeada a partir de *time stamps* enumerados. Essas parcelas de tempo poderiam ser separadas através de algum tipo de metrônomo, que é importante para mapear o ritmo e dar um norte melhor para a pessoa. Porém, é importante levar em consideração que o som de metrônomo pode causar desconforto em algumas crianças. O objetivo aqui é tentar minimizar a chance de sobrecarga sensorial.

Eventualmente, **a música pausará** e a criança será questionada a respeito de qual som haveria ocorrido **N-passos atrás**. Determinadas opções seriam oferecidas e o usuário deve selecionar a correta. A quantidade de erros de escolha podem ser computadas como algum tipo de descrição a respeito de seu desempenho.

> Talvez seja interessante não ir eliminando as alternativas incorretas que a criança selecionar. Isso pode, também, servir de métrica para o nosso sistema.

> Vale ressaltar que músicas geralmente possuem repetições em suas estruturas, isso pode ser levado em consideração para construção do envelope narrativo.

O nível de dificuldade seria adaptativo a partir das debilidades encontradas por nível de memória. À princío, é importante detectar o tipo de memória mais frágil da pessoa em questão. Por exemplo, uma criança autista que também é **TDAH** muito provavelmente terá uma memória de curto prazo menos eficiente do que as demais.

Aqui, vale o seguinte questionamento: ao detectar uma memória de curto prazo menos eficiente, **exigiremos mais ou menos dela**? Devemos **enfatizar** os questionamentos acerca de estímulos mais recentes? Exigir mais de um tipo de memória que é natualmente mais "limitada" para uma pessoa neurodivergente poderá **desestimulá-la**?

Depois de cada pausa, **uma nova quantidade de tempo de rodagem para a música será definida** e ela voltará a tocar. Quando ela pausar novamente, perguntas a respeito de ambos os conjuntos de *timestamps* poderiam ser feitas, dependendo do **nível de dificuldade**.

Ao final, teríamos a pontuação do usuário para aquela música e ele podería ter a opção de escutar a música inteira novamente, sem pausas.

### Algumas ideias de UX/UI

1) **Um cronômetro na parte de cima**, indicando o tempo restante. Para auxiliar pessoas com problemas de visão, uma **narração de fundo** poderia funcionar;

2) As músicas apresentadas a partir de **blocos de ondas sonoras ou de notas musicais**, com uma numeração referente ao *timestamp* logo abaixo;

3) Os blocos, conforme o tempo for passando, vão sendo **enfileirados um na frente do outro**, formando a estrutura da música;

4) Quando o cronômetro zerar, um dos blocos será indicado e a criança será questionada a respeito daquele estímulo. Aparecerá, então, um quadro com opções de resposta em formato de bloco.

> Questionamento: vale à pena manter como resposta o mesmo símbolo que inicialmente foi apresentado na sequência?

### Contexto lúdico

Como o contexto aqui abordado é o musical, uma ideia é a seguinte:

1) Você é um músico e está aprendendo com um(a) professor(a). Ela toca trechos da música e depois lhe pergunta a respeito de trechos específicos. -> Justifica ter uma narração de fundo.
