# Redes de Computadores — Básico

## Conceitos estudados

- IP
- DNS
- DHCP
- Gateway
- Máscara de sub-rede
- Roteador
- Switch
- Wi-Fi
- Ping
- Tracert

## Comandos úteis no Windows

```bash
ipconfig
ping google.com
tracert google.com
nslookup google.com
netstat
```

---

# Conceitos Básicos de Redes

Repositório criado para armazenar meus estudos sobre redes de computadores, modelo OSI, TCP/IP, switching, endereçamento MAC e funcionamento das camadas de rede.

---

# Modelo OSI vs TCP/IP

## Modelo OSI (7 camadas)

1. Aplicação
2. Apresentação
3. Sessão
4. Transporte
5. Rede
6. Enlace de Dados
7. Física

## Modelo TCP/IP (4 camadas)

1. Aplicação
2. Transporte
3. Internet
4. Acesso à Rede

---

# Diferenças entre OSI e TCP/IP

O modelo OSI é um modelo teórico criado para padronizar a comunicação em redes.

O modelo TCP/IP é utilizado na prática na Internet moderna.

O TCP/IP agrupa algumas camadas do modelo OSI:

- Aplicação + Apresentação + Sessão → Aplicação
- Transporte → Transporte
- Rede → Internet
- Enlace + Física → Acesso à Rede

---

# Encapsulamento

Durante a comunicação os dados passam pelas camadas da rede:

Dados → Segmento → Pacote → Quadro → Bits

---

# Conceitos importantes

## Switch
Opera na camada 2 (Enlace de Dados) e utiliza endereços MAC para encaminhar quadros.

## Endereço MAC
Identificador físico da placa de rede.

## FCS
Campo utilizado para verificar erros de transmissão.


# 🌐 Resumo Completo — Endereçamento IPv4

## 📖 O que é IPv4?

O IPv4 (Internet Protocol Version 4) é um endereço lógico usado para identificar dispositivos dentro de uma rede.

Exemplo:

```txt
192.168.1.10
```

Ele funciona como um “endereço” do dispositivo na rede, permitindo que computadores, celulares, impressoras, servidores e roteadores consigam se comunicar.

Sem um endereço IP, um dispositivo não consegue acessar a internet ou se comunicar com outros dispositivos.

---

# 🧠 Estrutura do IPv4

Um endereço IPv4 possui:

```txt
32 bits
```

Esses 32 bits são divididos em:

```txt
4 octetos
```

Exemplo:

```txt
192.168.1.10
```

Cada número separado por ponto é um octeto.

---

# 🔹 Octetos

Cada octeto possui:

```txt
8 bits
```

Por isso:

```txt
8 + 8 + 8 + 8 = 32 bits
```

Cada octeto pode variar de:

```txt
0 até 255
```

Exemplo válido:

```txt
192.168.1.10
```

Exemplo inválido:

```txt
192.168.300.1
```

Porque o número 300 ultrapassa o limite permitido.

---

# 🔹 IPv4 em Binário

Os computadores trabalham em binário.

Exemplo:

```txt
11000000.10101000.00000001.00001010
```

Mas como isso é difícil para humanos entenderem, usamos a forma decimal com ponto:

```txt
192.168.1.10
```

---

# 🏠 Rede e Host

Um endereço IPv4 possui duas partes:

```txt
Parte da rede + Parte do host
```

---

## 🔹 Parte da Rede

A parte da rede identifica em qual rede o dispositivo está.

---

## 🔹 Parte do Host

A parte do host identifica qual dispositivo é aquele dentro da rede.

---

## 📌 Exemplo

```txt
IP: 192.168.1.50
Máscara: 255.255.255.0
```

Resultado:

```txt
Rede: 192.168.1.0
Host: 50
```

---

# 🎭 Máscara de Sub-rede

A máscara de sub-rede define qual parte do IP representa a rede e qual representa o host.

Exemplo:

```txt
255.255.255.0
```

Significa:

```txt
Os 3 primeiros octetos representam a rede.
O último octeto representa o host.
```

---

# 🔹 Notação CIDR (/24)

Às vezes a máscara aparece assim:

```txt
192.168.1.10/24
```

O `/24` representa:

```txt
255.255.255.0
```

Isso significa que:

```txt
24 bits pertencem à rede
8 bits pertencem ao host
```

---

# 🌎 Como Saber se Dois IPs Estão na Mesma Rede?

Com máscara:

```txt
255.255.255.0
```

Os três primeiros octetos precisam ser iguais.

---

## 📌 Exemplo

```txt
192.168.1.10
192.168.1.20
192.168.1.30
```

Todos pertencem à rede:

```txt
192.168.1.0
```

---

## ❌ Exemplo de Rede Diferente

```txt
192.168.2.10
```

Esse IP pertence à rede:

```txt
192.168.2.0
```

---

# 🔀 Papel do Roteador

O roteador conecta redes diferentes.

Exemplo:

```txt
Rede da sua casa → Internet
```

Se dois dispositivos estiverem em redes diferentes, eles precisarão de um roteador para se comunicar.

---

## 📌 Exemplo

```txt
192.168.1.10
192.168.2.10
```

Esses dispositivos estão em redes diferentes.

Eles precisam de um roteador para trocar informações.

---

# 📡 Tipos de Comunicação IPv4

Existem 3 formas principais de enviar pacotes na rede:

```txt
Unicast
Broadcast
Multicast
```

---

# 🔹 Unicast

O unicast é uma comunicação:

```txt
Um para um
```

Um dispositivo envia uma mensagem para apenas um destinatário específico.

---

## 📌 Exemplo

```txt
Computador → Impressora
```

---

## 📌 Exemplo de IP

```txt
192.168.1.10
```

---

## 🧠 Comparação simples

É como enviar mensagem para apenas uma pessoa no WhatsApp.

---

# 🔹 Broadcast

O broadcast é uma comunicação:

```txt
Um para todos
```

Um dispositivo envia uma mensagem para todos os dispositivos da mesma rede.

---

## 📌 Exemplo

```txt
Computador → Todos da rede
```

---

## 📌 Broadcast Limitado

```txt
255.255.255.255
```

---

## 📌 Broadcast da Rede

Em uma rede:

```txt
192.168.1.0/24
```

O broadcast será:

```txt
192.168.1.255
```

---

## ⚠️ Problema do Broadcast

Todos os dispositivos precisam processar a mensagem.

Muito broadcast pode deixar a rede lenta.

Por isso os roteadores normalmente não encaminham broadcasts.

---

## 🧠 Comparação simples

É como alguém gritando numa sala cheia:

```txt
“Todo mundo escute!”
```

---

# 🔹 Multicast

O multicast é uma comunicação:

```txt
Um para um grupo específico
```

A mensagem é enviada apenas para dispositivos inscritos naquele grupo multicast.

---

## 📌 Intervalo Multicast IPv4

```txt
224.0.0.0 até 239.255.255.255
```

---

## 📌 Exemplo

```txt
224.10.10.5
```

---

## 🧠 Comparação simples

É como mandar mensagem em um grupo do WhatsApp.

Somente os membros daquele grupo recebem/processam a mensagem.

---

# 📊 Comparação Geral

| Tipo | Comunicação | Quem Recebe |
|---|---|---|
| Unicast | Um para um | Um dispositivo |
| Broadcast | Um para todos | Todos da rede |
| Multicast | Um para grupo | Apenas membros do grupo |

---

# 📨 IP de Origem e Destino

Todo pacote possui:

```txt
IP de origem
IP de destino
```

---

## 📌 Exemplo

```txt
Origem: 192.168.1.10
Destino: 192.168.1.20
```

O dispositivo `192.168.1.10` está enviando dados para `192.168.1.20`.

---

# 🔒 IP Privado e IP Público

---

## 🔹 IP Privado

Usado dentro de redes locais.

Exemplos:

```txt
192.168.x.x
10.x.x.x
172.16.x.x até 172.31.x.x
```

---

## 🔹 IP Público

Usado para acessar a internet.

Normalmente é atribuído pelo provedor ao roteador.

---

# 🖧 Domínio de Broadcast

Um domínio de broadcast representa todos os dispositivos que recebem um broadcast.

Os roteadores dividem domínios de broadcast.

Isso ajuda a reduzir tráfego desnecessário.

---

# 🧩 Resumo Final

O IPv4 é o endereço lógico usado para identificar dispositivos em redes.

Ele possui:

```txt
32 bits
4 octetos
Parte de rede
Parte de host
```

A máscara de sub-rede ajuda a identificar qual parte pertence à rede e qual pertence ao dispositivo.

Os principais tipos de comunicação IPv4 são:

```txt
Unicast   → um para um
Broadcast → um para todos
Multicast → um para grupo específico
```

# 🌐 Endereços IPv4 de Uso Especial e Classes IPv4

## 📖 O que são endereços IPv4 especiais?

Existem alguns endereços IPv4 que possuem funções específicas dentro das redes.

Esses endereços não são usados da mesma forma que os IPs normais atribuídos aos computadores.

Alguns exemplos:

```txt
Loopback
APIPA
Broadcast
Multicast
```

Esses endereços ajudam no funcionamento da rede, testes, comunicação interna e configuração automática.

---

# 🔄 Endereço de Loopback

Os endereços de loopback são usados quando um dispositivo envia tráfego para ele mesmo.

O mais conhecido é:

```txt
127.0.0.1
```

Também chamado de:

```txt
localhost
```

---

## 📌 Faixa de Loopback

```txt
127.0.0.0 até 127.255.255.254
```

---

## 🧠 Para que serve?

Serve para testar:

- A pilha TCP/IP
- A placa de rede virtual
- O funcionamento da configuração IP local

Mesmo sem internet, o computador consegue responder ao loopback.

---

## 📌 Exemplo

```bash
ping 127.0.0.1
```

Se houver resposta:

```txt
Reply from 127.0.0.1
```

significa que a pilha TCP/IP do sistema está funcionando corretamente.

---

## 🧠 Explicação simples

É como o computador conversar consigo mesmo.

---

# 🔗 Endereço Local de Link (APIPA)

Os endereços APIPA são usados quando o computador não consegue obter um IP automaticamente.

Exemplo:

```txt
169.254.x.x
```

---

## 📌 Faixa APIPA

```txt
169.254.0.1 até 169.254.255.254
```

---

## 🧠 O que acontece?

Normalmente um roteador entrega IP automaticamente usando DHCP.

Mas se o DHCP falhar:

```txt
O Windows cria automaticamente um IP APIPA.
```

---

## ⚠️ Problema

Com APIPA:

- geralmente não há internet
- o dispositivo só consegue comunicação limitada

---

## 🧠 Explicação simples

É como o computador dizer:

```txt
“Já que ninguém me deu um endereço, vou criar um temporário.”
```

---

# 🏛️ Endereçamento Classful (Classes IPv4)

Antigamente os IPv4 eram divididos em classes.

As classes principais eram:

```txt
Classe A
Classe B
Classe C
```

Também existiam:

```txt
Classe D → Multicast
Classe E → Experimental
```

Hoje esse sistema está praticamente obsoleto, mas ainda é muito importante para estudos de redes.

---

# 🔴 Classe A

A Classe A foi criada para redes gigantes.

---

## 📌 Faixa

```txt
0.0.0.0 até 127.255.255.255
```

---

## 📌 Máscara padrão

```txt
255.0.0.0
```

ou:

```txt
/8
```

---

## 📌 Estrutura

```txt
1 octeto = rede
3 octetos = hosts
```

---

## 📌 Quantidade de hosts

Mais de:

```txt
16 milhões de hosts
```

---

## 🧠 Exemplo

```txt
10.0.0.1
```

---

# 🟠 Classe B

A Classe B foi criada para redes médias e grandes.

---

## 📌 Faixa

```txt
128.0.0.0 até 191.255.255.255
```

---

## 📌 Máscara padrão

```txt
255.255.0.0
```

ou:

```txt
/16
```

---

## 📌 Estrutura

```txt
2 octetos = rede
2 octetos = hosts
```

---

## 📌 Quantidade de hosts

Mais de:

```txt
65 mil hosts
```

---

## 🧠 Exemplo

```txt
172.16.0.1
```

---

# 🟡 Classe C

A Classe C foi criada para redes pequenas.

---

## 📌 Faixa

```txt
192.0.0.0 até 223.255.255.255
```

---

## 📌 Máscara padrão

```txt
255.255.255.0
```

ou:

```txt
/24
```

---

## 📌 Estrutura

```txt
3 octetos = rede
1 octeto = host
```

---

## 📌 Quantidade de hosts

Até:

```txt
254 hosts
```

---

## 🧠 Exemplo

```txt
192.168.1.10
```

---

# 🔵 Classe D

Usada para:

```txt
Multicast
```

---

## 📌 Faixa

```txt
224.0.0.0 até 239.255.255.255
```

---

# ⚫ Classe E

Usada para:

```txt
Pesquisa e testes experimentais
```

---

## 📌 Faixa

```txt
240.0.0.0 até 255.255.255.255
```

---

# ❌ Problema do Sistema Classful

O sistema de classes desperdiçava muitos endereços IPv4.

Exemplo:

- Classe A tinha IPs demais
- Classe C tinha poucos IPs

Isso gerava desperdício de endereços.

---

# ✅ Surgimento do Endereçamento Sem Classe (CIDR)

Para resolver isso surgiu o:

```txt
CIDR (Classless Inter-Domain Routing)
```

O CIDR ignora as classes A, B e C.

Hoje usamos:

```txt
/24
/16
/8
/30
/27
```

etc.

Isso permite criar redes do tamanho necessário, evitando desperdício.

---

# 🌎 Endereços IPv4 Públicos e Privados

---

# 🔒 IP Privado

IPs privados são usados dentro de redes locais.

Eles NÃO funcionam diretamente na internet.

---

## 📌 Faixas Privadas

### Classe A Privada

```txt
10.0.0.0 até 10.255.255.255
```

---

### Classe B Privada

```txt
172.16.0.0 até 172.31.255.255
```

---

### Classe C Privada

```txt
192.168.0.0 até 192.168.255.255
```

---

## 🧠 Exemplos

```txt
192.168.1.10
10.0.0.5
172.16.4.10
```

---

# 🌍 IP Público

IPs públicos são usados na internet.

Eles precisam ser únicos no mundo inteiro.

---

## 🧠 Exemplos

```txt
64.104.0.22
209.165.201.30
```

---

# 🏢 Quem Controla os IPs Públicos?

A organização responsável é:

```txt
IANA
```

Ela distribui blocos de IP para os:

```txt
RIRs (Registros Regionais da Internet)
```

---

# 🌎 Principais RIRs

| Organização | Região |
|---|---|
| AfriNIC | África |
| APNIC | Ásia/Pacífico |
| ARIN | América do Norte |
| LACNIC | América Latina |
| RIPE NCC | Europa, Oriente Médio e Ásia Central |

---

# 📌 Atividade — Público ou Privado

| Endereço IP | Tipo |
|---|---|
| 172.16.35.2 | Privado |
| 192.168.3.5 | Privado |
| 192.0.3.15 | Público |
| 64.104.0.22 | Público |
| 209.165.201.30 | Público |
| 192.168.11.5 | Privado |
| 172.16.30.30 | Privado |
| 10.55.3.168 | Privado |

---

# 📚 Resumo Final

Os endereços IPv4 especiais possuem funções específicas dentro das redes.

Os principais são:

```txt
Loopback → comunicação consigo mesmo
APIPA → IP automático quando DHCP falha
Broadcast → comunicação com todos
Multicast → comunicação com grupo específico
```

Antigamente o IPv4 era dividido em:

```txt
Classe A
Classe B
Classe C
```

Hoje usamos CIDR e endereçamento sem classe para evitar desperdício de IPs.

Os endereços IPv4 também podem ser:

```txt
Privados → usados dentro da rede local
Públicos → usados na internet
```

# 🌐 Glossário de Siglas de Redes de Computadores

Este material reúne siglas importantes do mundo de redes, explicadas de forma simples para iniciantes.

---

# 📌 IP — Internet Protocol

O IP é o protocolo responsável por identificar dispositivos em uma rede.

Exemplo:

```txt
192.168.1.10
```

Ele funciona como o endereço de um dispositivo.

---

# 📌 IPv4 — Internet Protocol Version 4

É a versão 4 do protocolo IP.

Exemplo:

```txt
192.168.1.10
```

Possui 32 bits e é formado por 4 octetos.

---

# 📌 IPv6 — Internet Protocol Version 6

É a versão mais nova do protocolo IP.

Foi criada porque os endereços IPv4 começaram a acabar.

Exemplo:

```txt
2001:0db8:85a3::8a2e:0370:7334
```

---

# 📌 MAC — Media Access Control

É o endereço físico da placa de rede.

Exemplo:

```txt
00:1A:2B:3C:4D:5E
```

Enquanto o IP pode mudar, o MAC é ligado ao hardware da placa de rede.

---

# 📌 NIC — Network Interface Card

É a placa de rede do dispositivo.

Pode ser:

```txt
Placa Ethernet
Adaptador Wi-Fi
Interface virtual
```

---

# 📌 LAN — Local Area Network

Rede local.

Exemplo:

```txt
Rede da sua casa
Rede de uma escola
Rede de uma empresa
```

---

# 📌 WAN — Wide Area Network

Rede de longa distância.

Exemplo:

```txt
A internet
Rede entre filiais de empresas
```

---

# 📌 WLAN — Wireless Local Area Network

Rede local sem fio.

Exemplo:

```txt
Wi-Fi da sua casa
Wi-Fi de uma empresa
```

---

# 📌 MAN — Metropolitan Area Network

Rede que cobre uma área metropolitana.

Exemplo:

```txt
Rede entre prédios de uma cidade
```

---

# 📌 PAN — Personal Area Network

Rede pessoal de curto alcance.

Exemplo:

```txt
Bluetooth entre celular e fone
```

---

# 📌 TCP — Transmission Control Protocol

Protocolo que garante entrega confiável dos dados.

Ele verifica se os dados chegaram corretamente.

Muito usado em:

```txt
Sites
E-mails
Downloads
```

---

# 📌 UDP — User Datagram Protocol

Protocolo mais rápido, porém sem garantia de entrega.

Muito usado em:

```txt
Jogos online
Chamadas de vídeo
Streaming
```

---

# 📌 HTTP — HyperText Transfer Protocol

Protocolo usado para acessar páginas da web.

Exemplo:

```txt
http://site.com
```

---

# 📌 HTTPS — HyperText Transfer Protocol Secure

Versão segura do HTTP.

Usa criptografia para proteger os dados.

Exemplo:

```txt
https://site.com
```

---

# 📌 DNS — Domain Name System

Traduz nomes de sites em endereços IP.

Exemplo:

```txt
google.com → endereço IP do Google
```

É como uma agenda telefônica da internet.

---

# 📌 DHCP — Dynamic Host Configuration Protocol

Protocolo que entrega IP automaticamente para os dispositivos.

Exemplo:

```txt
Seu celular entra no Wi-Fi e recebe um IP sozinho.
```

---

# 📌 NAT — Network Address Translation

Permite que vários dispositivos usem um único IP público para acessar a internet.

Exemplo:

```txt
Celular
Notebook
TV
Videogame
```

Todos saem para internet usando o IP público do roteador.

---

# 📌 ARP — Address Resolution Protocol

Descobre o endereço MAC de um dispositivo a partir do endereço IP.

Exemplo:

```txt
Quem tem o IP 192.168.1.10?
```

O dispositivo responde com seu MAC.

---

# 📌 ICMP — Internet Control Message Protocol

Usado para mensagens de controle e testes de rede.

O comando `ping` usa ICMP.

Exemplo:

```bash
ping 8.8.8.8
```

---

# 📌 FTP — File Transfer Protocol

Protocolo usado para transferência de arquivos.

---

# 📌 SFTP — SSH File Transfer Protocol

Versão segura para transferência de arquivos usando SSH.

---

# 📌 SSH — Secure Shell

Protocolo usado para acessar servidores remotamente com segurança.

Exemplo:

```bash
ssh usuario@servidor
```

---

# 📌 Telnet

Protocolo antigo para acesso remoto.

Não é seguro, pois não usa criptografia.

---

# 📌 SMTP — Simple Mail Transfer Protocol

Usado para envio de e-mails.

---

# 📌 POP3 — Post Office Protocol Version 3

Usado para baixar e-mails do servidor para o dispositivo.

---

# 📌 IMAP — Internet Message Access Protocol

Usado para acessar e-mails mantendo as mensagens sincronizadas no servidor.

---

# 📌 URL — Uniform Resource Locator

É o endereço de um recurso na internet.

Exemplo:

```txt
https://www.google.com
```

---

# 📌 URI — Uniform Resource Identifier

Identifica um recurso.

A URL é um tipo de URI.

---

# 📌 ISP — Internet Service Provider

Provedor de internet.

Exemplo:

```txt
Claro
Vivo
TIM
Oi
```

---

# 📌 VPN — Virtual Private Network

Cria uma conexão segura entre o dispositivo e outra rede.

Muito usada para:

```txt
Privacidade
Acesso remoto
Trabalho remoto
Segurança
```

---

# 📌 VLAN — Virtual Local Area Network

Permite dividir uma rede física em redes lógicas separadas.

Exemplo:

```txt
VLAN dos alunos
VLAN dos professores
VLAN administrativa
```

---

# 📌 WLAN — Wireless LAN

Rede local sem fio, normalmente Wi-Fi.

---

# 📌 SSID — Service Set Identifier

É o nome da rede Wi-Fi.

Exemplo:

```txt
MinhaCasa_5G
```

---

# 📌 WPA — Wi-Fi Protected Access

Padrão de segurança para redes Wi-Fi.

---

# 📌 WPA2 — Wi-Fi Protected Access 2

Versão mais segura que o WPA.

Ainda é muito usada.

---

# 📌 WPA3 — Wi-Fi Protected Access 3

Versão mais moderna e segura de proteção Wi-Fi.

---

# 📌 AP — Access Point

Ponto de acesso Wi-Fi.

É o equipamento que permite que dispositivos se conectem sem fio à rede.

---

# 📌 SSID Broadcast

É quando o roteador divulga o nome da rede Wi-Fi para os dispositivos encontrarem.

---

# 📌 BSSID — Basic Service Set Identifier

É o endereço MAC do ponto de acesso Wi-Fi.

---

# 📌 OSI — Open Systems Interconnection

Modelo usado para entender como a comunicação de rede funciona.

Possui 7 camadas:

```txt
1. Física
2. Enlace
3. Rede
4. Transporte
5. Sessão
6. Apresentação
7. Aplicação
```

---

# 📌 TCP/IP

Modelo usado na prática para comunicação na internet.

Possui camadas como:

```txt
Acesso à rede
Internet
Transporte
Aplicação
```

---

# 📌 PDU — Protocol Data Unit

Nome dado aos dados em cada camada do modelo OSI.

Exemplo:

```txt
Dados
Segmento
Pacote
Quadro
Bits
```

---

# 📌 MTU — Maximum Transmission Unit

Tamanho máximo de um pacote que pode passar por uma rede.

---

# 📌 TTL — Time To Live

Define por quanto tempo um pacote pode circular na rede.

Ajuda a evitar que pacotes fiquem circulando para sempre.

---

# 📌 QoS — Quality of Service

Usado para priorizar tipos de tráfego.

Exemplo:

```txt
Priorizar chamada de vídeo
Priorizar voz
Priorizar jogos
```

---

# 📌 VoIP — Voice over IP

Tecnologia que permite chamadas de voz pela internet.

Exemplo:

```txt
WhatsApp
Zoom
Telefone IP
```

---

# 📌 PoE — Power over Ethernet

Permite transmitir energia elétrica pelo cabo de rede.

Muito usado em:

```txt
Câmeras IP
Telefones IP
Access Points
```

---

# 📌 Ethernet

Tecnologia usada em redes cabeadas.

Exemplo:

```txt
Cabo de rede conectado ao computador
```

---

# 📌 UTP — Unshielded Twisted Pair

Cabo de par trançado sem blindagem.

Muito usado em redes Ethernet.

---

# 📌 STP — Shielded Twisted Pair

Cabo de par trançado com blindagem.

Ajuda a reduzir interferências.

---

# 📌 RJ-45

Conector usado em cabos de rede Ethernet.

---

# 📌 ISP — Internet Service Provider

Empresa que fornece acesso à internet.

---

# 📌 IANA — Internet Assigned Numbers Authority

Organização responsável por coordenar blocos de endereços IP globalmente.

---

# 📌 RIR — Regional Internet Registry

Registros regionais que distribuem endereços IP.

Exemplos:

```txt
LACNIC
ARIN
RIPE NCC
APNIC
AfriNIC
```

---

# 📌 LACNIC

Registro responsável pela América Latina e parte do Caribe.

---

# 📌 ARIN

Registro responsável pela América do Norte.

---

# 📌 APNIC

Registro responsável pela região Ásia-Pacífico.

---

# 📌 RIPE NCC

Registro responsável pela Europa, Oriente Médio e parte da Ásia Central.

---

# 📌 AfriNIC

Registro responsável pela África.

---

# 📌 CIDR — Classless Inter-Domain Routing

Forma moderna de representar redes.

Exemplo:

```txt
192.168.1.0/24
```

O `/24` indica quantos bits pertencem à parte da rede.

---

# 📌 APIPA — Automatic Private IP Addressing

Endereço automático usado quando o dispositivo não consegue obter IP pelo DHCP.

Faixa:

```txt
169.254.0.1 até 169.254.255.254
```

---

# 📌 Loopback

Endereço usado pelo dispositivo para testar a si mesmo.

Principal endereço:

```txt
127.0.0.1
```

Também conhecido como:

```txt
localhost
```

---

# 📌 localhost

Nome usado para se referir ao próprio computador.

Exemplo:

```txt
127.0.0.1
```

---

# 📌 NAT64

Técnica usada para comunicação entre redes IPv6 e IPv4.

---

# 📌 PAT — Port Address Translation

Tipo de NAT que usa portas para permitir que vários dispositivos compartilhem o mesmo IP público.

Muito comum em roteadores domésticos.

---

# 📌 DMZ — Demilitarized Zone

Área separada da rede usada para expor serviços com mais controle.

Exemplo:

```txt
Servidor web
Servidor de e-mail
```

---

# 📌 ACL — Access Control List

Lista de regras usada para permitir ou bloquear tráfego.

Muito usada em roteadores, switches e firewalls.

---

# 📌 Firewall

Sistema que filtra o tráfego de rede.

Pode bloquear ou permitir conexões com base em regras.

---

# 📌 IDS — Intrusion Detection System

Sistema que detecta possíveis invasões.

Ele alerta, mas normalmente não bloqueia automaticamente.

---

# 📌 IPS — Intrusion Prevention System

Sistema que detecta e também pode bloquear ameaças automaticamente.

---

# 📌 DoS — Denial of Service

Ataque que tenta derrubar um serviço com excesso de requisições.

---

# 📌 DDoS — Distributed Denial of Service

Ataque DoS feito por vários dispositivos ao mesmo tempo.

---

# 📌 SSL — Secure Sockets Layer

Protocolo antigo de segurança para criptografia na internet.

Foi substituído pelo TLS.

---

# 📌 TLS — Transport Layer Security

Protocolo usado para proteger conexões na internet.

É usado no HTTPS.

---

# 📌 CA — Certificate Authority

Autoridade certificadora.

Emite certificados digitais usados em conexões seguras.

---

# 📌 VPN Tunnel

Túnel criptografado criado por uma VPN.

---

# 📌 Gateway

Dispositivo que serve como saída para outra rede.

Normalmente é o roteador.

Exemplo:

```txt
Gateway padrão: 192.168.1.1
```

---

# 📌 Default Gateway

Gateway padrão configurado no dispositivo.

É usado quando o destino está fora da rede local.

---

# 📌 Subnet

Sub-rede.

É uma divisão menor dentro de uma rede maior.

---

# 📌 Subnet Mask

Máscara de sub-rede.

Define qual parte do IP é rede e qual parte é host.

Exemplo:

```txt
255.255.255.0
```

---

# 📌 Broadcast

Comunicação de um dispositivo para todos os dispositivos da rede.

---

# 📌 Multicast

Comunicação de um dispositivo para um grupo específico.

---

# 📌 Unicast

Comunicação de um dispositivo para outro dispositivo específico.

---

# 📌 SNMP — Simple Network Management Protocol

Protocolo usado para monitorar equipamentos de rede.

Exemplo:

```txt
Switches
Roteadores
Servidores
Impressoras
```

---

# 📌 NTP — Network Time Protocol

Protocolo usado para sincronizar data e hora dos dispositivos na rede.

---

# 📌 SMB — Server Message Block

Protocolo usado para compartilhamento de arquivos e impressoras em redes Windows.

---

# 📌 LDAP — Lightweight Directory Access Protocol

Protocolo usado para acessar serviços de diretório.

Exemplo:

```txt
Active Directory
```

---

# 📌 AD — Active Directory

Serviço da Microsoft usado para gerenciar usuários, computadores e permissões em uma rede.

---

# 📌 RDP — Remote Desktop Protocol

Protocolo usado para acessar computadores Windows remotamente.

---

# 📌 ICANN — Internet Corporation for Assigned Names and Numbers

Organização que coordena nomes de domínio e endereços na internet.

---

# 📌 Resumo Final

As siglas de redes representam protocolos, tecnologias, equipamentos, padrões e serviços usados para permitir comunicação entre dispositivos.

Algumas das mais importantes para iniciantes são:

```txt
IP
IPv4
IPv6
MAC
LAN
WAN
TCP
UDP
HTTP
HTTPS
DNS
DHCP
NAT
ARP
ICMP
OSI
TCP/IP
VLAN
VPN
SSID
WPA
CIDR
Gateway
Subnet Mask
```

Entender essas siglas ajuda muito em áreas como:

- Suporte técnico
- Redes de computadores
- Infraestrutura
- Segurança da informação
- Cybersegurança
- Administração de sistemas
- Cloud computing

Entender esses conceitos é essencial para:

- Redes de computadores
- Administração de sistemas
- Configuração de roteadores
- Segurança da informação
- Cybersegurança
- Infraestrutura de TI

O entendimento de IPv4 é fundamental para:

- Redes de computadores
- Segurança da informação
- Administração de sistemas
- Configuração de roteadores
- Servidores
- Cybersegurança
- Infraestrutura de TI
