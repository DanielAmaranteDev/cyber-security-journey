# Bandit Level 0

Para concluir o nível 0 foi necessário ter uma noção básica sobre **SSH (Secure Shell)**. SSH é um protocolo de rede que permite acessar e controlar computadores e servidores remotamente por meio da linha de comando, de forma segura e criptografada.

No desafio foram fornecidos o usuário (`bandit0`), o servidor (`bandit.labs.overthewire.org`) e a porta (`2220`). Com essas informações, bastou executar o comando SSH no terminal:

```bash
ssh usuario@servidor -p porta
```

No caso do desafio:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

Após executar o comando, foi solicitada a senha do nível:

```text
bandit0
```

Depois de acessar o servidor, utilizei o comando `ls` para listar os arquivos do diretório atual e verificar onde eu estava. Em seguida, encontrei o arquivo `readme` e usei o comando:

```bash
cat readme
```

para exibir seu conteúdo. Dentro dele estava a senha necessária para acessar o próximo nível:

```text
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

### Comandos aprendidos

- Conectar a um servidor via SSH:

```bash
ssh usuario@servidor -p porta
```

- Listar arquivos do diretório atual:

```bash
ls
```

- Exibir o conteúdo de um arquivo:

```bash
cat nome-do-arquivo
```