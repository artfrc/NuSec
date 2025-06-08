# 📡 Network Connections and Ports

Network connections are established between two ports:
- An open port listening on the server. 🖥️
- A randomly selected port on your computer (e.g., port 49534 connecting to a server's port 443 for a web page). 💻

![Network Connection Diagram](/TryHackMe/images/image-4.png)

---

## 🌐 Common Ports and Services

| Service               | Port | Description                     |
|-----------------------|------|---------------------------------|
| **HTTP Web Service**  | 80   | Unsecured web traffic 🌍        |
| **HTTPS Web Service** | 443  | Secure web traffic (SSL/TLS) 🔒 |
| **Windows NetBIOS**   | 139  | Network file and printer sharing 📁 |
| **SMB**               | 445  | Server Message Block protocol 🤝 |

---

## 🔍 Importance of Port Scanning

Port scanning is a critical initial step in any network attack, typically performed using the **Nmap** tool. 🛠️

---

## 🛡️ Types of Port Scans

1. **TCP Connect Scan** (`-sT`) 🔗
2. **SYN (Half-open) Scan** (`-sS`) 🕵️‍♂️
3. **UDP Scan** (`-sU`) 📡

---

## 🤝 TCP Connect Scans

### TCP Three-Way Handshake
- **SYN**: Initiates the connection. 🚀
- **SYN/ACK**: Server acknowledges. ✅
- **ACK**: Completes the connection. ✔️
  - **RST**: Terminates the connection. 🚫

Firewalls often drop incoming packets silently, causing Nmap to mark the port as **filtered** when no response is received after a TCP SYN request. 🚨 However, firewalls can be configured to respond with a **RST** packet. For example, in Linux using iptables:

```bash
iptables -I INPUT -p tcp --dport <port> -j REJECT --reject-with tcp-reset
```

---

## 🕵️‍♂️ SYN Scans

SYN scans, also known as **Half-open** or **Stealth** scans, target a TCP port range without completing the full handshake, making them less detectable. 🕶️

![SYN Scan Diagram](/TryHackMe/images/image-3.png)

---

## 📡 UDP Scans

- **Nature**: Stateless, no handshake involved. 🌐
- **Flag**: `-sU`
- **Performance**: Slower due to lack of response from closed ports. 🐢
- **Example Command**: Scan the top 20 UDP ports.

```bash
nmap -sU --top-ports 20 <target>
```