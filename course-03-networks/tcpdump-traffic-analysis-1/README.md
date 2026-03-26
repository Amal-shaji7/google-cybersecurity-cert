# tcpdump Network Traffic Analysis 1 — DNS Port Unreachable

## Overview

This folder documents a network traffic analysis conducted using 
**tcpdump** to investigate a reported service outage affecting 
`www.yummyrecipesforme.com`.

Multiple customers reported receiving a "destination port 
unreachable" error when attempting to access the website. This 
analysis captures and interprets the network traffic at packet 
level to identify the affected protocol and determine the most 
probable root cause.

---

## Files In This Folder

| File | Description |
|------|-------------|
| `dns-unreachable-report.md` | Full incident report — tcpdump log analysis and findings |
| `tcpdump-log.png` | Screenshot of raw tcpdump output captured during investigation |
| `tcpdump-lab.docx` | Original course submission document |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| tcpdump | Command line packet capture and network traffic analysis |

---

## Protocols Analysed

| Protocol | Role In This Incident |
|----------|----------------------|
| UDP | Used by browser to send DNS queries to DNS server on port 53 |
| DNS | The affected protocol — domain name resolution failed |
| ICMP | Returned error responses indicating port 53 unreachable |

---

## Skills Demonstrated

- Command line packet capture using tcpdump
- Reading and interpreting raw tcpdump log output
- Protocol identification across UDP, ICMP, and DNS layers
- DNS failure investigation through log analysis
- Root cause hypothesis development
- Professional cybersecurity incident report writing

---

*Completed by Amal Shaji — Google Cybersecurity Professional 
Certificate, Course 3: Connect and Protect: Networks and 
Network Security*
