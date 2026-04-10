# Módulo 9 :

#### Unicast: Comunicação Direta (1 para 1)

É o tipo mais comum. É como uma conversa privada entre você e uma pessoa específica.

* Origem: Sempre um único dispositivo (unicast).
* Destino: Um endereço específico (ex: o IP da impressora `172.16.4.253`).
* Intervalo: De `1.1.1.1` até `223.255.255.255`.
* Dica /24: O material mencionou que a máscara `255.255.255.0` pode ser escrita como /24. Isso significa que os primeiros 24 bits (3 octetos de 8 bits) são a rede.

#### Broadcast: O "Grito" na Rede (1 para Todos)

O dispositivo envia uma mensagem e todos na mesma rede local são obrigados a processar esse pacote.

* Endereço Especial: `255.255.255.255` (Broadcast Limitado).
* Comportamento do Switch: O switch envia para todas as portas.
* Comportamento do Roteador: O roteador bloqueia o broadcast. Ele não deixa esse "grito" passar para outras redes (Internet ou outros departamentos), limitando o que chamamos de Domínio de Broadcast.
* Uso: Muito usado para descobrir serviços (como quando seu PC pede um IP via DHCP).

#### Multicast: O Grupo de Interesse (1 para Vários)

É como uma lista de transmissão no WhatsApp ou um canal de TV a cabo: você só recebe se estiver "inscrito" no grupo.

* Intervalo Reservado: `224.0.0.0` até `239.255.255.255`.
* Vantagem: Reduz o tráfego. Em vez de enviar 10 pacotes unicast para 10 pessoas, a fonte envia um único pacote para o endereço do grupo (ex: `224.0.0.5`), e o switch/rede entrega para quem se inscreveu.
* Clientes Multicast: Dispositivos que "assinam" o serviço.



Dicas:

* Broadcast: Se você "escutar" (sniffing) transmissões de broadcast, pode descobrir servidores DHCP ou nomes de máquinas na rede sem precisar atacar ninguém diretamente.
* Multicast: Protocolos de roteamento (como OSPF) usam multicast. Se um atacante consegue se passar por um roteador no grupo multicast, ele pode desviar o tráfego de toda a empresa para a máquina dele.
* Notação /24: Você verá muito isso em ferramentas como o Nmap (ex: `nmap -sP 192.168.1.0/24`). É o jeito profissional de dizer "escaneie toda essa sub-rede".
