# 🧪 SOC Lab Simulations: Projetos Práticos de Detecção de Ameaças

## 🎯 Objetivo do Repositório

Simular situações reais de um analista SOC e aplicar técnicas práticas de detecção de ameaças com ferramentas como **Wireshark**, **Suricata** e arquivos `.pcap`.

Cada projeto demonstra:

- 📡 Análise de tráfego para encontrar sinais de ataque  
- ⚠️ Reconhecimento de padrões maliciosos (Brute Force, Port Scan, DNS Beaconing)  
- 🧠 Pensamento analítico de um verdadeiro analista de segurança

---

## 📁 Projetos Concluídos

### 1. 🔐 FTP Brute Force Detection (Wireshark)

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

---

### 2. 🚨 Port Scan Detection (Suricata + Wireshark)

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

### 3. 🛰️ DNS Beaconing Detection (Wireshark)

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

## 📌 Por que isso importa?

Esses projetos **não são só exercícios**. Eles mostram que eu:

✅ Sei interpretar tráfego malicioso  
✅ Consigo usar ferramentas reais de mercado  
✅ Tenho raciocínio SOC voltado para **ações práticas e imediatas**
