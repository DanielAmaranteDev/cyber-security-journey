## 1. Como os modelos de linguagem "entendem" um prompt

Os Modelos de Linguagem de Grande Escala (LLMs) são treinados com enormes volumes de texto, mas não entendem a linguagem como uma pessoa. O que eles fazem é calcular probabilidades com base nos padrões aprendidos no treinamento. A base disso é a arquitetura Transformer, apresentada no artigo "Attention Is All You Need" (Vaswani et al., 2017). Ela usa mecanismos de atenção para avaliar cada palavra em relação a todas as outras do texto, em vez de ler de forma estritamente linear como os modelos anteriores faziam. Por isso o modelo capta melhor o contexto do prompt e responde de forma mais coerente.

O curso usa a analogia de um editor experiente. Na frase "Ana pegou o livro porque achou interessante", ele não lê só palavra por palavra: volta ao texto para saber quem é Ana e por que o livro seria interessante. A atenção do Transformer faz algo parecido, destacando automaticamente os trechos mais relevantes para cada parte da frase.

Antes de tudo isso, o prompt é quebrado em tokens, que podem ser palavras, pedaços de palavras ou até caracteres. No exemplo do curso, a frase "A DIO é a primeira plataforma Open Education brasileira dedicada a tornar o conhecimento em tecnologias exponenciais acessível a todos." virou 24 tokens no Tokenizer da OpenAI, com os modelos GPT-4 e GPT-4 Mini. Os tokens são convertidos em embeddings, que são representações vetoriais do significado, e passam pelas camadas do Transformer. No fim, o modelo gera uma distribuição de probabilidade para o próximo token e repete o processo até completar a resposta.

Sobre memória, em geral o modelo não guarda nada entre interações. Dentro de uma conversa ele mantém o contexto pela janela de contexto, que é o limite de tokens que consegue processar ao mesmo tempo. Quando esse limite é atingido, os tokens mais antigos são descartados para abrir espaço aos novos. A analogia do curso é a lousa de uma sala de aula: o espaço é limitado, então o professor apaga o que escreveu primeiro para continuar escrevendo.

O exemplo mostra isso na prática. Perguntar "Em poucas palavras, o que é Aliança?" gera uma resposta genérica, sobre acordo entre partes. Depois de perguntar "O que é Azeroth?", repetir a pergunta sobre a Aliança faz o modelo responder que é uma das duas principais facções de World of Warcraft, porque a conversa anterior ainda está na janela de contexto. Se a conversa passar do limite, o começo se perde, e os pontos importantes precisam ser reforçados.

Ferramentas como o ChatGPT também oferecem personalização, com memória e instruções personalizadas, que guardam algumas informações entre os chats ou seguem diretrizes definidas pelo usuário.

## 2. Elementos essenciais de um bom prompt

O curso divide um bom prompt em cinco elementos e usa como exemplo a criação de uma história para uma campanha de RPG de mesa.

A instrução é a tarefa em si, dita de forma direta e sem ambiguidade. O contexto traz as informações que ajudam o modelo a entender a situação: no exemplo, uma maldição que impede qualquer um de sair da cidade, moradores desaparecendo, sombras ganhando vida e jogadores que chegaram pouco antes em busca de tesouros. Os exemplos orientam o formato ou o estilo esperado, como sugerir que a história comece com um ataque de sombras e leve a uma taberna onde um contador de histórias fala de uma relíquia perdida. Os dados de entrada são o material específico a ser trabalhado, aqui os personagens do grupo e o vilão encapuzado. O formato da saída define o que se espera da resposta, como o tamanho e a estrutura.

Juntando os cinco, o prompt completo fica assim:

```
Crie uma história inicial para uma campanha de RPG de fantasia, envolvendo um grupo de aventureiros presos em uma cidade amaldiçoada.

A cidade foi tomada por uma maldição que impede qualquer um de sair. Os moradores estão desaparecendo misteriosamente, e as sombras parecem ganhar vida. Os jogadores são aventureiros que chegaram à cidade pouco antes da maldição começar, em busca de tesouros escondidos.

Por exemplo, a história pode começar com os aventureiros sendo atacados por sombras vivas na entrada da cidade, forçando-os a buscar refúgio na taberna local. Lá, eles encontram um velho contador de histórias que fala sobre uma relíquia perdida que pode quebrar a maldição.

Os aventureiros incluem: um ladino sarcástico, um clérigo com uma conexão misteriosa com as sombras, um bárbaro impulsivo e um mago que busca conhecimento proibido. O vilão principal é uma figura encapuzada que manipula a maldição das sombras.

A história deve ter de 2 a 3 parágrafos, começando com uma introdução impactante, seguida pelo primeiro desafio e um gancho final que motive os jogadores a explorar a cidade.
```

Com tudo isso, o modelo devolveu uma história passada na cidade de Nocturnis, com o ataque das sombras, a fuga para a taberna, o contador de histórias e o vilão encapuzado, dentro do formato pedido.

## 3. Engenharia de prompts no dia a dia

A IA já estava presente no cotidiano em recomendações personalizadas e assistentes virtuais, mas a possibilidade de conversar com ela de forma natural facilitou o uso por qualquer pessoa e levou as aplicações para além da área de tecnologia. Hoje ela aparece em atendimento ao cliente, criação de conteúdo, automação de tarefas e até nas áreas jurídica e financeira. Isso torna a engenharia de prompts uma habilidade cada vez mais útil.

O curso traz dois exemplos de uso pessoal e profissional. O primeiro é o planejamento de metas pessoais: um plano de desenvolvimento de 6 meses em escultura em biscuit, com 5 horas semanais disponíveis e R$ 150,00 por mês, pedindo metas específicas e mensuráveis, recursos de aprendizado dentro do orçamento, cronograma semanal, métricas de acompanhamento e possíveis obstáculos com estratégias para superá-los.

O segundo é a preparação para entrevistas de emprego, com uma simulação para o cargo de Arquiteto Pleno. O prompt informa o perfil do candidato, a descrição da vaga, a empresa e o nível de senioridade, e organiza a conversa em passos: o modelo faz uma pergunta, o usuário responde, o modelo dá um feedback detalhado (o que foi bom, o que pode melhorar, sugestões com exemplos e dicas de desempenho) e segue com uma pergunta por vez.

## 4. Cuidados na aplicação de prompts

Como os modelos aprendem com grandes volumes de dados, eles podem repetir vieses e erros presentes nesses dados, o que afeta a qualidade e a imparcialidade das respostas. Por isso organizações e profissionais vêm adotando práticas de IA responsável, que envolvem imparcialidade, confiabilidade, segurança, privacidade, inclusão, transparência e responsabilidade.

Os prompts também podem ser enviesados, quando a pergunta já induz a resposta e limita a diversidade de opiniões. "Por que o café é a melhor bebida de todos os tempos?" assume a conclusão de antemão. A versão imparcial seria "Quais são as vantagens e desvantagens do café em comparação com outras bebidas?".

As alucinações acontecem quando a ferramenta gera informações erradas ou inventadas, muitas vezes tentando preencher lacunas. Um pedido como "Descreva os segredos escondidos no fundo do oceano, onde se encontram criaturas fantásticas" convida o modelo a inventar descobertas que não existem, com uma resposta convincente mas não necessariamente verdadeira. Perguntar pelos "principais estudos sobre a biodiversidade nas regiões mais profundas do oceano" dá uma base mais concreta, e mesmo assim vale verificar o conteúdo.

Em privacidade e segurança, a recomendação é não compartilhar dados pessoais ou confidenciais em prompts. Quando for preciso dar contexto, dá para anonimizar, usando "Pessoa A" no lugar de um nome real, e vale consultar a Política de Privacidade e os Termos de Uso do serviço.

### Conclusão

Este módulo mostrou que um modelo de linguagem não entende o texto como uma pessoa: ele trabalha com tokens, atenção e probabilidades, e só enxerga o que cabe na janela de contexto. Por isso a qualidade da resposta depende bastante do prompt, e vale montar o pedido com instrução, contexto, exemplos, dados de entrada e formato de saída. Também ficam os cuidados de não induzir a resposta na pergunta, conferir o que o modelo afirma e não colocar dados pessoais no prompt.