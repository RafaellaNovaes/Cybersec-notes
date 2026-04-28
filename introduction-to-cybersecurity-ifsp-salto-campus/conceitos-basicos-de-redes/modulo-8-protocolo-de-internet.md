# Módulo 8 : protocolo de internet

### O que é o Endereço IPv4?

O endereço IPv4 funciona como o "endereço residencial" de um dispositivo na rede. Para que um host (computador, servidor, celular) acesse a internet ou se comunique em uma rede local (LAN), ele precisa de um endereço lógico exclusivo.

* Atribuição: O IP é atribuído à NIC (Placa de Rede) do dispositivo.
* Múltiplos IPs: Lembre-se que um único dispositivo (como um servidor ou roteador) pode ter várias placas de rede, e cada uma terá seu próprio endereço IPv4.
* Origem e Destino: Todo pacote de dados trafegando na rede carrega o IP de quem enviou (Origem) e para onde ele vai (Destino).

### Estrutura do Endereço (Bits e Octetos)

Para o computador, tudo é binário ($$ $0$ $$ e $$ $1$ $$), mas para nós humanos, usamos a Notação Decimal com Ponto.

#### A Hierarquia do Endereço:

* Tamanho Total: 32 bits.
* Divisão: 4 grupos de 8 bits cada.
* Nome dos Grupos: Octetos (porque cada grupo tem 8 bits).



| **Formato**        | **Representação**                           |
| ------------------ | ------------------------------------------- |
| Binário Puro       | `11010001101001011100100000000001`          |
| Binário com Pontos | `11010001 . 10100101 . 11001000 . 00000001` |
| Decimal com Ponto  | `209 . 165 . 200 . 1`                       |

### A Estrutura Hierárquica: Rede vs. Host

Imagine o endereço IP como um número de telefone com DDD: `(11) 98765-4321`.

* O DDD (11) identifica a região (Rede).
* O Número (98765-4321) identifica o telefone específico (Host).

No IPv4, ocorre o mesmo. O endereço de 32 bits é dividido em duas partes:

1. Porção de Rede (Network): Identifica em qual "grupo" ou "departamento" o dispositivo está. Todos os dispositivos na mesma rede local devem ter a mesma porção de rede.
2. Porção de Host: Identifica o dispositivo específico dentro daquela rede. Cada host deve ter um número único dentro daquela rede.

### A Máscara de Sub-rede (Subnet Mask)

Como o computador sabe onde termina a rede e começa o host? Através da Máscara de Sub-rede.

* No exemplo , a máscara é `255.255.255.0`.
* Onde houver `255`, o IP representa a Rede.
* Onde houver `0`, o IP representa o Host.

#### Exemplo Prático do texto:

Se o IP é 192.168.5.11 com máscara 255.255.255.0:

* Rede: `192.168.5`
* Host: `.11`

### Redes Lógicas vs. Redes Físicas

Este ponto é muito interessante para segurança: você pode ter vários computadores ligados no mesmo "fio" (rede física), mas se eles tiverem endereços de redes lógicas diferentes, eles não se comunicam sem um roteador.

* Rede A: 192.168.18.x
* Rede B: 192.168.5.x

Mesmo que estejam no mesmo switch, o computador da Rede A é "surdo" para a Rede B. Para um atacante de Red Team, se você mudar seu IP para a mesma rede lógica do alvo, você consegue começar a "ouvir" e interagir com ele.&#x20;













