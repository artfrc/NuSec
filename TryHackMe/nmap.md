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

---

## Scan NULL, FIN e Xmas

### NULL (-sN)
Request is sent with no flags set at all. As per the RFC, the target host should respond with a RST if the port is closed.

### FIN (-sF)
Send FIN flag and receive RST too if port is closed.


### Xmas(-sX)
Send flags FIN, PSH and URG

- Why are NULL, FIN and Xmas scans generally used?
  - Firewall Evasion.

_o see which IP addresses contain active hosts, and which do not._
To perform a ping sweep, we use the -sn switch in conjunction with IP ranges which can be specified with either a hypen (-) or CIDR notation. i.e. we could scan the 192.168.0.x network using:

```bash
nmap -sn 192.168.0.1-254
```
or
```bash
nmap -sn 192.168.0.0/24
```
_The -sn switch tells Nmap not to scan any ports -- forcing it to rely primarily on ICMP echo packets (or ARP requests on a local network, if run with sudo or directly as the root user) to identify targets. In addition to the ICMP echo requests, the -sn switch will also cause nmap to send a TCP SYN packet to port 443 of the target, as well as a TCP ACK (or TCP SYN if not run as root) packet to port 80 of the target._

```bash
nmap -p 80 --script http-put --script-args http-put.url='/dav/shell.php',http-put.file='./shell.php'
```
Used to upload files using the PUT method. This takes two arguments: the URL to upload the file to, and the file's location on disk

### Searching for Scripts
Nmap stores its scripts on Linux at /usr/share/nmap/scripts

---

_-pn_ Which tells Nmap to not bother pinging the host before scanning it
_-f_ Used to fragment the packets making it less likely that the packets will be detected by a firewall or IDS.
_--scan-delay_ Used to add a delay between packets sent.
_--badsum_ Used to generate in invalid checksum for packets.