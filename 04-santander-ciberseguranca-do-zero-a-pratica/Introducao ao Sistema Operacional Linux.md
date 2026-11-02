## O que é um sistema operacional (SO)

Sitema Operacional é um software ou conjunto de softwares que tem a função de gerenciar e administrar os recursos de um sistema. Esses recursos são: Componentes de Hardware, sistemas de arquivos, programas de terceiros, etc.

# Principal função

Estabelecer uma interface entre o hardware e o usuário

# Kernel ou núcleo do sistema operacional

O Kernel é a ponte entre o usuário e o hardware, o kernel compõe a parte central do SO e responde por tarefas cruciais como: 

* Estabelecer a camada de abstração de baixo nível (linguagem de máquina, como o hardware)
* Gerenciar recursos como processador, RAM, sistema de arquivos e dispositivos de entrada e saída
* Gerenciar processos (execução) de programas
* Gerenciar o uso de dispositivos, memória do sistema e programas, definindo quais têm prioridade

## Diferença entre um SO e um Kernel

O Kernel é o núcleo do sistema e o SO é o sistema completo (incluindo o kernel), seria como um carro e um motor, o carro é o sistema operacional e o kernel é o motor desse carro, o kernel sozinho não serve para o usuário final, ele precisa de uma interface, programas, ferramentas, instaladores, etc.

## O que é o linux

O linux é um dos sistemas operacionais mais populares e é amplamente utilizado no segmento de servidores e por desenvolvedores de software. O kernel (nucleo) do linux começou a ser desenvolvido por Linus Torvalds em 1991 inspirado no Unix, um outro SO criado nos anos 70. O desenvolvimento inicial do kernel do Linux começou ainda quando Linus estava na faculdade em Helsinki na Finlândia.

O linux, mais especificamente o kernel do sistema operacional, não é suportado por uma empresa individual, mas sim por uma comunidade internacional de desenvolvedores. O kernel do Linux está disponível gratuitamente e pode ser usado por qualquer pessoa, sem restrições.

O kernel do Linux é mantido pela Linux Foundation, que é uma organização sem fins lucrativos. Para manter o kernel atualizado e implementar melhorias, a fundação é mantida por doações de grandes empresas que utilizam o linux em seus produtos ou serviços.

https://linuxfoundation.org/

#Distribuições

Uma distribuição Linux é um pacote que consiste em um kernel linux, mais uma seleção de aplicativos mantidos por uma empresa ou uma comunidade de usuários, o objetivo de uma distro é otimizar o kernel e os aplicativos que rodam no sistema operacional para um determinado tipo de uso ou grupo de usuários

Basicamente uma empresa (fundação) pega o Linux (Kernel) e adiciona elementos para torná-lo semelhante a um Sistema Operacional

# Sistemas embarcados

Os sistemas embarcados são uma combinação de hardware e software projetados para cumprir uma função específica dentro de um sistema maior. Normalmente fazem parte de outros dispositivos e ajudam a controlá-los. Podem ser encontrados em aplicações automotivas, médicas e até militares. O android é um sistema operacional móvel desenvolvido principalmente pelo Google. A empresa inicialmente criou um sistema operacional destinado a rodar em câmeras digitais.

## Diferenças entre Linux Desktop e Linux Server

Modelo Cliente-Servidor

O modelo cliente-servidor é uma estrutura de aplicação que distribui as tarefas e cargas de trabalho entre os fornecedores de um recurso ou serviço, chamados de servidores, e os dispositivos ou programas que solicitam esses serviços, chamados de clientes.

Na prática, isso significa que um servidor disponibiliza recursos, como páginas de sites, arquivos, bancos de dados ou aplicações, enquanto os clientes fazem solicitações para acessar esses recursos. Por exemplo, quando você acessa um site pelo navegador, seu computador atua como cliente, enquanto o computador que hospeda o site atua como servidor, recebendo sua solicitação e enviando a página solicitada.

Linux Desktop

O Linux Desktop é voltado para o uso cotidiano de pessoas que interagem diretamente com o computador. Seu principal objetivo é oferecer um ambiente gráfico, no qual o usuário pode executar tarefas por meio de janelas, ícones, menus e aplicativos, sem precisar utilizar comandos no terminal o tempo todo.

É utilizado para atividades como navegar na internet, estudar, trabalhar com documentos, assistir a vídeos, programar e executar outros programas. Por isso, normalmente possui uma interface gráfica completa, além de aplicativos e recursos que facilitam a experiência do usuário.

Algumas distribuições bastante conhecidas são Ubuntu Desktop, Linux Mint e Fedora Workstation.

Linux Server

O Linux Server é voltado para administrar e disponibilizar serviços a outros computadores ou dispositivos por meio de uma rede. Diferentemente do Desktop, seu foco não é oferecer uma interface visual para o uso cotidiano, mas executar serviços de maneira estável, contínua e eficiente.

Ele pode ser utilizado para hospedar sites, armazenar arquivos, gerenciar bancos de dados, executar aplicações, controlar redes e disponibilizar serviços para diversos usuários ao mesmo tempo.

Por esse motivo, muitas instalações de Linux Server não possuem interface gráfica, sendo administradas principalmente por meio do terminal, geralmente com acesso remoto utilizando o protocolo SSH. Essa configuração reduz o consumo de recursos do computador e permite que eles sejam direcionados à execução dos serviços.

Algumas distribuições utilizadas em servidores são Ubuntu Server, Debian e Red Hat Enterprise Linux.

Principal diferença

A principal diferença entre Linux Desktop e Linux Server está na finalidade de cada um. Enquanto o Linux Desktop é desenvolvido e configurado para facilitar a interação direta de uma pessoa com o computador, o Linux Server é configurado para fornecer serviços e recursos a outros dispositivos, normalmente por meio de uma rede.

É importante entender que eles não são necessariamente sistemas operacionais completamente diferentes. Ambos utilizam o Linux e podem compartilhar muitas das mesmas tecnologias. A diferença está principalmente nos programas instalados, nas configurações e na forma como cada sistema é utilizado. Inclusive, um Linux Desktop pode funcionar como servidor, assim como um Linux Server pode receber uma interface gráfica, caso seja necessário.