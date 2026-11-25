## Conceitos base sobre sistemas operacionais

Um sistema operacional (SO) é um software que atua como intermediário entre o usuário e o hardware do computador. Ele traduz as entradas do usuário para a linguagem de máquina, formando uma interface entre o usuário e o hardware, e também traduz para o usuário as saídas geradas pelo hardware.

No diagrama da aula, a comunicação vai em camadas: usuário, aplicação, sistema operacional e hardware.

### Funções e recursos

As funções do SO são o gerenciamento de processos, de memória, de dispositivos e de arquivos, além de segurança, detecção de erros e agendamento de tarefas. Na imagem da aula, o SO fica entre os aplicativos e a memória (cache, primária e secundária).

Entre os recursos que ele oferece estão:

- uma plataforma para executar aplicativos;
- gerenciamento de memória e CPU;
- abstração do sistema de arquivos;
- suporte de rede;
- recursos de segurança;
- interface de usuário;
- utilitários e serviços de sistema;
- suporte ao desenvolvimento de aplicativos.

### Componentes: shell e kernel

Para executar tarefas, o SO tem dois componentes.

| Componente | Descrição | Funções |
|---|---|---|
| Shell | Camada mais externa do SO. Trata das interações do usuário e gerencia a interação entre usuário e sistema operacional | Solicitar entradas do usuário; interpretar a entrada para o SO; manipular a saída do SO |
| Kernel | Componente central do SO, do qual todos os outros dependem para fornecer serviços essenciais. É a interface principal entre o SO e o hardware | Gerenciamento de entrada-saída, de memória, de processos (para execução de aplicativos) e de dispositivos; controle de chamadas do sistema |

No diagrama da aula, o kernel fica entre os aplicativos e o hardware (CPU, memória e dispositivos). O shell já apareceu no "Manipulando Arquivos no Linux", onde o Bash é o interpretador dos comandos.

### Exemplos de SO's

Microsoft Windows, macOS, Linux e Android.

## Microsoft Windows

O Windows é o principal sistema operacional da Microsoft e o padrão de fato para computadores domésticos e empresariais. É um sistema baseado em interface gráfica do usuário (GUI), introduzido em 1985 e lançado em várias versões.

O código-fonte das várias versões é escrito principalmente em C, com algumas partes em C++ e Assembly.

Até a versão 3.11 ele rodava em 16 bits (com um update chamado Win32s adicionando suporte a 32 bits). As versões a partir do XP e do Server 2003 já estão preparadas para a tecnologia de 64 bits.

### Versões

| Versão | Ano |
|---|---|
| Windows 1.0 | 1985 |
| Windows 3.1 | 1992 |
| Windows 95 | 1995 |
| Windows XP | 2001 |
| Windows Vista | 2006 |
| Windows 7 | 2009 |
| Windows 8 | 2012 |
| Windows 10 | 2015 |
| Windows 11 | 2021 |

### Ameaças e prevenção

Por ser tão popular, o Windows é um grande alvo das ameaças cibernéticas. A aula cita como exemplos de vírus: WinNT.Remote Explorer, WinNT.Infis, Win95.CIH, Win32.Kriz e Win95.Babylonia.

Para se prevenir:

- manter as atualizações do SO em dia;
- usar um bom antivírus;
- ter cuidado e bom senso com o que acessa.

## SO's baseados em Linux

### Antecedentes: o Unix

O Unix foi implementado em 1969 por Ken Thompson, Dennis Ritchie, Douglas McIlroy e Joe Ossanna. Foi lançado pela primeira vez em 1971, escrito em Assembly, e em 1973 foi reescrito em C por Dennis Ritchie.

### O que é Linux

De forma genérica, o Linux é um sistema operacional, assim como o Windows e o macOS, que permite executar programas em um computador e em outros dispositivos.

Em uma definição mais técnica, porém, **Linux é o nome dado apenas ao núcleo do sistema operacional, o kernel**. Ele foi escrito originalmente por Linus Torvalds, do Departamento de Ciência da Computação da Universidade de Helsinki (Finlândia), com a ajuda de vários programadores voluntários através da Usenet.

O diagrama do kernel Linux mostra os subsistemas dele entre os aplicativos e o hardware: gerenciamento de processos e de memória, VFS, rede, segurança, criptografia e os drivers de dispositivo.

O Linux é um SO *open source*: pode ser editado e distribuído sem o pagamento de royalties.

### Distribuições

Com base no kernel Linux foram criadas várias distribuições, com os mais diversos fins. A aula mostra a "tabela periódica das distribuições Linux", em que cada quadrado traz a posição de popularidade no DistroWatch, o símbolo, o nome e o ano da versão estável. As cores indicam a família de cada distribuição:

| Família | Exemplos que aparecem na imagem |
|---|---|
| Debian/Ubuntu | Debian, Ubuntu, Linux Mint, Kali Linux, Parrot Security OS, Tails, Raspbian, elementary OS |
| Arch | Arch Linux, Manjaro, ArchBang, Chakra |
| Red Hat/Fedora/Mandriva | Fedora, CentOS, RHEL, Oracle Linux, OpenMandriva |
| Slackware | Slackware Linux, Absolute Linux |
| Gentoo | Gentoo Linux, Sabayon, Calculate Linux |
| Outras | openSUSE, SLES, Alpine Linux, NixOS, Void, Puppy Linux |

### Vulnerabilidades do Linux

Nunca haverá um sistema operacional, ou qualquer outro software, infalível ou sem falhas, e o Linux não é exceção. A aula lista vulnerabilidades descobertas em 2022.

O nível de risco de cada vulnerabilidade é definido pelo CVSS (*Common Vulnerability Scoring System*), com uma representação numérica de 0 a 10.

| CVE | CVSS |
|---|---|
| CVE-2022-0435 | 9.0 |
| CVE-2022-0492 | 7.8 |
| CVE-2022-28893 | 7.2 |
| CVE-2022-0998 | 7.2 |
| CVE-2022-0995 | 6.6 |

Na faixa usada pelo CVSS v3 (a aula não cita a versão), de 9,0 a 10 a vulnerabilidade é crítica, de 7,0 a 8,9 é alta, de 4,0 a 6,9 é média e de 0,1 a 3,9 é baixa. A aula só lista os identificadores e as notas; os detalhes de cada CVE ficam na base do NIST (link em Referências).

## VirtualBox e virtualização

A virtualização consiste em executar sistemas operacionais sobre outros SO's, consumindo os recursos deles de forma isolada. Na imagem da aula, o *hypervisor* é a camada entre o hardware físico e as máquinas virtuais (VMs).

O VirtualBox é um software de virtualização desenvolvido pela empresa Innotek, que foi comprada pela Sun Microsystems e, por fim, pela Oracle. Pode ser usado de forma gratuita. Ele é usado no curso para emular as máquinas virtuais dos experimentos. O download fica em https://www.virtualbox.org/wiki/Downloads.

## Máquinas virtuais do laboratório

Nas quatro etapas seguintes, o curso instala um sistema por aula em uma máquina virtual no VirtualBox: Windows XP, Windows 7, Windows 10 e Kali Linux. Em cada uma, o slide só traz a introdução e pede para usar uma imagem .ISO disponível em um link, que não aparece no material. O passo a passo da instalação não está nos slides.

**Atenção:** o Windows XP, o 7 e o 10 já saíram do suporte padrão da Microsoft (em abril de 2014, janeiro de 2020 e outubro de 2025), então não recebem mais atualizações de segurança normais. Por isso só vale usá-los dentro da máquina virtual, como laboratório. Como o link da ISO não aparece nos slides, vale conferir a origem da imagem e o hash antes de usá-la.

### Kali Linux

O Kali é muito popular entre estudantes e profissionais de segurança da informação e traz várias ferramentas e aplicações nativas para testes de invasão, pentest, forense e outras áreas.

A aula cita quatro ferramentas, aqui com um resumo de cada uma:

| Ferramenta | Para que serve |
|---|---|
| Metasploit | Framework para desenvolver e executar exploits em testes de invasão |
| Nmap | Mapeamento de rede, com varredura de hosts, portas e serviços |
| Wireshark | Captura e análise do tráfego de rede |
| Aircrack-ng | Auditoria de segurança de redes Wi-Fi |

As interfaces gráficas citadas são o Gnome Shell, o XFCE e o KDE Plasma.

## Para lembrar

O sistema operacional fica entre o usuário e o hardware, e o kernel é o centro dele, enquanto o shell é a camada de contato com o usuário. Linux, a rigor, é só o kernel; o que se instala no computador é uma distribuição baseada nele. Nenhum sistema é livre de falhas, e é por isso que existem CVEs e notas CVSS para medir o risco. E, como os laboratórios usam sistemas antigos e ferramentas de pentest, tudo isso fica dentro de máquinas virtuais.