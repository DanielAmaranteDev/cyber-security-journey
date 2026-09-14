# Aprendendo sobre o Linux

Documentação dos aprendizados sobre comandos básicos do Linux, com foco em navegação, busca de arquivos e combinação de comandos via terminal.

---

## 1. Identificação e saída de texto

- **`whoami`** → indica quem é o usuário atual dentro do sistema.
- **`echo`** → exibe um texto específico fornecido (uma analogia simples: o `print` do Python).

---

## 2. Navegação pelo terminal

O objetivo é conseguir se mover pelo ambiente sem usar o mouse, apenas com o terminal. Quatro comandos são suficientes para realizar quase todas as operações de navegação:

- **`ls`** → lista o que está na pasta (diretório) atual.
- **`cd`** → muda de diretório (vai para uma pasta específica).
- **`cat`** → exibe o conteúdo de um arquivo.
- **`pwd`** → "onde eu estou?" — mostra a pasta (diretório) em que o usuário está no momento.

---

## 3. Busca eficiente de arquivos

- **`find`** → procura um arquivo pelo nome.
  ```bash
  find -name passwords.txt
  ```
- **`grep`** → procura por um texto dentro do conteúdo de um arquivo.
  ```bash
  grep "passwords123" passwords.txt
  ```

---

## 4. Caracteres especiais para combinar comandos

- **`&`** → executa um comando em segundo plano. Normalmente, ao digitar um comando no terminal, ele trava a sessão até a tarefa terminar. Usando `&` no final, o comando (programa) continua rodando em segundo plano e o terminal fica livre para uso.

- **`&&`** → executa um comando após o outro, na ordem, mas só executa o segundo se o primeiro tiver dado certo ("rode B se A tiver funcionado").
  ```bash
  cd pasta_que_nao_existe && ls
  ```
  Nesse exemplo, como o `cd` falha (a pasta não existe), o `ls` nem chega a ser executado.

- **`>`** → redireciona um texto (saída) para dentro de um arquivo, **sobrescrevendo** o conteúdo existente.
  ```bash
  echo "Olá, Mundo!" > arquivo.txt
  ```
  Nesse caso, `arquivo.txt` ficará apenas com o texto `"Olá, Mundo!"`. Se o arquivo já tivesse algum conteúdo, ele seria substituído.

- **`>>`** → faz a mesma coisa que o `>`, mas em vez de sobrescrever, **adiciona** o texto no final do arquivo.

- **`echo` + `>`** → combinação usada para salvar um texto (saída) dentro de um arquivo.
  ```bash
  echo hey > Welcome
  ```
  Esse comando cria o arquivo `Welcome` e coloca a saída `hey` dentro dele.