# Bandit Level 4

Para concluir o nível 4 foi necessário aprender a identificar diferentes tipos de arquivos utilizando ferramentas do próprio sistema Linux.

Após conectar ao servidor com o usuário `bandit4` e acessar o diretório `inhere`, encontrei diversos arquivos com nomes semelhantes:

```text
-file00  -file01  -file02  -file03  -file04
-file05  -file06  -file07  -file08  -file09
```

O desafio informava que a senha estava armazenada no único arquivo legível por humanos. Como não era possível descobrir isso apenas observando os nomes dos arquivos, foi necessário utilizar o comando `file`.

utilizei:

```bash
file ./*
```

O comando `file` analisa o conteúdo de um arquivo e tenta identificar seu tipo. Diferentemente do comando `ls`, que apenas mostra nomes, o `file` examina os dados armazenados para informar se o arquivo é texto, binário, imagem, executável ou outro formato.

O resultado mostrou que a maioria dos arquivos continha apenas dados binários (`data`), enquanto alguns foram identificados como arquivos de texto:

```text
./-file05: Non-ISO extended-ASCII text
./-file07: ASCII text
```

Como o desafio indicava que a senha estava em um arquivo legível por humanos, o arquivo identificado como `ASCII text` era o candidato mais provável.

Para visualizar seu conteúdo, utilizei:

```bash
cat ./-file07
```

O comando `cat` exibe o conteúdo de um arquivo diretamente no terminal. O prefixo `./` foi necessário porque o nome do arquivo começa com um traço (`-`), caractere que normalmente é interpretado pelo terminal como uma opção de comando.

Ao exibir o conteúdo do arquivo, encontrei a senha necessária para acessar o próximo nível:

```text
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

### Conceitos aprendidos

* Como listar todos os arquivos de um diretório utilizando curingas (`*`).
* Como utilizar o comando `file` para identificar tipos de arquivos.
* Diferença entre arquivos de texto e arquivos binários.
* Como localizar informações em arquivos legíveis por humanos.
* Como acessar arquivos cujos nomes começam com o caractere `-`.

### Comandos utilizados

Conectar ao servidor via SSH:

```bash
ssh usuario@servidor -p porta
```

Entrar em um diretório:

```bash
cd nome-do-diretorio
```

Listar todos os arquivos do diretório atual:

```bash
ls ./*
```

Identificar o tipo de cada arquivo:

```bash
file ./*
```

Exibir o conteúdo de um arquivo:

```bash
cat ./nome-do-arquivo
```
