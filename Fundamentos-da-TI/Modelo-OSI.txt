# Modelo OSI

## O que eu aprendi

O modelo OSI foi criado pela ISO (Organização Internacional de Normalização) com o objetivo de padronizar a comunicação entre diferentes redes, softwares e hardwares, permitindo que equipamentos de fabricantes diferentes consigam se comunicar entre si.

O modelo é dividido em 7 camadas, numeradas de baixo para cima. Da mais próxima do meio físico até a mais próxima do usuário:

1. **Física**: transmissão física dos bits (0s e 1s) através de cabos, ondas de rádio, etc.
2. **Enlace**: envia a informação (organizada em quadros) usando o endereço físico (MAC), passando por diferentes "pontos" da rede (como switches) até chegar ao destinatário.
3. **Rede**: identifica os IPs de origem e destino e define a melhor rota para que o dado já chamado de *pacote* nessa camada — chegue ao destino.
4. **Transporte**: divide a informação em *segmentos* (TCP) ou *datagramas* (UDP). Se, por exemplo, dos 5 segmentos enviados o de número 2 se perder, o TCP identifica isso e solicita o reenvio apenas dele — já o UDP não faz esse controle, sendo mais rápido, porém sem garantia de entrega.
5. **Sessão**: estabelece, gerencia e encerra a sessão de uso entre o programa e o servidor, controlando o início, a pausa/retomada e o fim da comunicação.
6. **Apresentação**: traduz, formata, comprime e criptografa a mensagem vinda da camada de Aplicação.
7. **Aplicação**: camada mais próxima do usuário. Fornece os serviços de rede diretamente aos programas por meio de protocolos como HTTP (navegação), SMTP (e-mail), FTP (arquivos) e DNS.

Na prática, o modelo OSI acabou não sendo amplamente implementado, principalmente por causa da popularização do modelo TCP/IP. Mesmo assim, ele continua sendo muito usado como referência didática para entender o funcionamento das redes, e foi essencial para o desenvolvimento das redes de computadores como as conhecemos hoje.

Para memorizar as 7 camadas, utilizei a técnica mnemônica usando a frase (Fui Em Roma Trazer Sapato Azul Anil)
