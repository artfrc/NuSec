
# Cybersecurity Notes: Offensive and Defensive Security

## 🛡️ Offensive Security

### 🔍 Ferramenta: Gobuster

**Gobuster** é uma ferramenta utilizada para descobrir páginas ocultas em sites, geralmente utilizada durante testes de penetração.

#### 💻 Exemplo de uso no terminal:

```bash
gobuster -u http://fakebank.thm -w wordlist.txt dir
```

#### 🔑 Parâmetros:

- `-u`: Indica a URL alvo
- `-w`: Define a wordlist com possíveis nomes de diretórios/páginas

#### ✅ Interpretação de Resultados:

- Códigos de status **200** indicam que a página foi encontrada com sucesso.
- Outros códigos úteis: 204, 301, 302, 307, 403

#### 📋 Exemplo de saída:

```
=====================================================
Gobuster v2.0.1              OJ Reeves (@TheColonial)
=====================================================
[+] Mode         : dir
[+] Url/Domain   : http://fakebank.thm/
[+] Threads      : 10
[+] Wordlist     : wordlist.txt
[+] Status codes : 200,204,301,302,307,403
[+] Timeout      : 10s
=====================================================
2025/05/24 02:42:16 Starting gobuster
=====================================================
/images (Status: 301)
/bank-transfer (Status: 200)
=====================================================
2025/05/24 02:42:26 Finished
=====================================================
```

---

### 👥 Perfis Profissionais em Segurança Ofensiva

#### 🇺🇸 In English:

- **Penetration Tester**: Responsible for testing technology products for finding exploitable security vulnerabilities.
- **Red Teamer**: Plays the role of an adversary, attacking an organization and providing feedback from an enemy's perspective.
- **Security Engineer**: Design, monitor, and maintain security controls, networks, and systems to help prevent cyberattacks.

#### 🇧🇷 Em Português:

- **Testador de Penetração**: Responsável por testar produtos de tecnologia para encontrar vulnerabilidades de segurança exploráveis.
- **Red Teamer**: Desempenha o papel de um adversário, atacando uma organização e fornecendo feedback da perspectiva de um inimigo.
- **Engenheiro de Segurança**: Projeta, monitora e mantém controles de segurança, redes e sistemas para ajudar a prevenir ataques cibernéticos.

---

## 🔐 Defensive Security

### 🛰️ Security Operations Center (SOC)

#### 🇺🇸 English

- Team that monitors 24/7 to detect and respond to threats
- Key focus areas:
  - **Vulnerabilities**: Patching and applying workarounds
  - **Policy violations**: Preventing data leaks and misconfigurations
  - **Network intrusions**: Detecting phishing and exploitation attempts

#### 🇧🇷 Português

- Equipe especializada em detecção e resposta a incidentes 24/7
- Atuação em:
  - **Vulnerabilidades**: Prioriza correções baseadas em risco
  - **Violações**: Monitora vazamentos em cloud storage não autorizado
  - **Intrusões**: Responde a acessos não autorizados via credenciais roubadas

---

### 📡 Threat Intelligence (Inteligência de Ameaças)

#### 🇺🇸 English

**Threat Intelligence Full Cycle:**

1. **Collection**: Logs, forums, threat feeds
2. **Processing**: Data normalization
3. **Analysis**: Identifying TTPs (Tactics, Techniques, and Procedures)

**Goal**: Anticipate attacks by profiling adversaries.

#### 🇧🇷 Português

**Processo contínuo para:**

- Coletar dados de redes internas e fontes abertas
- Processar informações em formatos analisáveis
- Produzir **IOCs** (Indicadores de Comprometimento)

**Resultado**: Defesa proativa contra ameaças conhecidas.

---

### 🔎 DFIR (Digital Forensics and Incident Response)

#### 📁 Forense Digital

##### 🇺🇸 English

- **File System**: Analyzes hidden/deleted files
- **Memory**: Captures malware resident in RAM
- **Logs**: Rebuilds activity even after cover-up attempts

##### 🇧🇷 Português

- **Sistemas de Arquivo**: Recupera metadados e timestamps
- **Memória**: Analisa processos maliciosos voláteis
- **Registros/Logs**: Correlaciona eventos em múltiplos sistemas

---

#### 🚨 Incident Response

##### 🇺🇸 English

1. **Preparation**: Trained team and clear policies
2. **Detection**: Continuous monitoring
3. **Containment**: Isolate threat
4. **Eradication**: Completely remove threat
5. **Recovery**: Securely restore operations
6. **Lessons Learned**: Improve for future response

##### 🇧🇷 Português

1. Preparar políticas e equipe
2. Identificar a extensão do comprometimento
3. Conter o impacto imediato
4. Eliminar vestígios do ataque
5. Restaurar operações com segurança
6. Documentar casos para melhorias futuras

---

### 🧬 Malware Analysis (Análise de Malware)

#### 🇺🇸 English

- **Virus**: Infects legitimate files
- **Trojan**: Hides malicious functions
- **Ransomware**: Encrypts data for extortion

#### 🇧🇷 Português

- **Vírus**: Propaga-se infectando arquivos legítimos
- **Cavalo de Troia**: Engana usuários com aparência legítima
- **Ransomware**: Sequestra dados para resgate financeiro

---
