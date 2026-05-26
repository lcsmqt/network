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
