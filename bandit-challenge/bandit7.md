# Bandit Level 7

Para concluir o nível 7 foi necessário aprender a utilizar o comando `grep`, uma das ferramentas mais importantes do Linux para pesquisar palavras, padrões e informações específicas dentro de arquivos de texto.

O enunciado informava que a senha do próximo nível estava armazenada no arquivo `data.txt`, ao lado da palavra:

```text
millionth
```

Ao acessar a conta, utilizei:

```bash
ls -a
```

O comando `ls` lista os arquivos de um diretório, enquanto a opção `-a` também exibe arquivos ocultos. Dessa forma, foi possível identificar o arquivo `data.txt`, que continha os dados necessários para o desafio.

Antes de realizar a busca, consultei a documentação do comando:

```bash
grep --help
```

O parâmetro `--help` exibe um resumo das opções disponíveis para o comando. Ao analisar a documentação, observei que o `grep` é utilizado para procurar padrões de texto dentro de arquivos.

Como o desafio informava exatamente qual palavra deveria ser encontrada, utilizei:

```bash
grep "millionth" data.txt
```

O comando `grep` procura ocorrências de um determinado padrão dentro de um arquivo.

Nesse caso:

* `"millionth"` é o texto que está sendo procurado.
* `data.txt` é o arquivo onde a busca será realizada.

O `grep` percorreu todas as linhas do arquivo e exibiu apenas aquela que continha a palavra pesquisada.

O resultado foi:

```text
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

Como a senha estava localizada ao lado da palavra `millionth`, foi possível identificar a senha do próximo nível:

```text
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

## Conceitos aprendidos

* Como consultar rapidamente a documentação de um comando utilizando `--help`.
* Como utilizar o comando `grep` para localizar informações específicas dentro de arquivos.
* Como pesquisar palavras ou padrões em grandes volumes de texto.
* Como filtrar a saída de um arquivo para exibir apenas as linhas relevantes.

## Comandos utilizados

Listar arquivos do diretório:

```bash
ls -a
```

Consultar a ajuda do comando:

```bash
grep --help
```

Pesquisar uma palavra dentro de um arquivo:

```bash
grep "palavra" arquivo.txt
```

sort = agrupa
uniq = remove repetições adjacentes