## O que é cibersegurança

A cibersegurança é um conjunto de ações e técnicas para proteger sistemas, programas, redes e equipamentos contra invasões. O foco é garantir que dados valiosos não vazem nem sejam violados em ataques cibernéticos.

Na prática, ela cobre software, hardware e redes, previne problemas na gestão das informações e protege os dados armazenados.

Para dar uma noção da dimensão do problema, a aula cita uma pesquisa da Netscout de 2022: o Brasil era o 2º país do mundo em que mais ocorriam ciberataques, com mais de 439 mil tentativas de invasão e de ataques de negação de serviço distribuído (DDoS) registradas, atrás apenas dos EUA.

### Tipos de cibersegurança

Dependendo do contexto, a cibersegurança pode ser dividida em categorias:

| Tipo | O que faz |
|---|---|
| Segurança operacional | Protege os dados da empresa definindo quem pode acessá-los e com quais níveis de acesso |
| Segurança de rede | Protege a rede contra acessos indevidos e contra ataques como o DoS (*Denial of Service*) |
| Segurança de aplicativos | Responde às ameaças aos softwares instalados em computadores e dispositivos móveis, aplicando protocolos de segurança já durante o desenvolvimento |
| Educação do usuário final | Encontra e corrige comportamentos de risco dos usuários que podem expor dados sensíveis ou colocar a organização em risco |
| Recuperação de desastres | Define as práticas que a organização usa em caso de desastre para se recuperar o mais rápido possível e com o menor dano possível |

### Pilares da cibersegurança

São cinco, e funcionam como um ciclo: primeiro conheço o que preciso proteger, depois protejo, detecto, respondo e, se algo der errado, me recupero.

| Pilar | Função |
|---|---|
| *Identify* (identificar) | Entender os ativos e os riscos associados a eles |
| *Protect* (proteger) | Estabelecer salvaguardas contra eventos de cibersegurança |
| *Detect* (detectar) | Identificar e monitorar continuamente os eventos de cibersegurança |
| *Respond* (responder) | Responder rápido e de forma adequada para conter o impacto dos eventos |
| *Recover* (recuperar) | Restaurar capacidades e serviços após um ataque |

**Observação:** esses cinco pilares correspondem às funções do NIST Cybersecurity Framework (versão 1.1; a 2.0 acrescentou uma sexta, *Govern*). Não é a mesma coisa que a tríade CIA (confidencialidade, integridade e disponibilidade).

## O que é hacking

De forma geral, hacking significa comprometer sistemas de computador, contas pessoais, redes de computador ou dispositivos digitais. Isso não quer dizer, necessariamente, um ato mal-intencionado: o termo também pode ser usado para o emprego da tecnologia ou de um conhecimento para contornar um desafio. É um termo muitas vezes usado de forma equivocada.

O hacker é a pessoa que usa seus conhecimentos e tecnologias para driblar mecanismos e acessar ou comprometer informações e sistemas.

### Hacker vs cracker

Quando um hacker invade uma rede ou sistema, violando a segurança de forma maliciosa, o termo correto para ele é *cracker*.

### Tipos de hackers

Os hackers são classificados com base na legalidade do que fazem:

| Tipo | Descrição |
|---|---|
| *Black hat* (chapéu preto) | Usa conhecimento e tecnologia para fins maliciosos, como vazamento de dados, comprometimento de sistemas e extorsão |
| *White hat* (chapéu branco) | Também chamado de hacker ético. Usa conhecimento e tecnologia para detectar ameaças e proteger sistemas, com base em acordos e contratos |
| *Grey hat* (chapéu cinza) | Tipo intermediário: começa testando os sistemas ou softwares de uma empresa para identificar falhas de segurança e depois avisa a organização para oferecer uma solução |

### Legalidade

Todo hacking do tipo black hat é ilegal, porque não há consentimento prévio da parte invadida. Já o white hat é feito totalmente com base em acordos e limites estabelecidos entre as partes.

A aula não diz como o grey hat se enquadra aqui. Em geral ele age sem autorização prévia, e é isso que o coloca na zona cinzenta: a intenção pode ser boa, mas o ato pode continuar sendo ilegal.

### Técnicas de hacking

A aula apenas lista as técnicas; abaixo, um resumo de cada uma.

| Técnica | O que é |
|---|---|
| Phishing | Mensagem ou página falsa (e-mail, SMS, site) que engana a vítima para que ela entregue dados ou execute uma ação |
| Spoofing de DNS | Adulteração das respostas de DNS para levar a vítima a um site falso, mesmo digitando o endereço certo |
| Roubo de cookies | Roubo dos cookies de sessão do navegador para se passar pelo usuário sem precisar da senha |
| XSS (*Cross-Site Scripting*) | Injeção de um script malicioso em uma página web, que é executado no navegador de quem a acessa |
| SQL Injection | Inserção de comandos SQL em campos de entrada para que a aplicação os execute no banco de dados |

## Principais tipos de ameaças

As ameaças não são direcionadas apenas aos sistemas ou às redes de uma organização, mas também às pessoas que fazem parte dela. E podem surgir de uma variedade de lugares, pessoas e contextos.

### Fontes de ataques

Cada fonte de ataque tem uma motivação diferente:

| Fonte | Motivação |
|---|---|
| Estados-nação (*nation-states*) | Geopolítica |
| Cibercriminosos (*cybercriminals*) | Lucro |
| Hacktivistas (*hacktivists*) | Ideológica |
| Grupos terroristas (*terrorist groups*) | Violência ideológica |
| Buscadores de emoção (*thrill-seekers*) | Satisfação |
| Ameaças internas (*insider threats*) | Descontentamento |

Os hacktivistas combinam hacking com ativismo. As ameaças internas vêm de pessoas de dentro da própria organização.

### Tipos de ataques

Para os tipos de ataques, a aula mostra o Top 15 de ameaças cibernéticas da ENISA, a Agência da União Europeia para a Cibersegurança. A imagem vem do relatório *ENISA Threat Landscape 2020*, então o ranking é daquele ano.

| Nº | Ameaça | Em português |
|---|---|---|
| 1 | *Malware* | Software malicioso |
| 2 | *Web-based attacks* | Ataques baseados na web |
| 3 | *Phishing* | Phishing |
| 4 | *Web application attacks* | Ataques a aplicações web |
| 5 | *Spam* | Spam |
| 6 | *DDoS* | Negação de serviço distribuída |
| 7 | *Identity theft* | Roubo de identidade |
| 8 | *Data breach* | Violação de dados |
| 9 | *Insider threat* | Ameaça interna |
| 10 | *Botnets* | Redes de dispositivos infectados controlados remotamente |
| 11 | *Physical manipulation, damage, theft and loss* | Manipulação física, dano, roubo e perda |
| 12 | *Information leakage* | Vazamento de informações |
| 13 | *Ransomware* | Sequestro de dados mediante pagamento de resgate |
| 14 | *Cyberespionage* | Ciberespionagem |
| 15 | *Cryptojacking* | Uso não autorizado de dispositivos para minerar criptomoedas |

Os ataques crescem em quantidade e em tipos, e isso, por outro lado, abre um leque enorme de oportunidades para os profissionais da área.

## Boas práticas em cibersegurança

Existem várias boas práticas, que vão do uso de sistemas seguros e confiáveis até a mudança de comportamento dos usuários. A aula as divide em cinco categorias:

| Categoria | Práticas |
|---|---|
| Conscientização de pessoas | Abordagem de segurança centrada nas pessoas; reduzir a negligência dos funcionários; informar os funcionários sobre técnicas comuns de phishing |
| Controle de acesso a ativos críticos | Proteger o acesso de dispositivos remotos; manipular as senhas com segurança; usar o princípio do privilégio mínimo |
| Proteção de dados confidenciais | Atenção aos usuários privilegiados; monitorar o acesso de terceiros aos dados; manter backup dos dados confidenciais |
| Segurança robusta e proteção de rede | Usar políticas hierárquicas de segurança cibernética; proteger a rede corporativa; fazer auditorias regulares de segurança cibernética |
| Gerenciamento de identidades | Empregar segurança biométrica; usar autenticação multifator |

### Detalhes das imagens

Cada categoria tem uma imagem de apoio (da Ekran) com algum detalhe a mais:

- **Conscientização:** o phishing é combatido em dois passos, usando um filtro de spam e ensinando os funcionários sobre as técnicas de phishing. Segundo o *Cost of Insider Threats Global Report* de 2022 (Ponemon Institute), 62% das violações de dados causadas por pessoas de dentro da organização vieram de negligência e erros de funcionários.
- **Dados confidenciais:** o acesso de terceiros pode ser restringido com senhas de uso único, aprovações manuais e listas separadas de direitos de acesso.
- **Segurança de rede:** as políticas hierárquicas partem de uma política de segurança centralizada, com políticas específicas para cada departamento (vendas, contabilidade, desenvolvimento de software e gerência).
- **Identidades:** a autenticação multifator combina a senha com outros fatores, como a biometria (impressão digital) e o celular.

Para o controle de acesso, a imagem compara três técnicas de equilíbrio entre privilégios e necessidades do usuário:

| Técnica | Quem recebe o acesso |
|---|---|
| *Zero trust* | Só usuários autenticados e verificados |
| Princípio do privilégio mínimo | Só o acesso às informações e recursos necessários para uma finalidade legítima |
| JIT PAM (*Just-in-Time Privileged Access Management*) | Só os usuários certos, para sistemas e recursos específicos, por um motivo válido e por um tempo determinado |

Resumindo a etapa: as boas práticas podem fazer a diferença entre a vida e a morte de uma organização, por causa do alto dano financeiro e de reputação que os ataques cibernéticos causam.

## Red Team, Blue Team e Purple Team

Com o aumento da quantidade e da complexidade das ameaças, as organizações passaram a adotar uma abordagem mais estratégica. Elas formam times, como o Red Team e o Blue Team, que ensaiam técnicas de ataque e de defesa para identificar e corrigir possíveis falhas de segurança.

### Red Team

É formado para realizar testes de ciberataque, com profissionais de alto conhecimento sobre as principais ameaças e ataques existentes, capazes de simular tentativas de penetrar na rede e/ou nos sistemas. É o lado ofensivo.

Nas imagens da aula, aparecem associados a ele: segurança ofensiva, hacking ético, exploração de vulnerabilidades, testes de intrusão (*penetration tests*), testes de caixa-preta (*black box*), engenharia social e varredura de aplicações web.

### Blue Team

O papel do Blue Team é se opor aos ataques ensaiados pelo Red Team, desenvolvendo estratégias para aumentar as defesas e modificando e reagrupando os mecanismos de proteção da rede para que fiquem mais fortes. É o lado defensivo.

Nas imagens da aula, aparecem associados a ele: segurança defensiva, proteção da infraestrutura, controle de danos, resposta a incidentes (*incident response*, IR), segurança operacional, *threat hunting* (caça a ameaças) e forense digital.

### Purple Team

É a fusão entre o Blue Team e o Red Team: uma combinação de profissionais de cibersegurança que atuam como uma única unidade. Desempenha as funções dos dois times, com vantagens como melhor comunicação, compartilhamento de conhecimento, melhoria da segurança e otimização do tempo.

Nas imagens da aula, aparecem associados a ele: facilitar melhorias na detecção e na defesa, aprimorar as habilidades dos membros dos outros dois times e fazer verificações pontuais (*spot-checking*) em sistemas de organizações maiores.

## Para lembrar

Hacking não é sinônimo de crime: o que separa o white hat do black hat é a autorização das partes. As ameaças vêm de várias fontes, cada uma com sua motivação, inclusive de dentro da própria organização, e por isso as boas práticas combinam tecnologia e comportamento das pessoas. Quanto aos times, o Red Team ataca, o Blue Team defende e o Purple Team junta os dois para que um aprenda com o outro.