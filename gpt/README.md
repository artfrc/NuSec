# 🛡️ Plano de Estudos em Cibersegurança para Iniciantes – 4 Semanas

Bem-vindo ao seu cronograma de introdução prática ao mundo da cibersegurança! Este plano foi pensado para iniciantes e cobre fundamentos de redes, varredura, enumeração e exploração com ferramentas reais.

---

## 📆 Cronograma Resumido

| Semana | Tópico Principal             | Ferramentas                           | Desafios                                        |
|--------|------------------------------|----------------------------------------|-------------------------------------------------|
| 1      | Fundamentos de Redes + Nmap  | `nmap`, `netdiscover`                 | Mapear serviços com Nmap em máquina-alvo       |
| 2      | Enumeração de Serviços       | `whatweb`, `gobuster`, `ftp`, `nmap`  | Identificar tecnologias e diretórios ocultos   |
| 3      | Introdução à Exploração      | `searchsploit`, `metasploit`          | Explorar vulnerabilidade com Metasploit        |
| 4      | Pós-Exploração e Privesc     | `linpeas`, comandos Linux              | Buscar escalada de privilégios                 |

---

## ✅ Semana 1 – Fundamentos de Redes e Nmap

### Objetivos:
- Entender protocolos, IPs e portas
- Realizar varreduras básicas e avançadas com Nmap

### Ferramentas:
- `nmap`
- `netdiscover`

### Desafio:
- Escanear e documentar serviços da máquina **Metasploitable2**

### Recursos:
- [TryHackMe - Nmap Room](https://tryhackme.com/room/nmap)

---

## ✅ Semana 2 – Enumeração de Serviços

### Objetivos:
- Obter detalhes sobre serviços como HTTP, FTP, SMB
- Localizar diretórios ocultos, banners, credenciais

### Ferramentas:
- `whatweb`, `gobuster`, `ftp`, `smbclient`
- `nmap` com scripts NSE

### Desafio:
- Coletar o máximo de informações sobre os serviços da Metasploitable2

### Recursos:
- [TryHackMe - Basic Pentesting](https://tryhackme.com/room/basicpentestingjt)

---

## ✅ Semana 3 – Introdução à Exploração

### Objetivos:
- Compreender exploits e CVEs
- Usar o Metasploit para explorar uma vulnerabilidade

### Ferramentas:
- `searchsploit`
- `metasploit-framework`

### Desafio:
- Usar o Metasploit para explorar uma falha e obter uma shell

### Recursos:
- [TryHackMe - Metasploit Intro](https://tryhackme.com/room/metasploitintro)

---

## ✅ Semana 4 – Pós-Exploração e Escalada de Privilégio

### Objetivos:
- Enumerar a máquina após o acesso
- Identificar formas de escalar privilégios

### Ferramentas:
- `linpeas.sh`
- Comandos Linux básicos (`whoami`, `sudo -l`, `cat`, `find`, etc.)

### Desafio:
- Encontrar arquivos sensíveis e escalar para `root`

### Recursos:
- [TryHackMe - Linux Privilege Escalation](https://tryhackme.com/room/linuxprivesc)

---

## 📝 Dica Extra: Documente seus aprendizados

Crie um relatório simples por máquina ou desafio:

```markdown
# Relatório: Metasploitable2

## IP: 192.168.0.10
## Serviços:
- FTP (vsftpd 2.3.4)
- HTTP (Apache 2.2.8)
- MySQL (versão X.X.X)

## Exploração:
- Usado exploit vsftpd_234_backdoor via Metasploit
- Obteve shell reversa com usuário `nobody`

## Pós-Exploração:
- Escalada de privilégio via cron job exposto
