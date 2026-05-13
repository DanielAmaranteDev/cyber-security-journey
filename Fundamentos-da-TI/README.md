# Entendendo os componentes básicos de um computador:

## 1 - Unidade Central de Processamento (CPU): O Cérebro do Computador

É chamada de "Cérebro" porque é responsável por executar instruções,
realizar cálculos e gerenciar fluxos do sistema. Interpreta e executa  
instruções das mais simples as mais complexas

## Como a CPU funciona ?

Ela consiste em várias partes principais:

### 1° - Unidade Lógica Aritmética (ULA)
Executa operações aritméticas (adição, subtração) e operações lógicas (E, OU, NÃO)

### 2° - Unidade de Controle (UC)
Dirige e coordena a maioria das operações no computador,
interpretando instruções e gerenciando fluxo de dados

### 3° - Registradores
Pequenos locais de armazenamento de alta velocidade  
dentro da CPU usados para armazenar dados TEMPORARIAMENTE durante o  
processamento

---

As CPUs modernas geralmente contém múltiplos "núcleos", que são unidades  
de processamento independentes dentro de um único chip físico. Cada  
núcleo pode lidar com um conjunto separado de instruções, permitindo  
que a CPU execute múltiplas tarefas simultaneamente, conceito conhecido  
como "processamento paralelo". Além disso, muitas CPUs ultilizam  
"hyper-threading" ou "multithreading simultâneo (SMT)", o que permite  
que cada núcleo físico apareça como dois núcleos lógicos, aprimorando ainda  
mais a capacidade de multitarefa, permitindo que um único núcleo processe  
dois fluxos de instruções simultaneamente.

---

## Principais métricas da CPU

Ao avaliar uma CPU, várias métricas são importantes:

### 1° - Núcleos
O número de unidades de processamento independentes.  
Mais núcleos significam melhor desempenho para aplicativos multithread

### 2° - Threads
O número de fluxos de instruções que uma CPU pode processar  
simultaneamente. Como hyper-threading/SMT, o número de threads pode ser  
o dobro do número de núcleos

### 3° - Velocidade de Clock(GHz)
Mede o número de ciclos que a CPU pode  
executar por segundo, Uma velocidade de clock mais alta geralmente  
significa uma execução mais rápida de instruções em um único núcleo

### 4° - Memória Cache(L1, L2, L3)
Memória pequena e extremamente rápida  
integrada diretamente ao chip da CPU. Ela armazena dados acessados com frequência,  
reduzindo o tempo que a CPU precisa esperar por dados da RAM, que é mais lenta  
Maiores caches, geralmente melhoram o desempenho

---

## Cenário Hipotético:

Imagine uma cozinha de restaurante movimentada, onde a CPU é o chefe de cozinha.  
O chefe recebe vários pedidos(instruções) simultâneamente.

- Os núcleos são como os cozinheiros individuais sob comando do chef principal,  
  cada um capaz de preparar um prato diferente ao mesmo tempo.

- Os fios são como a habilidade do chef de realizar várias tarefas ao mesmo tempo  
  picando legumes enquanto fica de olho em uma panela fervendo, fazendo duas coisas  
  simultâneamente com um único par de mãos.

- A velocidade de processamento (Clock Speed) é a rapidez com que esse chef  
  consegue executar cada ação individual, como picar uma cebola mais rapidamente

- A memória cache é como uma pequena despensa organizada ao lado do chef, que  
  armazena ingredientes usados com frequência (como sal, pimenta e vegetais comuns)  
  para o acesso imediato, facilitando a atuação do chef, sem fazer ele ter  
  que ir a despensa (RAM) toda vez

---

* PAREI EM Memória de Acesso Aleatório (RAM): Memória de Curto Prazo