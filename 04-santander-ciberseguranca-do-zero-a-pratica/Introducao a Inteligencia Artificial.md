## 1. Como a Inteligência Artificial nasceu

Hoje em dia é cada vez mais difícil saber se estamos conversando com uma pessoa ou com um computador. Essa questão ganhou destaque em 1950, quando Alan Turing se perguntou se uma máquina poderia imitar o comportamento humano a ponto de ser impossível diferenciá-la de uma pessoa. Na época, muita gente achava isso impossível, já que os computadores só executavam aquilo para o que haviam sido programados.

Para explorar a ideia, Turing criou o "Jogo da Imitação", que ficou conhecido como **Teste de Turing**. Três participantes ficavam em salas separadas: um avaliador humano, outro ser humano e uma máquina. O avaliador fazia perguntas e recebia respostas apenas por texto, e precisava descobrir quem era a máquina. Se ele não conseguisse identificar com certeza, a máquina estava imitando bem o comportamento humano.

Isso levantou novas questões entre os cientistas, porque uma conversa humana envolve muito mais do que respostas: depende de experiências, conhecimentos e da capacidade de compreender diferentes situações.

Em 1956, na conferência realizada no Dartmouth College (EUA), John McCarthy reuniu pesquisadores como Marvin Minsky, Herbert Simon e Allen Newell para discutir se as máquinas poderiam reproduzir o raciocínio humano. Foi nesse encontro que surgiu o termo **"Inteligência Artificial"**, marcando o início de um novo campo de pesquisa.

### ELIZA

Dez anos depois, em 1966, Joseph Weizenbaum criou a **ELIZA**, um dos primeiros programas capazes de simular uma conversa entre um ser humano e um computador. Naquela época, usar um computador exigia conhecimentos específicos e comandos próprios. A proposta da ELIZA era tornar essa comunicação mais natural, permitindo conversar com a máquina por meio de frases parecidas com as do dia a dia.

Essa necessidade de simplificar a comunicação entre pessoas e computadores contribuiu para o **Processamento de Linguagem Natural (PLN)**, área que busca fazer as máquinas compreenderem e responderem à linguagem humana.

O funcionamento da ELIZA era mais simples do que parece: ela identificava palavras importantes na mensagem e usava respostas previamente programadas para manter a conversa. Se alguém digitasse "Oi, estou triste", ela podia captar a palavra "triste" e responder "Por que você está triste?". Dava a impressão de entender o que a pessoa dizia, mesmo sem entender seus sentimentos.

Vale destacar que a ELIZA não aprendia a cada conversa. Suas respostas vinham de regras criadas antes, e ela não ficava mais inteligente com o uso. A ideia de fazer máquinas aprenderem a partir de dados já existia e seguiu sendo pesquisada, dando origem aos sistemas que aprendem com exemplos, o **Machine Learning (aprendizado de máquina)**.

### Dos anos 70 ao Watson

Com o tempo surgiram programas mais sofisticados. Em 1972, Kenneth Colby, psiquiatra e pesquisador da Universidade de Stanford, criou o **PARRY**. Diferente da ELIZA, ele foi desenvolvido para imitar a maneira de pensar e conversar de uma pessoa, o que permitia respostas mais coerentes com o comportamento que o programa tentava representar.

Na década de 1980 apareceram programas capazes de gerar textos. Um exemplo foi o **Racter**, conhecido por produzir textos criativos, incluindo poemas e histórias. Em 1984 foi publicado o livro *The Policeman's Beard Is Half Constructed*, com textos atribuídos ao programa. Isso mostrou que os computadores podiam ir além de responder perguntas e também produzir conteúdo escrito.

Mesmo assim, o acesso a essas tecnologias ainda era limitado: programar e usar computadores exigia conhecimento específico, e as ferramentas estavam longe de ser tão simples quanto as de hoje.

Nesse contexto, a IBM desenvolveu o **Watson**, um sistema criado para responder perguntas complexas e trabalhar com grandes quantidades de informação. Em 2011, ele ganhou destaque mundial ao vencer dois campeões humanos no programa americano *Jeopardy!*, que exigia conhecimento e capacidade de interpretar perguntas. Foi uma demonstração do avanço dos computadores na compreensão da linguagem humana. Com o tempo, esses sistemas passaram a combinar diferentes formas de analisar textos, reconhecer padrões e produzir respostas.

### ChatGPT

Em 30 de novembro de 2022, a OpenAI lançou o **ChatGPT**, tornando esse tipo de interação acessível ao público pela internet. Diferente dos primeiros programas, ele já chega pronto para conversar, responder perguntas, explicar assuntos e produzir textos, sem que o usuário precise programá-lo ou alimentar uma base de informações manualmente. Seu desenvolvimento usa grandes quantidades de textos e outros materiais, além de um treinamento que permite identificar padrões na linguagem e construir respostas de acordo com o contexto da conversa.

### Conclusão

A interação entre humanos e computadores evoluiu muito: começamos com programas que identificavam palavras e respondiam por regras predefinidas e chegamos a sistemas que interpretam perguntas complexas e produzem respostas bem mais elaboradas. Foram décadas de pesquisa e avanços na área da Inteligência Artificial.

---

## 2. Como uma IA é treinada e o que são LLMs

Para entender como uma IA é treinada, podemos imaginar que estamos ensinando um computador a reconhecer alguma coisa, parecido com o que fazemos ao aprender a identificar objetos no dia a dia: observando características e percebendo o que eles têm em comum. A diferença é que a IA aprende por meio de dados e cálculos matemáticos.

### O exemplo das maçãs

Imagine uma IA capaz de olhar para uma macieira e contar quantas maçãs estão boas e quantas estão estragadas. Primeiro, o modelo precisa aprender o que é uma maçã. Para isso, mostramos várias imagens diferentes: vermelhas, verdes, maiores, menores, com folhas, com o caule em posições variadas. Assim ele começa a perceber os padrões que identificam uma maçã.

No começo, a IA pode errar. Durante o treinamento, ela compara suas respostas com as respostas corretas e ajusta seus parâmetros para melhorar. Esse processo se repete muitas vezes, com muitos exemplos. Com o tempo, ela passa a reconhecer uma maçã mesmo quando encontra uma um pouco diferente das que já viu. Por exemplo, uma maçã bem vermelha, sem tons de amarelo e com o caule em outra posição, ou uma com folha presa ao caule, continuam sendo maçãs para um modelo treinado com exemplos variados. O objetivo é aprender padrões que ajudem a identificar exemplos novos, e não decorar as imagens do treinamento.

Mas se encontrar algo muito diferente do que viu, ela ainda pode errar. Por isso não basta ter muitas imagens: elas precisam ser variadas e representar as situações que a IA vai encontrar na prática.

No nosso exemplo, além de reconhecer maçãs, queremos separar as boas das estragadas. Então precisamos de imagens das duas condições para ensinar o modelo a diferenciá-las. E, para contar todas as frutas da árvore, o sistema também precisa **localizar** cada maçã na imagem, e não só saber se a imagem contém uma fruta.

### A IA guarda todas as imagens?

Não exatamente. O treinamento não funciona como uma pasta cheia de imagens que o computador consulta a cada resposta. Uma rede neural aprende por meio de valores numéricos chamados **parâmetros**, que são ajustados durante o treinamento e influenciam suas respostas. Ela não guarda uma lista escrita dizendo que a maçã é arredondada, tem caule e pode ser vermelha ou verde; aprende padrões matemáticos a partir dos exemplos. As características que usei para explicar o reconhecimento de uma maçã são só uma forma simplificada de entender a ideia.

### Aprendizado supervisionado

Quando o modelo erra durante o treinamento, podemos mostrar a resposta correta. Se ele classificar uma maçã como outro objeto, indicamos que aquela imagem é uma maçã. Esse tipo de treinamento, com exemplos acompanhados das respostas corretas, é o **aprendizado supervisionado**.

Isso não significa que a IA adiciona uma regra nova à memória toda vez que é corrigida. Para os parâmetros mudarem, a correção precisa fazer parte de um processo de treinamento ou de atualização do modelo.

### Tokens

Os **tokens** são unidades que os modelos de linguagem usam para processar textos. Um token pode ser uma palavra inteira, parte de uma palavra, um número ou até um sinal de pontuação. Antes de processar uma frase, o modelo pode dividi-la em várias dessas unidades.

Não podemos confundir os dois conceitos: **tokens** são as unidades usadas no processamento do texto, e **parâmetros** são os valores numéricos aprendidos durante o treinamento.

### LLMs e SLMs

As **LLMs** (*Large Language Models*, ou "Grandes Modelos de Linguagem") são treinadas com enormes quantidades de texto para aprender padrões da linguagem e gerar respostas de acordo com o contexto. Entre outras coisas, aprendem a prever quais tokens podem aparecer em seguida em um texto. É isso que permite responder perguntas, resumir conteúdos, traduzir textos e até ajudar na programação.

Apesar da quantidade de dados, a LLM não funciona apenas guardando tudo o que leu: ela aprende padrões e relações entre as informações. Isso também não garante respostas sempre corretas, já que ela pode interpretar algo de forma equivocada ou gerar informações incorretas.

As **SLMs** (*Small Language Models*, ou "Pequenos Modelos de Linguagem") seguem a mesma ideia, mas geralmente são menores e exigem menos recursos computacionais. Por isso podem ser úteis em computadores mais simples, celulares e aplicações que precisam de menor custo. Um modelo menor também não é necessariamente pior em tudo: o desempenho depende dos dados, do treinamento e da tarefa.

### Conclusão

Uma IA aprende com os dados que recebe no treinamento, identificando padrões e ajustando seus parâmetros para melhorar as respostas. Os tokens ajudam a entender como os modelos de linguagem processam texto, e os parâmetros fazem parte do funcionamento interno do modelo. LLMs e SLMs são modelos de linguagem que diferem principalmente em escala e recursos computacionais.

---

## 3. Entendendo Deep Learning

Para entender o **Deep Learning**, imagine que eu gostei muito do filme *Robô Selvagem* e pedi ao ChatGPT que me recomendasse outros filmes com base nele. Em vez de sugerir só filmes com robôs ou animais selvagens, a IA pode considerar vários aspectos da obra: a história, os personagens, a mensagem, o estilo visual e temas como amizade, família e adaptação.

Com base nessas características, ela pode recomendar filmes com elementos parecidos, mesmo que não sejam sobre robôs. Isso é possível porque os modelos aprendem padrões e relações entre diferentes informações durante o treinamento, e a recomendação não depende só de palavras no título, mas das relações entre os conteúdos.

Esse tipo de capacidade está ligado ao **Deep Learning** (aprendizado profundo), uma área do aprendizado de máquina que usa redes neurais artificiais com várias camadas para aprender padrões complexos a partir de grandes quantidades de dados. Essas redes identificam relações que seriam difíceis de representar manualmente com regras simples.

Isso não quer dizer que a IA sinta emoções ou pense exatamente como um ser humano. Ela aprende padrões nos dados e usa essas relações para gerar respostas que façam sentido no contexto. O Deep Learning ajuda a explicar como a IA lida com informações complexas e encontra semelhanças que vão além do óbvio.

---

## 4. A era das IAs generativas

Até aqui vimos como as IAs aprendem padrões nos dados e os usam para interpretar perguntas, reconhecer imagens e produzir respostas. Mas, se uma IA identifica padrões, será que ela também consegue criar algo novo? É aí que entram as **IAs generativas**.

"Generativa" quer dizer capaz de gerar, produzir, dar origem a algo. Essas IAs não se limitam a identificar informações que já existem: também geram conteúdos novos, como textos, imagens, músicas, vídeos e até código de programação.

Por exemplo, para criar a imagem de uma maçã, não preciso dar uma fotografia e pedir para modificá-la. Posso só escrever um comando, como "Crie uma imagem de uma maçã vermelha sobre uma mesa de madeira". A IA usa os padrões que aprendeu no treinamento para gerar uma imagem que corresponda à descrição, mesmo sem uma foto de referência. Ela combina formatos, cores, texturas, iluminações e posições de acordo com o que foi pedido.

Isso não significa que ela crie algo literalmente do zero. Ela depende do que aprendeu no treinamento. A diferença é que não precisa copiar um exemplo específico: pode combinar características e chegar a algo diferente dos exemplos usados, embora isso não garanta que toda criação seja totalmente inédita.

As IAs generativas também se baseiam em modelos matemáticos e estatísticos, ou seja, continuam trabalhando com probabilidades. Elas usam o que aprenderam para gerar conteúdo conforme o contexto e as instruções recebidas.

### Conclusão

As IAs generativas representam um avanço importante porque permitem não só analisar informações, mas também produzir conteúdo novo a partir delas. Isso abriu espaço para aplicações que vão da criação de imagens e músicas à produção de textos, vídeos e ferramentas de programação, ampliando o uso da Inteligência Artificial no dia a dia.