# 📡 Wireshark Network Capture Report 

## 1. Installation
Wireshark was installed from the official [Wireshark website](https://www.wireshark.org) with default settings, including Npcap for packet capture.

---

## 2. Start Capture
The capture was started on the **Wi-Fi** network interface.

---

## 3. Generate Traffic
During the capture:
- A web browser was used to visit websites.
- Background applications (e.g., a browser auto-update service) generated traffic.
- Both IPv4 and IPv6 communications were observed.

---

## 4. Stop Capture
Capture was stopped after approximately **1 minute**.

---

## 5. Filter by Protocol
Filters applied:
- `tcp`
- `tls`
- `dns`

---

## 6. Protocols Identified
1. **TCP** – Reliable transport protocol for web and application traffic.  
2. **TLSv1.2 / TLSv1.3** – Encrypted communication for secure web browsing (HTTPS).  
3. **DNS** – Domain Name System lookups and responses.

---

## 7. Export as `.pcap`
The capture was saved as `network_capture.pcap` (internal use only).

---

## 8. Summary of Findings

### General Observations
- Traffic includes **both IPv4 and IPv6** connections.
- Multiple **external servers** were contacted (anonymized in this report).
- **DNS requests** were made to resolve an update domain.
- **Encrypted HTTPS traffic** (TLS) was observed.

---

### Example Packet Details (Anonymized)

| Packet No. | Protocol   | Source         | Destination   | Info |
|------------|------------|---------------|---------------|------|
| 140        | TCP        | Public_IP_A   | Private_IP_1  | Keep-Alive ACK, HTTP port 80 |
| 141        | TLSv1.2    | Public_IP_B   | Private_IP_1  | Application Data (encrypted) |
| 144        | TCP        | Private_IP_1  | Public_IP_B   | RST, ACK (connection reset) |
| 42         | TCP (IPv6) | Private_IP_1  | Public_IP_C   | ACK on port 80 (HTTP) |
| 74         | DNS (IPv6) | Private_IP_2  | Public_IP_D   | Query: `A autoupdate.example.com` |
| 76         | DNS (IPv6) | Public_IP_D   | Private_IP_2  | Response: `A autoupdate.example.com` |

---

### Notable Points
- **TCP retransmissions** and **duplicate ACKs** indicate minor packet loss or network delay.  
- **TLS** confirms secure encrypted communication.  
- **DNS** activity shows background services were active during capture.  

---

## ✅ Conclusion
The capture demonstrates:
- Standard DNS lookups
- TCP connections
- Encrypted HTTPS sessions

Retransmissions observed are common in real-world networks and are not necessarily problematic.

---

## 📂 Files
- `network_capture.pcap` – Full capture file (**internal use only**; not shared publicly).


