# HTTP & HTTPS — Fundamentos do Protocolo

**Anotações de estudo — TryHackMe**
*Trilha: Cibersegurança / Pentest*

---

## 📑 Índice

- [HTTP \& HTTPS — Fundamentos do Protocolo](#http--https--fundamentos-do-protocolo)
  - [📑 Índice](#-índice)
  - [O que são HTTP e HTTPS](#o-que-são-http-e-https)
    - [HTTP (HyperText Transfer Protocol)](#http-hypertext-transfer-protocol)
    - [HTTPS (HyperText Transfer Protocol Secure)](#https-hypertext-transfer-protocol-secure)
  - [Estrutura de uma URL](#estrutura-de-uma-url)
  - [Anatomia de uma Requisição e Resposta HTTP](#anatomia-de-uma-requisição-e-resposta-http)
    - [Requisição (Request)](#requisição-request)
    - [Resposta (Response)](#resposta-response)
  - [Métodos HTTP](#métodos-http)
  - [Códigos de Status HTTP](#códigos-de-status-http)
    - [Faixas gerais](#faixas-gerais)
    - [Códigos mais comuns](#códigos-mais-comuns)
  - [Headers (Cabeçalhos) HTTP](#headers-cabeçalhos-http)
    - [Cabeçalhos de requisição (Request Headers)](#cabeçalhos-de-requisição-request-headers)
    - [Cabeçalhos de resposta (Response Headers)](#cabeçalhos-de-resposta-response-headers)
  - [Cookies](#cookies)

---

## O que são HTTP e HTTPS

### HTTP (HyperText Transfer Protocol)

Protocolo utilizado sempre que um site é acessado. Define as regras de comunicação com servidores web, com o objetivo de transmitir dados de páginas web (HTML, imagens, vídeos, etc). Foi criado por **Tim Berners-Lee**.

### HTTPS (HyperText Transfer Protocol Secure)

Versão segura do HTTP. Utiliza criptografia para:

- Impedir que a mensagem seja acessada de forma indevida (interceptação);
- Garantir que a comunicação está sendo feita com o servidor correto, e não com uma cópia dele (falsificação).

| Conceito | Definição |
|---|---|
| **HTTP** | Regra de comunicação (protocolo) |
| **URL** | Endereço da web — o HTTP é o protocolo usado para transportar os dados desse endereço |

---

## Estrutura de uma URL

**URL (Uniform Resource Locator)**: um endereço, uma instrução de como acessar um recurso na internet.

```
http://usuario:senha@tryhackme.com:80/view-room?id=1#task3
```

| Componente | Exemplo | Descrição |
|---|---|---|
| **Schema** | `http` | Indica qual protocolo deve ser utilizado para acessar o recurso (HTTP, HTTPS, FTP, etc) |
| **Usuário** | `usuario:senha` | Alguns serviços exigem autenticação; usuário e senha podem ser inseridos diretamente na URL |
| **Host/Domínio** | `tryhackme.com` | Nome de domínio ou endereço IP do servidor a ser acessado |
| **Porta** | `80` | Porta de conexão. Padrão: 80 (HTTP) e 443 (HTTPS), mas pode ser qualquer valor entre 1 e 65535 |
| **Path** | `/view-room` | Nome do arquivo ou local onde está armazenado o recurso solicitado |
| **Query String** | `?id=1` | Informações adicionais enviadas junto ao path (ex: `/blog?id=1` solicita o artigo de ID 1) |
| **Fragment** | `#task3` | Referência a uma parte específica da página, usado em páginas extensas |

> 📌 *Espaço reservado para a imagem ilustrativa da estrutura da URL (as anotações originais faziam referência a uma imagem de apoio).*

---

## Anatomia de uma Requisição e Resposta HTTP

Uma requisição pode ser feita a um servidor web, por exemplo usando o método `GET`. Junto da requisição são enviados **cabeçalhos de mensagem (headers)** — informações adicionais para o servidor com quem se está se comunicando.

### Requisição (Request)

```http
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/
```

- `GET /` → solicita a página inicial, usando HTTP na versão 1.1
- `Host` → informa ao servidor qual site deve ser exibido (tryhackme.com)
- `User-Agent` → informa o navegador utilizado e sua versão
- `Referer` → informa o endereço de origem da requisição

> Toda requisição termina em uma linha em branco, indicando ao servidor que o pedido foi concluído e que se aguarda a resposta.

### Resposta (Response)

```http
HTTP/1.1 200 OK
Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98

<html>
<head>
    <title>TryHackMe</title>
</head>
<body>
    Welcome To TryHackMe.com
</body>
</html>
```

| Campo | Descrição |
|---|---|
| `HTTP/1.1 200 OK` | Versão do HTTP usada pelo servidor + mensagem de status (200 OK = pedido concluído com sucesso) |
| `Server` | Software do servidor web e sua versão |
| `Date` | Data, hora e fuso horário atuais do servidor |
| `Content-Type` | Tipo de conteúdo da resposta (ex: `text/html`) |
| `Content-Length` | Tamanho da resposta |

---

## Métodos HTTP

| Método | Descrição |
|---|---|
| **GET** | Requisita dados do servidor; pede algo e espera uma resposta. Usado para obter informações |
| **POST** | Envia informações ao servidor, geralmente para criar novos registros |
| **PUT** | Envia informações ao servidor, mas atualiza um registro existente em vez de criar um novo |
| **DELETE** | Exclui informações/registros do servidor web |

---

## Códigos de Status HTTP

Toda requisição retorna um **status code** na primeira linha da resposta (ex: `GET` retornando `200 OK`).

### Faixas gerais

| Faixa | Categoria | Descrição |
|---|---|---|
| **100–199** | Informational | Informa ao cliente que a primeira parte da solicitação foi aceita e que ele deve continuar enviando o restante (pouco comum atualmente) |
| **200–299** | Sucesso | O pedido foi bem-sucedido |
| **300–399** | Redirecionamento | A requisição é redirecionada para outro recurso (outra página ou site) |
| **400–499** | Erro do cliente | Houve algum erro no pedido feito pelo cliente |
| **500–599** | Erro do servidor | Erros que ocorrem no lado do servidor, geralmente indicando problemas graves no processamento dos pedidos |

### Códigos mais comuns

| Código | Nome | Descrição |
|---|---|---|
| **200** | OK | O pedido foi concluído com sucesso |
| **201** | Created | Um novo recurso foi criado (ex: novo usuário, nova publicação) |
| **301** | Moved Permanently | Redireciona o navegador para uma nova página; informa aos mecanismos de busca que o recurso foi movido permanentemente |
| **302** | Found | Similar ao 301, mas indica que o recurso foi movido temporariamente |
| **400** | Bad Request | O pedido do usuário está incorreto, geralmente por parâmetros ausentes ou inválidos |
| **401** | Unauthorized | O cliente não está autorizado a realizar essa requisição; geralmente exige autenticação |
| **403** | Forbidden | O usuário não tem permissão para visualizar o recurso, esteja autenticado ou não |
| **404** | Not Found | O recurso solicitado não existe |
| **405** | Method Not Allowed | O recurso esperava outro método HTTP (ex: `/create-account` esperava `POST`, mas recebeu `GET`) |
| **500** | Internal Server Error | O servidor encontrou um erro e não sabe como lidar com ele |
| **503** | Service Unavailable | O servidor não conseguiu atender ao pedido por estar sobrecarregado ou em manutenção |

> 🔗 Referência visual dos status codes: [http.cat](https://http.cat/)

---

## Headers (Cabeçalhos) HTTP

Informações adicionais enviadas ao servidor (ou pelo servidor) durante uma requisição/resposta. Não é obrigatório incluir headers, mas sem eles fica difícil interpretar a resposta corretamente.

### Cabeçalhos de requisição (Request Headers)

| Header | Descrição |
|---|---|
| **Host** | Permite acessar um site específico em servidores que hospedam vários sites. Sem esse header, apenas a página padrão é acessada |
| **User-Agent** | Nome e versão do navegador; ajuda o servidor a formatar o site adequadamente |
| **Content-Length** | Informa quantos dados devem ser recebidos na solicitação, garantindo que nenhum dado seja perdido |
| **Accept-Encoding** | Indica quais métodos de compressão o navegador suporta, facilitando a compressão e transmissão dos dados |
| **Cookie** | Dados enviados ao servidor para que ele "lembre" de informações do cliente |

### Cabeçalhos de resposta (Response Headers)

| Header | Descrição |
|---|---|
| **Set-Cookie** | Informações que devem ser armazenadas no cliente e reenviadas ao servidor futuramente |
| **Cache-Control** | Por quanto tempo o conteúdo da resposta deve ficar em cache no navegador antes de ser solicitado novamente |
| **Content-Type** | Informa ao cliente qual tipo de dado está sendo retornado |
| **Content-Encoding** | Qual método foi utilizado para comprimir os dados |

---

## Cookies

Pequenos fragmentos de dados armazenados no computador do cliente. São salvos quando o cliente recebe um header `Set-Cookie` de um servidor.

- Em toda requisição subsequente, os cookies são reenviados ao servidor.
- Servem para identificar o usuário, lembrar configurações do site, verificar visitas anteriores, etc — depende de como o site os utiliza.
- Como o **HTTP é um protocolo sem estado** (*stateless* — não guarda informações de pedidos anteriores), os cookies existem justamente para suprir essa limitação.
- O uso mais comum é a **autenticação de usuários**: o valor do cookie geralmente não é uma senha legível, mas sim um **token** — um código único e difícil de ser adivinhado.

**Como visualizar os cookies enviados/recebidos:**

> DevTools do navegador → aba **Network** → **Cookies**

Isso permite visualizar quais cookies a aplicação solicitou e quais foram enviados de volta ao servidor.

---

*Anotações feitas durante estudos na plataforma [TryHackMe](https://tryhackme.com/), como parte da trilha de cibersegurança com foco em pentest.*