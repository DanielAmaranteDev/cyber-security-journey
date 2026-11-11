# Navegando pelo sistema de arquivos no Linux

No Linux, os arquivos e diretórios são organizados em uma estrutura hierárquica que começa na raiz (`/`).

## 1. Símbolos importantes

| Símbolo | Significado |
|---|---|
| `/` | Diretório raiz do sistema. |
| `~` | Diretório pessoal do usuário (*Home*). |
| `.` | Diretório atual. |
| `..` | Diretório imediatamente acima do atual. |

## 2. Navegação

| Comando | Função |
|---|---|
| `pwd` | Mostra o caminho completo do diretório atual. |
| `ls` | Lista os arquivos e diretórios do local atual. |
| `ls -la` | Lista também os itens ocultos, em formato detalhado. |
| `ls \| more` | Mostra a listagem por partes; `Enter` avança uma linha e `q` sai. |
| `cd nome_da_pasta` | Entra em um diretório. |
| `cd ..` | Volta para o diretório pai. |
| `cd /` | Vai para a raiz do sistema. |
| `cd ~` ou `cd` | Vai para o diretório pessoal do usuário. |

Os caminhos podem ser **absolutos**, quando começam em `/` (por exemplo, `/home/usuario/Downloads`), ou **relativos**, quando usam o diretório atual como referência (por exemplo, `Downloads`).

## 3. Criação e remoção

| Comando | Função |
|---|---|
| `touch arquivo.txt` | Cria um arquivo vazio ou atualiza sua data de modificação, caso já exista. |
| `mkdir pasta` | Cria um diretório. |
| `rmdir pasta` | Remove um diretório vazio. |
| `rm arquivo.txt` | Remove um arquivo. |

**Atenção:** `rm` exclui arquivos sem enviá-los para a lixeira. Confira o caminho antes de executar. A opção `-r` permite remover diretórios e seu conteúdo.

## 4. Pesquisa de arquivos

O comando `find` procura arquivos e diretórios a partir do local informado.

```bash
find . -name "arquivo.txt"
```

Procura `arquivo.txt` a partir do diretório atual (`.`).

```bash
find ~ -name "*.pdf"
```

Procura arquivos com extensão `.pdf` dentro do diretório pessoal do usuário.

Opções úteis:

- `-name`: pesquisa pelo nome, diferenciando maiúsculas de minúsculas.
- `-iname`: pesquisa pelo nome, sem diferenciar maiúsculas de minúsculas.
- `-type f`: pesquisa somente arquivos.
- `-type d`: pesquisa somente diretórios.

## 5. Ajuda dos comandos

| Recurso | Função |
|---|---|
| `comando --help` | Mostra uma ajuda resumida com opções e formas de uso, quando disponível. |
| `man comando` | Abre o manual detalhado do comando. Pressione `q` para sair. |

Exemplos:

```bash
ls --help
man find
```

**Observação:** `--help` é uma opção usada junto a um comando; `man` é o comando que abre a página de manual.

## 6. Observações

- O Linux diferencia letras maiúsculas de minúsculas: `Downloads` e `downloads` podem ser nomes diferentes.
- O diretório atual influencia os comandos que utilizam caminhos relativos.
- Não é necessário decorar todas as opções. É importante entender a finalidade dos comandos e consultar a ajuda quando necessário.
