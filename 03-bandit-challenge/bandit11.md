# Bandit Level 11

Para concluir o nível 11 foi necessário aprender a utilizar o comando `tr` (*translate*), uma ferramenta capaz de substituir caracteres por outros seguindo um padrão definido.

O enunciado informava que a senha estava armazenada no arquivo `data.txt` e que todos os caracteres haviam sido codificados utilizando **ROT13**.

ROT13 é uma técnica simples de substituição em que cada letra do alfabeto é deslocada 13 posições. Por exemplo:

```text
A → N
B → O
C → P
```

Como o alfabeto possui 26 letras, aplicar ROT13 duas vezes retorna o texto original.

Ao acessar a conta, verifiquei os arquivos disponíveis:

```bash
ls -a
```

e confirmei a existência do arquivo `data.txt`.

Antes de resolver o desafio, consultei a documentação do comando que seria utilizado:

```bash
tr --help
```

A documentação mostrou que o comando `tr` pode traduzir caracteres de um conjunto para outro. Essa funcionalidade é ideal para desfazer a codificação ROT13.

Para decodificar o conteúdo do arquivo, utilizei:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

Neste comando:

* `cat data.txt` exibe o conteúdo do arquivo.
* O operador `|` (*pipe*) envia essa saída para o próximo comando.
* `tr 'A-Za-z' 'N-ZA-Mn-za-m'` substitui cada letra do alfabeto pela correspondente na posição deslocada em 13 caracteres.

O primeiro conjunto:

```text
A-Za-z
```

representa todas as letras maiúsculas e minúsculas.

O segundo conjunto:

```text
N-ZA-Mn-za-m
```

representa o alfabeto rotacionado em 13 posições.

Ao executar o comando, o texto foi decodificado e o terminal exibiu:

```text
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

Dessa forma, foi possível obter a senha necessária para acessar o próximo nível.

## Conceitos aprendidos

* O que é a codificação ROT13.
* Como utilizar o comando `tr` para traduzir caracteres.
* Como combinar comandos utilizando o operador `|` (*pipe*).
* Como processar e transformar texto diretamente pelo terminal.
* Como consultar rapidamente a documentação de um comando utilizando `--help`.

## Comandos utilizados

Consultar a ajuda do comando:

```bash
tr --help
```

Exibir o conteúdo de um arquivo:

```bash
cat data.txt
```

Decodificar um texto utilizando ROT13:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
