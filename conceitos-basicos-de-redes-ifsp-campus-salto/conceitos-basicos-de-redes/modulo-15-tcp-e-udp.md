# Módulo 15: TCP e UDP

### TCP vs. UDP: O Duelo da Entrega

A grande diferença reside na Confiabilidade versus Velocidade.

#### TCP (Transmission Control Protocol)

É o protocolo "educado" e garantido. Ele estabelece uma conexão antes de enviar dados.

* Confiável: Se um pacote sumir, ele pede de novo (Retransmissão).
* Sequenciado: Os pacotes chegam e são organizados na ordem correta.
* Controle de Fluxo: Ajusta a velocidade conforme a qualidade da rede.
* Exemplos: Navegação Web (HTTP/S), E-mail (SMTP), Transferência de arquivos (FTP).

#### UDP (User Datagram Protocol)

É o protocolo "fale e esqueça". Ele não quer saber se você ouviu, ele apenas envia.

* Sem Conexão: Não há aviso prévio, apenas o envio (baixa sobrecarga/overhead).
* Não Confiável: Se perder um pacote, o vídeo "engasga" um segundo, mas continua.
* Rápido: Ideal para tempo real.
* Exemplos: Streaming de vídeo, Chamadas de voz (VoIP), Consultas DNS, Jogos online.

***

### 2. Portas e Sockets: O Sistema de Endereçamento

Se o IP é o endereço do prédio, a Porta é o número do apartamento.

#### Categorias de Portas:

1. Bem Conhecidas (0 - 1023): Reservadas para serviços padrão (ex: 80 para Web, 21 para FTP, 53 para DNS).
2. Registradas (1024 - 49151): Para aplicações específicas de empresas.
3. Dinâmicas/Privadas (49152 - 65535): Usadas pelo seu PC como "Porta de Origem" quando você abre uma conexão.

#### O que é um Socket?

Um Socket é a combinação de Endereço IP + Número da Porta.

* Exemplo: `192.168.1.5:1099`
* O Socket Pair (par de sockets) é o que identifica uma conversa única entre seu PC e um servidor na internet.

***

### 3. Visão de Cybersecurity (Offensive)

Como você está estudando para Red Team, preste atenção nestes pontos:

* Port Scanning (Nmap): Quando usamos ferramentas de scan, estamos basicamente batendo em várias portas (sockets) para ver quais respondem. Se a porta 80 responde, sabemos que há um servidor Web ali.
* Comando `netstat`: É sua primeira ferramenta de defesa e análise. No terminal, use `netstat -an` (o `-n` mostra números em vez de nomes) para ver quem está conectado à sua máquina agora.
  * _Dica:_ Se vir uma conexão `ESTABLISHED` em uma porta estranha para um IP desconhecido, pode ser um sinal de um artefato malicioso ou um "shell" reverso.

#### Resumo de Portas Importantes para Decorar:

| **Serviço** | **Porta** | **Protocolo**      |
| ----------- | --------- | ------------------ |
| FTP         | 21        | TCP                |
| SSH         | 22        | TCP                |
| DNS         | 53        | UDP (quase sempre) |
| HTTP        | 80        | TCP                |
| HTTPS       | 443       | TCP                |
