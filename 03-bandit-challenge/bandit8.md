# Bandit Level 8

Para concluir o nível 8 foi necessário aprender a utilizar os comandos `sort` e `uniq` em conjunto para identificar uma linha que aparecia apenas uma vez em um arquivo contendo milhares de registros.

O enunciado informava que a senha do próximo nível estava armazenada em uma linha única dentro do arquivo `data.txt`, ou seja, uma linha que aparecia apenas uma vez enquanto todas as demais estavam duplicadas.

Ao acessar a conta, utilizei:

```bash
ls -a
```

para verificar os arquivos disponíveis no diretório atual e confirmar a presença do arquivo `data.txt`.

Antes de resolver o desafio, consultei a documentação dos comandos que provavelmente seriam necessários:

```bash
sort --help
```

e

```bash
uniq --help
```

O comando `sort` é utilizado para ordenar linhas de texto, enquanto o comando `uniq` é utilizado para identificar ou remover linhas repetidas.

Ao ler a documentação do `uniq`, observei uma informação importante:

> O comando `uniq` só consegue identificar linhas repetidas quando elas estão lado a lado.

Isso significa que, caso existam linhas iguais espalhadas em diferentes partes do arquivo, o `uniq` não será capaz de detectá-las corretamente. Por esse motivo, primeiro foi necessário ordenar o arquivo utilizando o comando `sort`.

Para resolver o desafio, executei:

```bash
sort data.txt | uniq -u
```

Neste comando:

* `sort data.txt` ordena todas as linhas do arquivo em ordem alfabética, agrupando as linhas iguais umas ao lado das outras.
* O símbolo `|` (pipe) envia a saída de um comando diretamente para outro comando.
* `uniq -u` exibe apenas as linhas que aparecem uma única vez.

Ao executar o comando, o sistema retornou:

```text
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

Como essa era a única linha não repetida do arquivo, ela correspondia à senha necessária para acessar o próximo nível.

## Conceitos aprendidos

* Como utilizar o comando `sort` para ordenar dados.
* Como utilizar o comando `uniq` para identificar linhas repetidas ou únicas.
* Por que o `uniq` exige que linhas iguais estejam adjacentes.
* Como utilizar o operador `|` (*pipe*) para conectar a saída de um comando à entrada de outro.
* Como combinar múltiplos comandos para resolver problemas de forma eficiente.

## Comandos utilizados

Ordenar as linhas de um arquivo:

```bash
sort arquivo.txt
```

Exibir apenas linhas únicas:

```bash
uniq -u arquivo.txt
```

Combinar os comandos para encontrar uma linha não repetida:

```bash
sort data.txt | uniq -u
```
