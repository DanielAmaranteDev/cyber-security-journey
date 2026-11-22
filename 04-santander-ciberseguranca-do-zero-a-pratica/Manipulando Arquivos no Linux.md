# Manipulando Arquivos no Linux

Anotações do curso sobre navegação pelo sistema de arquivos, uso do root, gerenciamento de usuários e criação de usuários em lote com script.

## Navegando pelo sistema de arquivos

No Linux, arquivos e diretórios ficam em uma hierarquia que começa na raiz (`/`).

| Símbolo | Significado |
|---|---|
| `/` | Diretório raiz do sistema |
| `~` | Diretório pessoal do usuário |
| `.` | Diretório atual |
| `..` | Diretório acima do atual (diretório pai) |

### Navegação

| Comando | Função |
|---|---|
| `pwd` | Mostra o caminho completo do diretório atual |
| `ls` | Lista os arquivos e diretórios do local atual |
| `ls -la` | Lista também os itens ocultos, em formato detalhado |
| `ls \| more` | Mostra a listagem por partes; `Enter` avança uma linha e `q` sai |
| `cd nome_da_pasta` | Entra em um diretório |
| `cd ..` | Volta para o diretório pai |
| `cd /` | Vai para a raiz do sistema |
| `cd ~` ou `cd` | Vai para o diretório pessoal do usuário |
| `cat arquivo` | Exibe o conteúdo de um arquivo |

O `|` (*pipe*) passa a saída de um comando como entrada do próximo; é assim que o `more` exibe a listagem do `ls` aos poucos.

Os caminhos podem ser absolutos ou relativos:

- **Absolutos:** começam em `/` e indicam o caminho completo, independentemente do diretório atual. Exemplo: `/home/usuario/Downloads`.
- **Relativos:** partem do diretório atual. Exemplo: `Downloads`, se eu já estiver em `/home/usuario`.

### Criação e remoção

| Comando | Função |
|---|---|
| `touch arquivo.txt` | Cria um arquivo vazio ou, se já existir, atualiza sua data de modificação |
| `mkdir pasta` | Cria um diretório |
| `rmdir pasta` | Remove um diretório vazio |
| `rm arquivo.txt` | Remove um arquivo |

**Atenção:** o `rm` apaga direto, sem passar pela lixeira, então vale conferir o caminho antes de executar. A opção `-r` remove diretórios e todo o conteúdo deles, e a `-f` força a remoção sem pedir confirmação. Juntas ficam `rm -rf`, a combinação mais perigosa.

### Pesquisa de arquivos

O `find` procura arquivos e diretórios a partir do local informado:

```bash
find . -name "arquivo.txt"   # a partir do diretório atual
find ~ -name "*.pdf"         # arquivos .pdf dentro do diretório pessoal
```

| Opção | Função |
|---|---|
| `-name` | Pesquisa pelo nome, diferenciando maiúsculas de minúsculas |
| `-iname` | Pesquisa pelo nome, sem diferenciar maiúsculas de minúsculas |
| `-type f` | Pesquisa somente arquivos |
| `-type d` | Pesquisa somente diretórios |

### Ajuda dos comandos

| Recurso | Função |
|---|---|
| `comando --help` | Mostra uma ajuda resumida com opções e formas de uso, quando disponível |
| `man comando` | Abre o manual detalhado do comando; `q` para sair |

```bash
ls --help
man find
```

`--help` é uma opção usada junto a um comando. Já o `man` é um comando que abre a página de manual.

### Para lembrar

O Linux diferencia maiúsculas de minúsculas (*case sensitive*): `Downloads` e `downloads` podem ser nomes diferentes. O diretório atual influencia os comandos com caminho relativo. Não é preciso decorar todas as opções; o importante é entender a finalidade de cada comando e consultar a ajuda quando precisar.

## Terminal, Shell e Bash

Três termos que parecem a mesma coisa, mas não são:

- **Terminal:** a "janela" onde digito o texto. Ele captura o que foi digitado e mostra o resultado.
- **Shell:** o interpretador desse texto. Ele entende o comando e pede ao kernel do sistema operacional que o execute.
- **Bash** (*Bourne Again Shell*): um tipo de shell, o mais comum nas distribuições Linux.

## Executando tarefas administrativas como root

O `sudo` executa um comando com privilégios de administrador. No Ubuntu o usuário root já existe, mas vem sem senha definida, então não dá para entrar nele. Primeiro defino uma senha:

```bash
sudo passwd root
```

Depois o `su` troca para o root (pede a senha que acabei de definir):

```bash
su
```

Terminadas as tarefas como root, volto para o usuário comum:

```bash
su nome_do_usuario
```

Como root, um comando errado pode danificar o sistema, então só vale usá-lo quando necessário. Definir senha para o root é coisa de laboratório: em um sistema real o ideal é mantê-lo sem senha, como o Ubuntu faz por padrão, e usar o `sudo`.

## Gerenciando usuários

Os comandos desta seção precisam ser executados como root (ou com `sudo`).

### Criando e excluindo

| Comando | Função |
|---|---|
| `useradd nome_do_usuario` | Cria um usuário |
| `userdel -f nome_do_usuario` | Exclui um usuário (o `-f` força a exclusão) |

Atenção: o `userdel -f` não apaga a pasta pessoal do usuário, que continua em `/home`.

Do jeito mais simples, o `useradd` também não cria a pasta pessoal nem define o Bash como shell (no Ubuntu o padrão é o `/bin/sh`, mais limitado). Para criar o usuário já com tudo isso:

```bash
useradd joao -m -c "João da Silva" -s /bin/bash
```

| Opção | Função |
|---|---|
| `-m` | Cria a pasta pessoal (home) do usuário |
| `-c` | Define o nome completo do usuário |
| `-s` | Define o shell padrão do usuário |

### Senhas e shell de usuários existentes

| Comando | Função |
|---|---|
| `passwd joao` | Cadastra a senha do usuário; o mesmo comando serve para redefinir |
| `chsh -s /bin/bash joao` | Muda o shell do usuário (*change shell*) |
| `usermod joao -s /bin/bash` | Faz a mesma mudança; o `usermod` serve para alterar contas já existentes |

### Criando o usuário já com senha

Para definir a senha na própria criação, uso a opção `-p`:

```bash
useradd guest -m -c "Convidado1" -s /bin/bash -p $(openssl passwd -crypt senha123)
```

O `-p` espera a senha **já criptografada**: se eu passasse `senha123` direto, o texto puro seria gravado em `/etc/shadow` e o usuário não conseguiria logar. Por isso o `openssl passwd` gera a versão criptografada, e o `$( )` executa esse comando e usa o resultado no lugar.

**Atenção:** nas versões 3.x do OpenSSL (como a do Ubuntu 24.04) a opção `-crypt` não existe mais. O terminal mostra `Unknown option: -crypt`, o `$( )` fica vazio e o `useradd` falha com `option requires an argument -- 'p'`. A alternativa é o `-6`, que gera um hash SHA-512: `$(openssl passwd -6 senha123)`. O `-crypt` também usa um algoritmo antigo e fraco.

## Criando usuários em lote com script

Em vez de repetir o comando na mão, coloco todos em um script. Primeiro crio um diretório para guardá-lo e entro nele:

```bash
mkdir /scripts
cd /scripts
```

Como o `mkdir` usou o caminho absoluto, o `cd` também precisa usar. O `cd scripts` (relativo) só funcionaria se eu já estivesse em `/`.

Depois crio o arquivo com o nano:

```bash
nano criaruser.sh
```

O nano (GNU nano) é um editor de texto simples que roda no terminal e já vem instalado. É o usado no curso porque o Ubuntu Server não tem interface gráfica. O comando abre o arquivo para edição (ele só passa a existir de fato quando eu salvo).

A extensão `.sh` é só convenção. O que faz o arquivo funcionar como script é a primeira linha, que indica o interpretador (aqui, o Bash), e a permissão de execução, mais abaixo. Depois vem, para cada usuário, o `useradd` e, logo abaixo, o `passwd usuario -e`, que obriga a trocar a senha assim que logar. Para criar mais usuários, basta repetir o par de linhas:

```bash
#!/bin/bash

echo "criando usuários..."

useradd guest10 -m -c "Convidado" -s /bin/bash -p $(openssl passwd -crypt senha123)
passwd guest10 -e

useradd guest11 -m -c "Convidado" -s /bin/bash -p $(openssl passwd -crypt senha123)
passwd guest11 -e

useradd guest12 -m -c "Convidado" -s /bin/bash -p $(openssl passwd -crypt senha123)
passwd guest12 -e

useradd guest13 -m -c "Convidado" -s /bin/bash -p $(openssl passwd -crypt senha123)
passwd guest13 -e

echo "finalizado"
```

A senha `senha123` é provisória e fica em texto puro no script, por isso a troca no primeiro login é obrigatória. Se o `-crypt` der erro, veja a observação sobre o OpenSSL na seção anterior.

Para salvar no nano, `Ctrl+O`; para sair, `Ctrl+X`.

Por padrão, o arquivo criado não tem permissão para ser executado. Libero com:

```bash
chmod +x criaruser.sh
```

E executo (o `./` indica que o script está no diretório atual):

```bash
./criaruser.sh
```

O `echo "finalizado"` aparece mesmo que algum comando tenha falhado no meio do caminho, então vale conferir se os usuários foram mesmo criados.

### echo e touch

O `echo` imprime um texto na tela, e é isso que o script usa para mostrar as mensagens. Combinado com o `>` (como no módulo de Linux Fundamentals), esse texto vai para um arquivo em vez da tela. Já o `touch` cria um arquivo vazio ou, se ele já existir, só atualiza a data de modificação.

## Grupos de usuários

Para testar, crio uma usuária nova (o mesmo comando de antes, com a mesma observação sobre o `-crypt`):

```bash
useradd maria -m -c "Maria dos Santos" -s /bin/bash -p $(openssl passwd -crypt senha123)
```

Os grupos que já existem ficam listados em `/etc/group`:

```bash
cat /etc/group
```

Entre eles aparecem o `sudo` e o `adm`. Se eu logasse como maria e tentasse usar o `sudo`, daria erro, porque ela não pertence ao grupo `sudo`, que é o que libera esse uso no Ubuntu. O `adm` é outra coisa: dá acesso à leitura dos logs do sistema, mas não libera o `sudo`.

Para adicioná-la aos grupos, o `usermod --help` mostra as opções:

```bash
usermod -G adm,sudo maria
```

O `-G` (maiúsculo) define os grupos adicionais do usuário, um ou vários, separados por vírgula e sem espaços. Já o `-g` (minúsculo) troca o grupo **principal** do usuário, que não é o que quero aqui.

Também posso criar e excluir meus próprios grupos:

| Comando | Função |
|---|---|
| `groupadd admgroup` | Cria um grupo |
| `groupdel admgroup` | Exclui um grupo |

Um grupo novo nasce sem privilégio nenhum, e o nome `admgroup` é só um nome. As permissões do grupo vêm dos arquivos e diretórios associados a ele (assunto da próxima seção), e todo usuário adicionado ao grupo passa a ter esse acesso. No caso do `sudo`, o que libera o uso é uma regra do arquivo `/etc/sudoers` para o grupo `sudo`.

Supondo que a maria esteja no `sudo` e no `adm` e eu queira colocá-la também no `admgroup`: se eu rodar `usermod -G admgroup maria`, ela sai dos outros dois e fica só no `admgroup`, porque o `-G` substitui a lista de grupos em vez de acrescentar. Com o `usermod` eu teria que listar todos (`usermod -G sudo,adm,admgroup maria`). Para acrescentar ou remover um grupo sem mexer nos demais, existe um comando específico, o `gpasswd`:

| Comando | Função |
|---|---|
| `gpasswd -a maria admgroup` | Adiciona a maria ao `admgroup`; ela continua nos grupos em que já estava |
| `gpasswd -d maria admgroup` | Remove a maria do `admgroup`; ela continua nos demais |

A mudança de grupos só vale para sessões novas: se o usuário já estiver logado, precisa sair e entrar de novo.

## Conhecendo o sistema de permissões

Ao listar um local com `ls -l`, cada linha traz várias informações. Por exemplo:

```text
drwxr-xr-x  19 root root 4620 Nov 21 15:14 dev
```

| Campo | No exemplo | Significado |
|---|---|---|
| Tipo e permissões | `drwxr-xr-x` | O primeiro caractere é o tipo; os outros nove são as permissões |
| Links | `19` | Quantidade de links do item (não é essencial por enquanto) |
| Dono | `root` | Usuário dono do item |
| Grupo | `root` | Grupo dono do item |
| Tamanho | `4620` | Tamanho em bytes (em diretórios, não é o tamanho do conteúdo) |
| Data | `Nov 21 15:14` | Data e hora da última modificação |
| Nome | `dev` | Nome do arquivo ou diretório |

O primeiro caractere indica o tipo: `d` é um diretório e `-` é um arquivo comum. Existem outros, como o `l` (link simbólico).

Os nove caracteres seguintes são três blocos de três, sempre na ordem dono, grupo e outros (todos os demais usuários). Dentro de cada bloco as letras vêm na ordem `r`, `w`, `x`, e um `-` no lugar significa que aquela permissão não existe.

| Letra | Em um arquivo | Em um diretório |
|---|---|---|
| `r` | Ler o conteúdo | Listar o conteúdo |
| `w` | Alterar o conteúdo | Criar, renomear e apagar itens dentro dele |
| `x` | Executar como programa ou script | Entrar nele (`cd`) |

Lendo o exemplo, `rwx r-x r-x` quer dizer que o dono (`root`) pode tudo, e o grupo (`root`) e os demais usuários podem listar e entrar no diretório, mas não alterá-lo. É por isso que o script precisou do `chmod +x`: ele liga o `x` do arquivo.