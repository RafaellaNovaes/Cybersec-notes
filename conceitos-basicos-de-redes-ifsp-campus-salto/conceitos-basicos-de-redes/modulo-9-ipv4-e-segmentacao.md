# Módulo 9 : IPv4 e Segmentação

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



### Endereços Públicos vs. Privados (RFC 1918)

A internet "acabou" com os endereços IPv4 muito rápido, então criaram os endereços privados para serem usados dentro das casas e empresas.

* Públicos: Roteáveis na Internet. Precisam ser únicos no mundo todo.
* Privados: Não são roteáveis na Internet. São usados apenas na rede local (Intranet).

| **Classe** | **Intervalo**                       | **Exemplo comum**            |
| ---------- | ----------------------------------- | ---------------------------- |
| A          | `10.0.0.0` até `10.255.255.255`     | Redes corporativas gigantes. |
| B          | `172.16.0.0` até `172.31.255.255`   | Redes médias/universidades.  |
| C          | `192.168.0.0` até `192.168.255.255` | Sua casa (roteador Wi-Fi).   |

### O papel do NAT (Network Address Translation)

Como os IPs privados não funcionam na internet, o seu roteador faz um "truque":

1. Ele recebe o pacote do seu PC (IP Privado).
2. Ele troca o seu IP pelo IP Público dele.
3. Envia para a Internet.
4. Quando a resposta volta, ele traduz de volta para você.

### Endereços Especiais (Cuidado com estes!)

* Loopback (`127.0.0.0/8`): O famoso "não há lugar como o nosso `127.0.0.1`". Serve para o computador falar com ele mesmo. Útil para testar se a sua placa de rede está funcionando.
* Link-Local / APIPA (`169.254.0.0/16`): Se o seu PC aparecer com esse IP, algo está errado. Significa que ele não conseguiu falar com o servidor DHCP e "inventou" um IP para não ficar totalmente isolado.

### Endereçamento Classful (O Legado)

Antigamente, a máscara era definida pela "cara" do IP (Classe A, B ou C). Hoje usamos o Classless (Sem classe), onde qualquer IP pode ter qualquer máscara

| **Classe** | **Primeiro Octeto** | **Máscara Padrão**    | **Capacidade de Hosts** |
| ---------- | ------------------- | --------------------- | ----------------------- |
| A          | 1 a 126             | `/8` (255.0.0.0)      | 16 milhões+             |
| B          | 128 a 191           | `/16` (255.255.0.0)   | 65.534                  |
| C          | 192 a 223           | `/24` (255.255.255.0) | 254                     |

\*O endereço 127 foi "pulado" porque é reservado para o Loopback.

### Quem manda no IP?

A IANA é a "chefona" global. Ela distribui os IPs para os RIRs (Registros Regionais). No nosso caso (América Latina e Caribe), o órgão responsável é o LACNIC.



## Segmentação de Rede

### O que é um Domínio de Broadcast?

Imagine uma sala de aula. Se um aluno grita "Alguém tem uma caneta?", todos na sala ouvem. Essa sala é o Domínio de Broadcast.

* O Switch é o facilitador: Ele espalha o grito por todas as portas. Se o switch recebe um broadcast, ele replica para todo mundo.
* O Roteador é a parede: Ele não deixa o broadcast passar. O roteador separa as salas. Se você grita na sala A, quem está na sala B (atrás do roteador) não ouve nada.

### Por que domínios grandes são ruins?

O texto menciona uma rede com 400 usuários. Imagine 400 pessoas gritando ao mesmo tempo "Cadê a impressora?" (ARP) ou "Me dá um IP?" (DHCP).

1. Rede Lenta: O cabo fica ocupado com "gritos" em vez de dados reais.
2. Dispositivos Lentos: Cada computador é obrigado a parar o que está fazendo para ouvir o broadcast, mesmo que a mensagem não seja para ele.
3. Segurança (Ponto chave para você!): Em um domínio de broadcast grande, um atacante pode fazer um ARP Spoofing com muito mais facilidade, interceptando o tráfego de centenas de pessoas de uma vez.

### A Solução: Sub-redes (Subnetting)

Para resolver isso, "cortamos" a rede grande em pedaços menores.

* Antes: Uma rede `/16` (65.534 endereços possíveis). É gente demais no mesmo domínio!
* Depois: Duas redes `/24` (254 endereços cada).

Note o que aconteceu com os IPs no exemplo:

* LAN 1: `172.16.0.0/24`
* LAN 2: `172.16.1.0/24`

Agora, se um computador na LAN 1 enviar um broadcast, os usuários da LAN 2 ficam em silêncio e tranquilos, porque o Roteador R1 barrou a mensagem.

### Por que segmentar? (Visão de Segurança)

Como futura profissional de segurança, grave estes motivos:

1. Performance: Menos tráfego desnecessário.
2. Segurança: Você pode colocar o "Departamento de RH" em uma sub-rede e o "Departamento de Vendas" em outra. Com o roteador no meio, você pode criar regras (ACLs) dizendo: _"Vendas não podem acessar os IPs do RH"_.
3. Contenção: Se um vírus (como um ransomware) começar a se espalhar via broadcast em uma sub-rede, o roteador impede que ele "pule" automaticamente para as outras.



