# Módulo 16: Serviço da capada de aplicação

### 1. O Ciclo de Vida de uma Requisição Web

Quando você digita `www.learnip.com`, acontece uma coreografia de protocolos:

1. DNS (Porta 53 UDP): O PC pergunta ao servidor DNS: "Qual o IP deste nome?". O DNS responde (ex: `172.16.10.50`).
2. TCP Handshake (Porta 80 ou 443): O PC abre uma conexão confiável com o servidor.
3. HTTP Request (Porta 80): O navegador envia um `GET /index.html`.
4. HTTP Response: O servidor envia o código HTML (a estrutura da página).

***

### 2. Protocolos de Acesso Remoto: O perigo do Texto Simples

Aqui está uma lição fundamental de segurança:

* Telnet (Porta 23 TCP): Inseguro. Tudo o que você digita (usuário, senha, comandos) viaja em texto puro. Um atacante na mesma rede usando um _sniffer_ (como o Wireshark) pode ler sua senha facilmente.
* SSH (Porta 22 TCP): Seguro. Cria um túnel criptografado. Mesmo que o tráfego seja capturado, o conteúdo é ilegível sem a chave.

> Insight para Red Team: Em testes de invasão, encontrar o Telnet habilitado em roteadores ou servidores antigos é um "presente", pois permite capturar credenciais de administradores.

***

### 3. Transferência de Arquivos e E-mail

#### FTP (File Transfer Protocol)

O FTP é único porque usa duas portas:

* Porta 21: Para comandos (login, listar arquivos).
* Porta 20: Para a transferência dos dados em si.

#### E-mail (A tríade de protocolos)

* SMTP (Porta 25): Para enviar e-mail (do seu PC para o servidor ou entre servidores).
* POP3 (Porta 110): Para baixar e-mails. Geralmente apaga do servidor após baixar.
* IMAP (Porta 143): Para sincronizar. O e-mail fica no servidor (ideal para usar em vários dispositivos).

***

### 4. Identificadores: URI, URL e URN

Para não confundir mais:

* URI (O Identificador): O conceito geral.
* URL (O Localizador): Inclui o protocolo e o endereço (ex: `https://www.cisco.com/index.html`).
* URN (O Nome): Apenas o nome do recurso, sem dizer como chegar lá (ex: `urn:isbn:0451450523`).
