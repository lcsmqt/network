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
