# Wireshark Network Traffic Analysis — SYN Flood DoS Attack

## Overview

This folder documents a network traffic analysis conducted using 
**Wireshark** to investigate a web server outage affecting a travel 
agency's sales website.

An automated monitoring alert indicated a problem with the web server. 
Packet capture analysis revealed a large volume of TCP SYN requests 
originating from a single suspicious IP address, consistent with a 
SYN flood Denial of Service attack. This report identifies the attack 
type, explains the mechanism, and analyses the captured log data as 
evidence.

---

## Files In This Folder

| File | Description |
|------|-------------|
| `syn-flood-analysis-report.md` | Full incident report — Wireshark traffic analysis and findings |
| `wireshark-capture.xlsx` | Raw Wireshark packet capture log — full traffic data |
| `wireshark-lab.docx` | Original course submission document |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Wireshark | GUI-based packet capture and deep packet inspection |

---

## Attack Type Identified

| Detail | Value |
|--------|-------|
| Attack Type | SYN Flood — Denial of Service |
| Attacker IP | 203.0.113.0 |
| Target IP | 192.0.2.1 |
| Target Port | 443 (HTTPS) |
| Protocol Affected | TCP |

---

## Skills Demonstrated

- Packet capture analysis using Wireshark
- TCP three-way handshake understanding
- SYN flood attack identification through log pattern recognition
- DoS attack classification and documentation
- Professional cybersecurity incident report writing
- Firewall response and remediation recommendation

---

*Completed by Amal Shaji — Google Cybersecurity Professional 
Certificate, Course 3: Connect and Protect: Networks and 
Network Security*
