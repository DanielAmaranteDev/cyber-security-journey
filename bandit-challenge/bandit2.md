# Bandit Level 2

Para concluir o nível 2 foi necessário reforçar os conhecimentos básicos sobre o **Terminal Unix/Linux**, especialmente sobre como o sistema interpreta nomes de arquivos que contêm caracteres especiais.

Assim como nos níveis anteriores, realizei a conexão ao servidor utilizando SSH com o usuário `bandit2` e a senha obtida no nível anterior.

Após acessar o servidor, utilizei o comando:

```bash
ls
```

para listar os arquivos presentes no diretório atual. Foi então identificado um arquivo com o seguinte nome:

```text
--spaces in this filename--
```

Minha primeira tentativa foi utilizar o comando `cat` diretamente para visualizar seu conteúdo. No entanto, isso não funcionou porque o nome do arquivo possuía espaços e também começava com o caractere `-`, que normalmente é interpretado pelo terminal como uma opção (flag) de comando.

Em sistemas Unix/Linux, quando um nome de arquivo contém espaços, é necessário colocá-lo entre aspas para que todo o texto seja interpretado como um único argumento. Além disso, como o nome começava com `-`, utilizei `./` para indicar explicitamente que se tratava de um arquivo localizado no diretório atual.

O comando correto foi:

```bash
cat "./--spaces in this filename--"
```

Após executar o comando, foi possível visualizar o conteúdo do arquivo e obter a senha necessária para acessar o próximo nível:

```text
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

### Conceitos aprendidos

- Como trabalhar com arquivos que possuem espaços no nome.
- Como utilizar aspas para que o terminal interprete um nome com espaços como um único argumento.
- Como utilizar `./` para indicar que um nome iniciado por `-` deve ser tratado como um arquivo e não como uma opção de comando.
- Como combinar diferentes técnicas para acessar arquivos com nomes considerados "especiais" pelo terminal.

### Comandos utilizados

Listar arquivos do diretório atual:

```bash
ls
```

Exibir o conteúdo de um arquivo com espaços no nome:

```bash
cat "./--spaces in this filename--"
```