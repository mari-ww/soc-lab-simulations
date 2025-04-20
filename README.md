# 🧪 SOC Lab Simulations: Projetos Práticos de Detecção de Ameaças

[![Status](https://img.shields.io/badge/status-concluído-brightgreen)]()
[![Nível](https://img.shields.io/badge/nível-intermediário-orange)]()
[![Ferramentas](https://img.shields.io/badge/ferramentas-Wireshark%20%7C%20Suricata-purple)]()

## 📦 Estrutura

```bash
├── 01-brute-force/                  <- Link FTP Brute Force com Wireshark
│   └── README.md
├── 02-port-scan-suricata/          <- Link Port Scan com Suricata + Wireshark
│   └── README.md
├── 03-dns-tunneling/               <- Link DNS Tunneling Detection
│   └── README.md
├── README.md                       <- Este arquivo
└── Relatório_final.pdf            <- Relatório final com análise dos três projetos
```

## 🎯 Objetivo do Repositório

Simular situações reais de um analista SOC e aplicar técnicas práticas de detecção de ameaças com ferramentas como **Wireshark**, **Suricata** e arquivos `.pcap`.

Cada projeto demonstra:

- 📡 Análise de tráfego para encontrar sinais de ataque  
- ⚠️ Reconhecimento de padrões maliciosos (Brute Force, Port Scan, DNS Beaconing)  
- 🧠 Pensamento analítico de um verdadeiro analista de segurança

## 📁 Projetos Concluídos

### [1. 🔐 FTP Brute Force Detection (Wireshark)](https://github.com/mari-ww/wireshark-brute-force)

- **Alvo:** FTP (porta 21)  
- **Ataque Detectado:** Tentativas automáticas de login com usuário `bro` e várias senhas  

**🧪 Filtros usados no Wireshark:**
```bash
ftp.request.command == "USER"
ftp.request.command == "PASS"
ftp.response.arg == "Login incorrect."
```
**🧠 Conclusão:**
Padrão típico de brute force com tentativas contínuas e falhas repetidas.

**💪 Habilidade demonstrada:** Reconhecimento de anomalias em autenticação

### [2. 🚨 Port Scan Detection (Suricata + Wireshark)](https://github.com/mari-ww/port-scan-suricata)

- **Simulação:** Port scan com Nmap

**🔍 Análise Manual:**
- Pacotes SYN enviados em sequência sem resposta SYN-ACK
- Wireshark mostra tentativa de sondagem sem conexão completa

**🤖 Análise Automática (IDS):**
- Suricata com regra personalizada
- Alerta disparado: `"SYN Port Scan Detected"`

**🧠 Conclusão:**
Combinação de análise manual + IDS para validação cruzada.

**💪 Habilidade demonstrada:** Escrita de regras e correlação visual com pacotes

---

### [3. 🛰️ DNS Beaconing Detection (Wireshark)](https://github.com/mari-ww/dns-tunneling-detection)

- **Arquivo analisado:** `dnscat2_dns_tunneling_24hr.pcap`

**🧩 Sinais Detectados:**
- Domínios longos e obscuros
- Padrões temporais regulares (beaconing)
- Requisições DNS repetidas

**🔧 Técnicas Aplicadas:**
- Filtros: `dns.qry.name`
- Análise gráfica de envio de pacotes

**🧠 Conclusão:**
Indícios claros de C2 (Command & Control) via DNS

**💪 Habilidade demonstrada:** Identificação de comportamento furtivo e persistente (APT)

---

## 🔍 Visão Técnica Geral

| Projeto            | Técnica de Detecção          | Ferramentas               | Habilidade SOC                               |
|--------------------|------------------------------|---------------------------|-----------------------------------------------|
| FTP Brute Force    | Manual via Wireshark         | Wireshark                 | Análise de autenticação + filtros             |
| Port Scan          | IDS + Visual (Wireshark)     | Suricata + Wireshark      | Escrita de regras + padrão de scan            |
| DNS Beaconing      | Manual via Wireshark         | Wireshark                 | Detecção de C2 e persistência furtiva         |

---

## ✅ Conclusão

Esses projetos demonstram minha capacidade de aplicar técnicas práticas de detecção de ameaças em ambientes simulados, utilizando ferramentas comuns no mercado. Eu sou capaz de:

- Detectar ataques comuns como brute force, port scans e DNS beaconing.
- Utilizar ferramentas como **Wireshark** e **Suricata** para análise de tráfego e identificação de anomalias.
- Escrever regras personalizadas para melhorar a detecção de ataques.

Esses projetos **não são apenas exercícios**; eles são experiências reais de detecção de ameaças no contexto de um analista SOC.

## 🧰 Ferramentas Usadas

- **Wireshark:** Para análise de pacotes e tráfego de rede.
- **Suricata:** Para detecção de intrusões e criação de regras personalizadas de IDS.
- **Nmap:** Para simulação de ataques como port scans.
