# Bandit Level 3

Para concluir o nível 3 foi necessário aprender sobre **arquivos ocultos no Linux**. Em sistemas Unix/Linux, arquivos e diretórios cujo nome começa com um ponto (`.`) são considerados ocultos e, por padrão, não aparecem quando utilizamos o comando `ls`.

Assim como nos níveis anteriores, realizei a conexão ao servidor utilizando SSH com o usuário `bandit3` e a senha obtida no nível anterior.

Após acessar o servidor, utilizei o comando:

```bash
ls
```

para listar os arquivos e diretórios presentes no diretório atual. Foi possível identificar um diretório chamado `inhere`.

Para acessá-lo, utilizei:

```bash
cd inhere
```

Ao listar os arquivos novamente utilizando apenas `ls`, nenhum arquivo visível apareceu. Como o enunciado informava que a senha estava armazenada em um arquivo oculto, utilizei a opção `-a` do comando `ls`, que exibe todos os arquivos, incluindo os ocultos:

```bash
ls -a
```

O resultado exibiu os diretórios especiais `.` e `..`, além do arquivo oculto:

```text
...Hiding-From-You
```

Em seguida, utilizei o comando:

```bash
cat ...Hiding-From-You
```

para visualizar o conteúdo do arquivo.

Inicialmente, tentei executar:

```bash
cat . .. ...Hiding-From-You
```

Porém, os itens `.` e `..` representam diretórios especiais do sistema (`diretório atual` e `diretório pai`), e o comando `cat` não pode exibir o conteúdo de diretórios. Por isso foram exibidas mensagens de erro para esses dois itens. Ainda assim, como o terceiro argumento era um arquivo válido, o comando exibiu corretamente o conteúdo dele.

Dentro do arquivo estava a senha necessária para acessar o próximo nível:

```text
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

### Conceitos aprendidos

* O que são arquivos ocultos no Linux.
* Como utilizar o comando `ls -a` para visualizar arquivos ocultos.
* O significado dos diretórios especiais `.` (diretório atual) e `..` (diretório pai).
* Como utilizar o comando `cd` para navegar entre diretórios.
* Como visualizar o conteúdo de arquivos utilizando o comando `cat`.

### Comandos utilizados

Conectar ao servidor via SSH:

```bash
ssh usuario@servidor -p porta
```

Listar arquivos visíveis:

```bash
ls
```

Listar todos os arquivos, incluindo os ocultos:

```bash
ls -a
```

Entrar em um diretório:

```bash
cd nome-do-diretorio
```

Exibir o conteúdo de um arquivo:

```bash
cat nome-do-arquivo
```
