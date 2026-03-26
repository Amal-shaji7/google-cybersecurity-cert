# Course 3 — Connect and Protect: Networks and Network Security

## Overview

This folder contains all deliverables completed during **Course 3: 
Connect and Protect: Networks and Network Security** of the Google 
Cybersecurity Professional Certificate.

---

## Contents

| Folder/File | Description |
|-------------|-------------|
| `tcpdump-traffic-analysis-1/` | tcpdump lab 1 — network traffic capture and analysis |
| `tcpdump-traffic-analysis-2/` | tcpdump lab 2 — network traffic capture and analysis |
| `wireshark-traffic-analysis/` | Wireshark — packet capture and deep packet inspection |
| `incident-response-report/` | NIST CSF-based incident response report — ICMP flood DoS attack |
---

## Key Concepts Covered In This Course

- Network architecture and communication protocols
- The TCP/IP model and OSI model — layers and functions
- Common network protocols — TCP, UDP, ICMP, DNS, HTTP, HTTPS, SFTP
- Network security — firewalls, VPNs, security zones, subnetting
- Network attacks — DoS, DDoS, packet sniffing, IP spoofing, 
replay attacks, on-path attacks
- Packet analysis using tcpdump and Wireshark
- Reading and interpreting network traffic logs
- Incident response using the NIST Cybersecurity Framework

## Additional Topics Covered In This Course

### Security Hardening
- **Network hardening** — port filtering, network segmentation, 
encryption in transit
- **OS hardening** — patch management, password policies, 
baseline configuration, disabling unused services
- **Cloud hardening** — identity and access management (IAM), 
hypervisor security, baseline configuration standards

### Cloud Security
- Cloud-specific attack surfaces and how they differ from 
on-premises environments
- Identity and Access Management (IAM) — roles, permissions, 
least privilege in cloud environments
- Cloud configuration security — misconfiguration as a leading 
cause of cloud breaches
- Cryptography in the cloud — encryption at rest and in transit
- Cryptographic erasure — secure data deletion through key 
destruction
- Key management — principles of managing encryption keys 
securely in cloud environments

### Intrusion Detection and Prevention
- How IDS and IPS systems work and differ
- Signature-based vs anomaly-based detection
- Placement of IDS/IPS within network architecture


---

## Tools Used

| Tool | Purpose |
|------|---------|
| tcpdump | Command line packet capture and traffic analysis |
| Wireshark | GUI-based packet capture and deep packet inspection |

---

## Skills Demonstrated

- Packet capture and network traffic analysis
- Protocol identification across TCP, UDP, ICMP, and DNS layers
- DNS failure investigation through log analysis
- DoS attack identification and response
- Applying the NIST CSF — Identify, Protect, Detect, Respond, Recover
- Professional incident report writing
- Root cause analysis and remediation recommendation

---

## Labs and Reports

### tcpdump — DNS Port Unreachable
Investigated a reported service outage affecting 
`www.yummyrecipesforme.com`. Used tcpdump to capture network 
traffic and identified that DNS port 53 was unreachable, 
preventing domain name resolution. Analysed UDP and ICMP 
packets to determine root cause and recommend next steps.

📁 [View Analysis](./tcpdump-traffic-analysis-1/)

---
### tcpdump — 
  

📁 [View Analysis](./tcpdump-traffic-analysis-2/)

  
---

  
### Wireshark — Network Traffic Analysis
Captured and inspected network packets using Wireshark to 
analyse traffic patterns, identify protocols in use, and 
investigate network behaviour during a simulated scenario.

📁 [View Analysis](./wireshark-traffic-analysis/)

---

### Incident Response Report — ICMP Flood DoS Attack
Analysed a DoS attack caused by an ICMP flood through an 
unconfigured firewall. Applied the NIST Cybersecurity Framework 
across all five functions — Identify, Protect, Detect, Respond, 
and Recover — to produce a structured security improvement plan.

📁 [View Report](./incident-response-report/)

---

## Technical Environment

- **tcpdump** — run via command line on Linux
- **Wireshark** — GUI analysis on lab environment
- **Lab machine:** HP Pavilion — Windows 11 with VirtualBox
- **Kali Linux VM** — primary environment for command line tools

---

*Completed by Amal Shaji — Google Cybersecurity Professional 
Certificate, Course 3: Connect and Protect: Networks and 
Network Security*
