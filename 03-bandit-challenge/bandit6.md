# Bandit Level 6

Para concluir o nível 6 foi necessário aprofundar o uso do comando `find`, aprendendo a realizar buscas utilizando múltiplos critérios simultaneamente e a consultar a documentação dos comandos de forma mais eficiente.

O enunciado informava que a senha estava armazenada em um arquivo que possuía as seguintes características:

* Tinha exatamente **33 bytes**.
* Pertencia ao usuário **bandit7**.
* Pertencia ao grupo **bandit6**.

Ao explorar o diretório pessoal do usuário, percebi que não havia nenhum arquivo relacionado ao desafio. Como seria inviável procurar manualmente em todo o sistema, a solução era utilizar o comando `find`.

Antes de executar a busca, consultei a documentação para descobrir quais opções permitiam filtrar arquivos por usuário e grupo. Em vez de ler toda a documentação, utilizei o comando:

```bash
find --help | grep user
```

O comando `grep` é utilizado para procurar palavras ou padrões em textos. Nesse caso, ele filtrou a saída do `find --help`, exibindo apenas as linhas que continham a palavra `user`.

A saída mostrou a opção:

```text
-user NAME
```

que permite procurar arquivos pertencentes a um usuário específico.

Em seguida, utilizei:

```bash
find --help | grep group
```

para localizar informações relacionadas a grupos. Dessa forma, encontrei a opção:

```text
-group NAME
```

que permite filtrar arquivos pertencentes a um grupo específico.

Após identificar os parâmetros necessários, executei:

```bash
find ./ -size 33c -user bandit7 -group bandit6
```

O comando `find` percorre recursivamente diretórios e subdiretórios em busca de arquivos que correspondam aos critérios informados.

Nesse caso:

* `./` indica que a busca deve começar no diretório atual.
* `-size 33c` procura arquivos com exatamente 33 bytes (`c` significa bytes).
* `-user bandit7` restringe os resultados aos arquivos pertencentes ao usuário `bandit7`.
* `-group bandit6` restringe os resultados aos arquivos pertencentes ao grupo `bandit6`.

Como o sistema possui diversos diretórios protegidos, a busca retornou muitas mensagens de erro relacionadas à falta de permissão de acesso. Para ocultar essas mensagens e visualizar apenas os resultados úteis, utilizei:

```bash
find ./ -size 33c -user bandit7 -group bandit6 2>/dev/null
```

O trecho `2>/dev/null` redireciona todas as mensagens de erro para `/dev/null`, um dispositivo especial do Linux que simplesmente descarta qualquer informação recebida.

Com isso, a saída ficou muito mais limpa e exibiu apenas o resultado relevante:

```text
./var/lib/dpkg/info/bandit7.password
```

Após localizar o arquivo correto, utilizei:

```bash
cat ./var/lib/dpkg/info/bandit7.password
```

O comando `cat` exibe o conteúdo de um arquivo diretamente no terminal.

Ao executar o comando, obtive a senha necessária para acessar o próximo nível:

```text
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

## Conceitos aprendidos

* Como utilizar o comando `find` para realizar buscas avançadas.
* Como filtrar arquivos por tamanho, usuário e grupo.
* Como consultar a documentação de um comando utilizando `--help`.
* Como utilizar `grep` para localizar rapidamente informações específicas dentro de uma documentação extensa.
* Como ocultar mensagens de erro utilizando `2>/dev/null`.
* Como visualizar o conteúdo de arquivos utilizando o comando `cat`.

## Comandos utilizados

Consultar opções relacionadas a usuários:

```bash
find --help | grep user
```

Consultar opções relacionadas a grupos:

```bash
find --help | grep group
```

Buscar arquivos por tamanho, usuário e grupo:

```bash
find ./ -size 33c -user bandit7 -group bandit6
```

Buscar arquivos ignorando mensagens de erro:

```bash
find ./ -size 33c -user bandit7 -group bandit6 2>/dev/null
```

Exibir o conteúdo de um arquivo:

```bash
cat caminho/do/arquivo
```
