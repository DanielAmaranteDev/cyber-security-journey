FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey# Bandit Level 9

Para concluir o nível 9 foi necessário aprender a utilizar o comando `strings`, que permite extrair textos legíveis dentro de arquivos que não são necessariamente estruturados como texto puro, além de combinar esse comando com `grep` para filtrar apenas as informações relevantes.

O enunciado informava que a senha estava escondida dentro do arquivo `data.txt`, porém esse arquivo continha muitos caracteres “misturados”, dificultando a leitura direta.

Ao acessar a conta, verifiquei os arquivos disponíveis:

```bash id="v8kq2p"
ls -a
```

A opção `-a` permite visualizar também arquivos ocultos. Com isso, confirmei a presença do arquivo `data.txt`, que seria o alvo do desafio.

Antes de resolver, consultei a documentação do comando que parecia adequado:

```bash id="s1d9pw"
strings --help
```

O comando `strings` é utilizado para extrair sequências de caracteres legíveis dentro de arquivos binários ou arquivos com conteúdo não estruturado. Ele ignora bytes não imprimíveis e exibe apenas textos que fazem sentido em ASCII.

A partir disso, utilizei o comando:

```bash id="kq8m0a"
strings data.txt | grep '^='
```

Neste comando:

* `strings data.txt` extrai todas as sequências de texto legíveis dentro do arquivo.
* O operador `|` (pipe) envia essa saída diretamente para o próximo comando.
* `grep '^='` filtra apenas as linhas que começam com o caractere `=`.

A escolha desse filtro foi baseada na observação de que as informações relevantes do desafio estavam destacadas visualmente por esse padrão.

Ao executar o comando, a saída apresentou a linha contendo a senha do próximo nível:

```text id="z9p2qx"
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

Dessa forma, foi possível identificar a senha correta.

## Conceitos aprendidos

* Como utilizar o comando `strings` para extrair texto legível de arquivos binários ou mistos.
* Como filtrar resultados utilizando o `grep`.
* Como combinar comandos com o operador `|` (pipe).
* Como identificar padrões visuais em saídas de comandos para facilitar a filtragem de informações.

## Comandos utilizados

Listar arquivos do diretório:

```bash id="a91kqz"
ls -a
```

Consultar ajuda do comando strings:

```bash id="m2x8lp"
strings --help
```

Extrair textos e filtrar padrões:

```bash id="n7wq0d"
strings data.txt | grep '^='
```
