# Network Fundamentals

## Device Identification on a Network

Two main ways to identify a device on a network:
- **IP Address**
- **MAC Address (Media Access Control)**

---

## IP Address

### Structure

```
Octet 1   Octet 2   Octet 3   Octet 4
192.      168.      1.        1
0–255     0–255     0–255     0–255
```

- IP addresses are not unique globally and can change.
- Within a single network, no two devices can have the same IP address simultaneously.
- Devices can have public or private IP addresses depending on their location on the network.

### Example Devices

| Device Name       | IP Address     | IP Type |
|-------------------|----------------|---------|
| DESKTOP-KJE57FD   | 192.168.1.77   | Private |
| DESKTOP-KJE57FD   | 86.157.52.21   | Public  |
| CMNatic-PC        | 192.168.1.74   | Private |
| CMNatic-PC        | 86.157.52.21   | Public  |

**MAC Addresses**:
- DESKTOP-KJE57FD: `EC:5C:68:C3:7E:51`
- CMNatic-PC: `50:3E:AA:E8:3B:64`

### IPv4 vs IPv6

- **IPv4**: 2³² addresses (~4.29 billion)
- **IPv6**: 2¹²⁸ addresses (340 trillion+)

**Examples**:
- IPv4: `86.157.52.21`
- IPv6: `2a00:22c4:a531:c500:425f:cce6:c36b:f64d`

---

## MAC Address

- Each network interface card (NIC) has a **unique MAC address**.
- Format: `a4:c3:f0:85:ac:2d`
  - First 6 characters: Manufacturer
  - Last 6 characters: Unique ID

### MAC Spoofing

- MAC addresses can be **faked (spoofed)**.
- This can **bypass security** if access control is based only on MAC addresses.

---

## Ping and ICMP

- `ping` uses **ICMP packets** to test network connectivity.
- ICMP sends an **echo request** and expects an **echo reply** to measure latency.

---

## LAN Topologies

### Star Topology
- Devices connect via a **central switch/hub**.
- **Reliable and scalable**, but expensive.
- If the central device fails, all communication is lost.

### Bus Topology
- Devices share a **single backbone cable**.
- **Cheap**, but prone to **bottlenecks** and **single point of failure**.

### Ring Topology
- Devices are connected in a **loop**.
- **Fewer cables** than star topology.
- If one cable fails, the **entire network fails**.

---

## Subnetting

Splitting a network into **smaller subnetworks**.

### Components:

- **Network Address**: e.g., `192.168.1.0`
- **Host Address**: e.g., `192.168.1.1`
- **Default Gateway**: e.g., `.1` or `.254`, used for routing external traffic.

---

## ARP (Address Resolution Protocol)

- Maps **IP addresses to MAC addresses**.
- Devices maintain an **ARP cache**.

### ARP Workflow:
1. **ARP Request**: "Who has this IP?"
2. **ARP Reply**: "I do! Here's my MAC address."

---

## DHCP (Dynamic Host Configuration Protocol)

- Assigns **IP addresses automatically**.

### Process:
1. **DHCP Discover**: "Anyone give me an IP?"
2. **DHCP Offer**: "Here’s `192.168.1.10`."
3. **DHCP Request**: "I’ll take it!"
4. **DHCP Acknowledgment**: "Good for 24 hours."

---

## OSI Model

### 7 Layers:

1. **Physical**: Hardware transmission (e.g., Ethernet).
2. **Data Link**: MAC addressing and formatting data.
3. **Network**: Routing using IP addresses. Protocols: OSPF, RIP.
4. **Transport**: Ensures data delivery.
   - **TCP**: Reliable, slower.
   - **UDP**: Fast, no guarantee.
5. **Session**: Manages sessions and checkpoints.
6. **Presentation**: Data formatting and translation.
7. **Application**: User-level protocols and interfaces.

---

## Summary

- IP and MAC addresses are essential for network communication.
- LAN topologies affect network design, cost, and reliability.
- Protocols like ARP, DHCP, and ICMP help devices discover and communicate.
- The OSI model offers a standard for data exchange across networks.
