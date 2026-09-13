# Módulo 01 — Start Your Cyber Security Journey (TryHackMe)

Documentação dos aprendizados obtidos durante o Módulo 01 do TryHackMe, com foco nos primeiros conceitos e ferramentas de Cyber Security.

---

## 1. DIRB

O **DIRB** é uma ferramenta de linha de comando do Linux usada para escanear arquivos e diretórios ocultos em um servidor web, através de força bruta com uma wordlist.

**Uso:**
```bash
dirb <URL_DO_ALVO>
```

---

## 2. Resposta a Incidentes (SOC)

Ao lidar com uma ameaça detectada, o primeiro passo **não** é tentar eliminá-la imediatamente — o correto é **conter** a ameaça primeiro, para depois tratá-la, evitando que ela se espalhe ou cause mais danos enquanto é analisada. Após a resolução, é feito um relatório documentando o que aconteceu.

A ordem do processo é:

1. **Detectar**
2. **Analisar**
3. **Conter**
4. **Erradicar**
5. **Recuperar**

---

## 3. Shodan

O **Shodan** é um mecanismo de busca de dispositivos conectados à internet. Enquanto navegadores tradicionais (como o Google) indexam principalmente sites, páginas e documentos, o Shodan varre a internet coletando informações sobre **serviços acessíveis publicamente**, como:

- Servidores
- Dispositivos de rede
- Câmeras IP
- Dispositivos IoT
- Bancos de dados expostos
- Serviços e aplicações

O Shodan mostra o que está **acessível**, e não necessariamente o que está **vulnerável**. Ou seja, ele coleta e expõe informações públicas sobre um dispositivo, mas isso não significa automaticamente que existe uma falha de segurança ali.

---

## 4. VirusTotal

O **VirusTotal** é uma ferramenta online que analisa arquivos, URLs, domínios ou hashes de arquivos, submetendo-os a mais de 70 antivírus e engines de análise diferentes, para verificar se há indícios de malware.

---

## 5. Bancos de Dados de Vulnerabilidades (CVE) e CVSS

Um **CVE (Common Vulnerabilities and Exposures)** é um banco de dados que ajuda a identificar vulnerabilidades conhecidas em softwares, mostrando o tipo de vulnerabilidade, o impacto e o nível de severidade.

**Ponto importante:** CVE e CVSS não são a mesma coisa.

- **CVE** → identifica a vulnerabilidade.
- **CVSS (Common Vulnerability Scoring System)** → atribui uma pontuação numérica para ajudar a avaliar a severidade dessa vulnerabilidade.

---

## 6. man e Netcat (nc)

O comando **`man`** no Linux é usado para consultar o manual (documentação) de outros comandos.

O **Netcat (`nc`)** é uma ferramenta usada para estabelecer conexões de rede e enviar/receber dados através delas.

**Exemplo:**
```bash
nc host.example.com 42
```

- `nc` → executa o Netcat
- `host.example.com` → computador/host de destino
- `42` → porta de destino

Nesse exemplo, o comando tenta estabelecer uma conexão TCP com a porta 42 do host informado.
