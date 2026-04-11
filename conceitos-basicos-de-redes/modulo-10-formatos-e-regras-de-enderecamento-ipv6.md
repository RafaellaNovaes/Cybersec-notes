# Módulo 10 : Formatos e Regras de endereçamento IPv6

### Estrutura do Endereço IPv6

Um endereço IPv6 é composto por 128 bits, divididos em 8 hextetos (segmentos de 16 bits), separados por dois pontos (`:`).

Cada dígito hexadecimal representa 4 bits ($$ $2^4 = 16$ $$). Portanto:

* 1 Hexteto = 4 dígitos hexadecimais = 16 bits.
* 8 Hextetos = 32 dígitos hexadecimais = 128 bits.

***

### 2. As Duas Regras de Ouro da Compactação

Para facilitar a escrita, aplicamos estas regras em ordem:

#### Regra 1: Omitir Zeros à Esquerda

Em qualquer hexteto, você pode remover os zeros que aparecem antes de outros números.

* Exemplo: `0db8` vira `db8`
* Exemplo: `000a` vira `a`
* Exemplo: `0000` vira `0` (você deve deixar pelo menos um zero se o hexteto for todo zerado nesta fase).

#### Regra 2: Os Dois Pontos Duplos (`::`)

Você pode substituir qualquer sequência contínua de hextetos compostos apenas por zeros por um sinal de dois pontos duplo (`::`).

* Regra Crucial: Você só pode usar o `::` uma única vez por endereço. Se usar duas vezes, o computador não saberá quantos zeros existem em cada lacuna.

***

### 3. Exemplo Prático de Transformação

Vamos aplicar as regras passo a passo no endereço:

`2001 : 0db8 : 0000 : 0000 : 0000 : ab00 : 0000 : 0001`

1. Original: `2001:0db8:0000:0000:0000:ab00:0000:0001`
2.  Aplicando Regra 1 (Zeros à esquerda): `2001:db8:0:0:0:ab00:0:1`

    _(Note que `ab00` não muda, pois os zeros estão à direita!)_
3.  Aplicando Regra 2 (Dois pontos duplos): `2001:db8::ab00:0:1`

    _(Substituímos a maior sequência de zeros, que eram os três hextetos centrais)._

***

### 4. Dica de "Melhor Prática"

Como mencionado no seu texto, se houver duas sequências de zeros de tamanhos iguais, como em:

`fe80:0000:0000:abcd:0000:0000:0001`

A recomendação é comprimir a primeira sequência:

`fe80::abcd:0:0:1` (Embora `fe80:0:0:abcd::1` também seja tecnicamente válido, a primeira forma é o padrão visual).
