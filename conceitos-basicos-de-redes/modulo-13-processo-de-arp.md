# Módulo 13: Processo de ARP

## MAC e IP

### Comunicação na Mesma Rede (Local)

Quando o PC1 quer falar com o PC2 na mesma LAN:

* Camada 3 (IP): O IP de origem é o do PC1 e o de destino é o do PC2.
* Camada 2 (MAC): O PC1 verifica sua Tabela ARP. Se não tiver o MAC do PC2, ele envia um ARP Request (Broadcast). O PC2 responde com seu MAC.
* O Quadro: O endereço MAC de destino é o do próprio PC2.

***

### Comunicação em Redes Remotas (Roteamento)

Aqui é onde muitos estudantes se confundem. Quando o destino está em outra rede:

* O IP nunca muda: O IP de destino no pacote permanece sendo o do host remoto (ex: o servidor na Internet).
* O MAC muda a cada "salto": 1. O PC1 percebe que o IP está em outra rede e envia o quadro para o seu Gateway Padrão (Roteador). O MAC de destino será o do Roteador. 2. O Roteador remove o cabeçalho da Camada 2, olha o IP de destino, decide para onde enviar e coloca um novo cabeçalho de Camada 2 com o MAC do próximo salto.

> Regra de Ouro: O endereço IP é o destino final (o CEP da casa), o endereço MAC é o transporte local (quem entrega na próxima esquina).

***

### Broadcast e Domínios de Colisão

* O que é um Broadcast? É um grito para a rede inteira (`FF-FF-FF-FF-FF-FF`).
* Quem barra o Broadcast? O Roteador. Switches apenas replicam o broadcast para todos na mesma rede. Por isso, usamos roteadores para segmentar a rede e evitar que o tráfego de broadcast consuma toda a banda (excessivo tráfego ARP, por exemplo).

| **Característica** | **IPv4 (ARP)**       | **IPv6 (ND)**              |
| ------------------ | -------------------- | -------------------------- |
| Protocolo          | ARP                  | ICMPv6                     |
| Método             | Broadcast            | Multicast (mais eficiente) |
| Função             | Descobrir MAC via IP | Descobrir MAC via IP       |

