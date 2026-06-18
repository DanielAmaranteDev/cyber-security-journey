# Bandit Level 1

Para concluir o nível 1 foi necessário ter uma noção básica sobre **SSH (Secure Shell)** e sobre o **Terminal Unix/Linux**. O SSH é um protocolo de rede que permite acessar e controlar computadores e servidores remotamente por meio da linha de comando, de forma segura e criptografada. Já o terminal Unix/Linux é uma interface de texto que permite interagir diretamente com o sistema operacional, executando comandos para gerenciar arquivos, diretórios e processos.

Neste desafio, o processo de conexão foi praticamente o mesmo do nível anterior, alterando apenas o usuário utilizado no comando SSH.

Foram fornecidos o usuário (`bandit1`), o servidor (`bandit.labs.overthewire.org`) e a porta (`2220`). Com essas informações, bastou executar o comando:

```bash
ssh usuario@servidor -p porta
```

No caso do desafio:

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

Após executar o comando, foi solicitada a senha obtida no nível anterior:

```text
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

Depois de acessar o servidor, utilizei o comando `ls` para listar os arquivos presentes no diretório atual. Foi então possível identificar um arquivo chamado `-`.

Minha primeira tentativa foi visualizar seu conteúdo usando:

```bash
cat -
```

Porém, o comando não funcionou como esperado. Isso acontece porque, em sistemas Unix/Linux, o caractere `-` normalmente é interpretado como uma opção (flag) de um comando ou como uma referência à entrada padrão (stdin), e não como um nome de arquivo.

Quando um arquivo possui um nome que começa com um traço, é necessário informar explicitamente ao terminal que se trata de um caminho de arquivo. Uma forma de fazer isso é utilizando `./`, que representa o diretório atual:

```bash
cat ./-
```

Outra alternativa é utilizar redirecionamento de entrada:

```bash
cat < -
```

Após executar o comando corretamente, foi possível visualizar o conteúdo do arquivo e obter a senha necessária para acessar o próximo nível:

```text
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

### Conceitos aprendidos

- Como acessar um servidor remoto utilizando SSH.
- Como listar arquivos em um diretório com o comando `ls`.
- Como visualizar o conteúdo de arquivos utilizando o comando `cat`.
- Como lidar com arquivos que possuem nomes iniciados por `-`, evitando que sejam interpretados como opções de comandos.

### Comandos utilizados

Conectar a um servidor via SSH:

```bash
ssh usuario@servidor -p porta
```

Listar arquivos do diretório atual:

```bash
ls
```

Exibir o conteúdo de um arquivo:

```bash
cat nome-do-arquivo
```

Exibir o conteúdo de um arquivo chamado `-`:

```bash
cat ./-
```