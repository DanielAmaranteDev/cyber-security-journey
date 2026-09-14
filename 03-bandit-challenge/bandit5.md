# Bandit Level 5

Para concluir o nível 5 foi necessário aprender a utilizar o comando `find` para localizar arquivos com características específicas dentro de uma estrutura de diretórios.

O enunciado informava que a senha estava armazenada em um arquivo que possuía três características:

* Legível para humanos
* Possuía exatamente **1033 bytes**.
* Não era executável.

Ao acessar o diretório `inhere`, encontrei diversos subdiretórios chamados `maybehere00`, `maybehere01`, `maybehere02` e assim por diante. Como procurar manualmente em todos eles seria um processo demorado, utilizei o comando:

```bash
find . -type f -size 1033c
```

O comando `find` realiza buscas em diretórios e subdiretórios. Nesse caso:

* `.` indica que a busca deve começar no diretório atual.
* `-type f` restringe os resultados apenas a arquivos comuns.
* `-size 1033c` procura arquivos com exatamente 1033 bytes (`c` representa bytes).

O resultado da busca foi:

```text
./maybehere07/.file2
```

Isso indicava exatamente qual arquivo atendia aos critérios informados pelo desafio.

Em seguida, acessei o diretório onde o arquivo estava localizado:

```bash
cd ./maybehere07
```

Para examinar melhor os arquivos presentes, utilizei:

```bash
ls -la
```

O comando `ls` lista os arquivos de um diretório. A opção `-l` exibe informações detalhadas sobre cada arquivo, incluindo permissões, proprietário, grupo e tamanho, enquanto a opção `-a` também mostra os arquivos ocultos, que possuem nomes iniciados por um ponto (`.`).

Como o desafio informava que a senha estava armazenada em um arquivo **não executável**, analisei as permissões exibidas pelo comando. Os arquivos que possuíam a permissão `x` eram executáveis, enquanto aqueles que apresentavam apenas permissões de leitura e escrita (`rw`) não eram executáveis.

Após identificar os arquivos que atendiam a esse requisito, utilizei o comando:

```bash
file nome-do-arquivo
```

O comando `file` analisa o conteúdo de um arquivo e informa seu tipo e algumas características adicionais, como o formato do texto e o tamanho aproximado das linhas.

Comparando os resultados obtidos, percebi que um dos arquivos possuía cerca de 1000 caracteres, valor compatível com a informação fornecida pelo desafio de que o arquivo correto teria exatamente 1033 bytes.

Dessa forma, identifiquei que o arquivo correto era:

```text
.file2
```

Por fim, utilizei:

```bash
cat .file2
```

O comando `cat` exibe o conteúdo de um arquivo diretamente no terminal.

Ao visualizar o conteúdo do arquivo, encontrei a senha necessária para acessar o próximo nível:

```text
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

### Conceitos aprendidos

* Como utilizar o comando `find` para localizar arquivos com características específicas.
* Como buscar arquivos pelo tamanho utilizando a opção `-size`.
* Como restringir buscas para arquivos comuns utilizando `-type f`.
* Como visualizar informações detalhadas sobre arquivos com `ls -la`.
* Como identificar o tipo de um arquivo utilizando o comando `file`.
* Como visualizar o conteúdo de arquivos utilizando o comando `cat`.

### Comandos utilizados

Conectar ao servidor via SSH:

```bash
ssh usuario@servidor -p porta
```

Entrar em um diretório:

```bash
cd nome-do-diretorio
```

Localizar arquivos por tamanho:

```bash
find . -type f -size 1033c
```

Listar arquivos com detalhes e exibir arquivos ocultos:

```bash
ls -la
```

Identificar o tipo de um arquivo:

```bash
file nome-do-arquivo
```

Exibir o conteúdo de um arquivo:

```bash
cat nome-do-arquivo
```