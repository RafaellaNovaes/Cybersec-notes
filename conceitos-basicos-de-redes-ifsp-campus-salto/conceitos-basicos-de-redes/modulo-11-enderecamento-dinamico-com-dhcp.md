# Módulo 11: Endereçamento dinâmico com DHCP

### Endereçamento Estático (Manual)

É como atribuir um número de casa fixo e imutável. Você vai até o dispositivo e digita as informações.

* O que configurar: IP, Máscara de Sub-rede e Gateway Padrão.
* Quando usar:
  * Servidores: Para que os usuários sempre saibam onde encontrar o serviço.
  * Impressoras de Rede: Evita que o atalho no computador pare de funcionar.
  * Dispositivos de Infraestrutura: Roteadores e switches.
*   Desvantagens: Alto risco de erro humano (digitação) e difícil de gerenciar em redes grandes (requer uma planilha de controle rigorosa).\
    <br>

    ### Endereçamento Dinâmico (DHCP)

    O DHCP (Dynamic Host Configuration Protocol) funciona como um sistema de "aluguel" automático. Quando um dispositivo se conecta, ele pergunta: _"Alguém tem um IP para me emprestar?"_ e o servidor responde.

    #### O Processo DORA

    As quatro etapas da conversa entre o cliente e o servidor são fáceis de lembrar pela sigla DORA:

    1. D (Discovery): O cliente envia um broadcast procurando um servidor DHCP.
    2. O (Offer): O servidor oferece um endereço IP disponível.
    3. R (Request): O cliente aceita a oferta e solicita aquele IP formalmente.
    4.  A (Acknowledgment): O servidor confirma e "aluga" o IP ao cliente por um tempo determinado (_lease time_).\
        <br>

        | **Característica** | **Estático**                          | **Dinâmico (DHCP)**                       |
        | ------------------ | ------------------------------------- | ----------------------------------------- |
        | Configuração       | Manual (Host por host)                | Automática (Centralizada no servidor)     |
        | Risco de Erro      | Alto (IPs duplicados)                 | Baixo (O servidor controla a lista)       |
        | Flexibilidade      | Baixa (Ruim para dispositivos móveis) | Alta (Ideal para Wi-Fi e redes grandes)   |
        | Uso Ideal          | Dispositivos de infraestrutura        | Dispositivos de usuários (PCs, celulares) |



### Onde mora o Servidor DHCP?

* Redes Médias/Grandes: Geralmente é um servidor dedicado (Windows Server ou Linux).
* Redes Domésticas: O próprio Roteador Wi-Fi faz esse papel. Ele recebe um IP público do Provedor (ISP) e distribui IPs privados para sua TV, celular e notebook.
