# tcpdump Network Traffic Analysis 2 — Brute Force Attack & Malware Redirect

## Overview

This folder documents a network traffic analysis conducted using 
**tcpdump** to investigate a security incident affecting 
`yummyrecipesforme.com`.

A former employee executed a brute force attack against the 
website's administrative account, gained access using a default 
password, embedded malicious JavaScript into the site's source 
code, and redirected visitors to a malware-laden fake website. 
This report identifies the protocols involved, documents the 
full attack chain, and recommends controls to prevent recurrence.

---

## Files In This Folder

| File | Description |
|------|-------------|
| `brute-force-malware-report.md` | Full incident report — attack documentation and recommendations |
| `tcpdump-log.docx` | RAW tcpdump capture log - traffic data|
| `tcpdump-lab-2.docx` | Original course submission document |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| tcpdump | Command line packet capture and network traffic analysis |
| Sandbox environment | Isolated environment to safely observe malicious website behaviour |

---

## Attack Type Identified

| Detail | Value |
|--------|-------|
| Initial Attack | Brute force — administrative account |
| Vulnerability Exploited | Default password with no brute force controls |
| Malware Delivery | Malicious JavaScript embedded in website source code |
| Protocol Affected | HTTP |
| Redirect Destination | greatrecipesforme.com |

---

## Protocols Identified

| Protocol | Role In This Incident |
|----------|----------------------|
| DNS | Resolved IP addresses for both yummyrecipesforme.com and greatrecipesforme.com |
| HTTP | Used to deliver the malicious file to users and redirect to the fake website |

---

## Skills Demonstrated

- Multi-stage attack chain analysis and documentation
- Protocol identification — DNS and HTTP
- Brute force attack investigation
- Malware delivery mechanism analysis
- Sandbox-based incident investigation
- Security remediation recommendation
- Professional cybersecurity incident report writing

---

*Completed by Amal Shaji — Google Cybersecurity Professional 
Certificate, Course 3: Connect and Protect: Networks and 
Network Security*
