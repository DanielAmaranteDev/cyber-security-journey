# Bandit Level 10

Para concluir o nível 10 foi necessário aprender a utilizar o comando `base64`, que permite decodificar dados que foram codificados nesse formato.

O enunciado informava que a senha do próximo nível estava armazenada dentro do arquivo `data.txt`, porém esse conteúdo estava codificado em Base64.

Ao acessar a conta, verifiquei os arquivos disponíveis:

```bash id="p2kq9a"
ls -a
```

O comando `ls` lista os arquivos de um diretório, e a opção `-a` permite visualizar também arquivos ocultos. Com isso, confirmei a presença do arquivo `data.txt`.

Antes de executar a solução, consultei a documentação do comando:

```bash id="v9q1ld"
base64 --help
```

O comando `base64` é utilizado para codificar ou decodificar dados no formato Base64, que é um método de representação de dados binários em texto ASCII.

Para resolver o desafio, utilizei a opção de decodificação:

```bash id="m0x7qp"
base64 -d data.txt
```

Neste comando:

* `base64` é o comando responsável por manipular a codificação Base64.
* `-d` indica que a operação deve ser de **decodificação** (decode).
* `data.txt` é o arquivo que contém os dados codificados.

Ao executar o comando, o conteúdo do arquivo foi decodificado e exibiu diretamente a mensagem com a senha do próximo nível:

```text id="k8w1rz"
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

Dessa forma, foi possível obter a senha necessária para avançar para o próximo nível.

## Conceitos aprendidos

* Como identificar dados codificados em Base64.
* Como utilizar o comando `base64` para decodificação de arquivos.
* A diferença entre codificação e decodificação de dados.
* Como ler documentação de comandos utilizando `--help`.

## Comandos utilizados

Listar arquivos do diretório:

```bash id="a8xq3p"
ls -a
```

Consultar ajuda do comando base64:

```bash id="q1m9tw"
base64 --help
```

Decodificar conteúdo de um arquivo:

```bash id="z7p0ld"
base64 -d data.txt
```
