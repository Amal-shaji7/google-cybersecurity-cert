# Google Cybersecurity Professional Certificate
### Amal Shaji | MSc Cybersecurity & Penetration Testing | BSc Forensics

---

## About This Repository

This repository documents my work and deliverables completed throughout the **Google Cybersecurity Professional Certificate** (9-course series via Coursera).

Each folder corresponds to a course in the programme. Where applicable, completed assessments, audits, reports, and professional artefacts are included — not as raw course submissions, but as polished professional documents reflecting how I approach real-world security work.

> **Note:** This is a living repository. It will be updated continuously as I progress through all 9 courses.

---

## Certificate Overview

| # | Course | Status |
|---|--------|--------|
| 1 | Foundations of Cybersecurity | ✅ Complete |
| 2 | Play It Safe: Manage Security Risks | ✅ Complete |
| 3 | Connect and Protect: Networks and Network Security | ✅ Complete |
| 4 | Tools of the Trade: Linux and SQL | ✅ Complete |
| 5 | Assets, Threats, and Vulnerabilities | ✅ Complete |
| 6 | Sound the Alarm: Detection and Response | ✅ Complete |
| 7 | Automate Cybersecurity Tasks with Python | ✅ Complete |
| 8 | Put It to Work: Prepare for Cybersecurity Jobs | ✅ Complete |
| 9 | Capstone: Prepare for Cybersecurity Jobs | ✅ Complete |

---

## Repository Structure
```
google-cybersecurity-cert/
│
├── course-01-foundations/
│   ├── README.md
│   └── professional-statement.docx
│
├── course-02-managing-security-risks/
│   ├── README.md
│   └── botium-toys-security-audit/
│       ├── README.md
│       ├── audit-scope-and-goals.docx
│       ├── controls-compliance-checklist.docx
│       └── security-audit-report.md
│
├── course-03-networks/
│   ├── README.md
│   ├── incident-response-report/
│   │   ├── README.md
│   │   ├── icmp-dos-nist-csf-report.md
│   │   └── nist-csf-report.docx
│   ├── tcpdump-traffic-analysis-1/
│   │   ├── README.md
│   │   ├── dns-unreachable-report.md
│   │   ├── tcpdump-lab.docx
│   │   └── tcpdump-log.png
│   ├── tcpdump-traffic-analysis-2/
│   │   ├── README.md
│   │   ├── brute-force-malware-report.md
│   │   ├── tcpdump-lab-2.docx
│   │   └── tcpdump-log.docx
│   └── wireshark-traffic-analysis/
│       ├── README.md
│       ├── syn-flood-analysis-report.md
│       ├── wireshark-capture.xlsx
│       └── wireshark-lab.docx
│
├── course-04-linux-sql/
│   ├── README.md
│   ├── linux-labs/
│   │   ├── README.md
│   │   ├── file-management-lab.md
│   │   └── (linux-screenshots 1-5).png
│   └── sql-labs/
│       ├── README.md
│       ├── sql-filters-lab.md
│       └── (sql-screenshots 1-6).png
│
├── course-05-assets-threats/
│   ├── aaa-improvement/
│   ├── asset-classification/
│   ├── data-handling-practices/
│   ├── pasta-threat-model/
│   ├── risk-scoring/
│   ├── usb-attack-vectors/
│   ├── vulnerable-system-analysis/
│   └── README.md
│
├── course-06-detection-response/
│   ├── incident-handlers-journal.docx
│   ├── incident-handlers-journal.md
│   └── README.md
│
├── course-07-python-automation/
│   ├── python-file-update.md
│   ├── (screenshot 1-8).png
│   └── README.md
│
│
├── course-08-job-preparation/
│   └── README.md
│
└── course-09-capstone/                
```
---

## Course 1 — Foundations of Cybersecurity

### Professional Statement
A structured professional statement developed as part of Course 1, outlining my strengths, values, and goals within the cybersecurity field. Written following Google's professional statement framework.

📄 [View Professional Statement](./course-01-foundations/professional-statement.docx)

---

## Course 2 — Play It Safe: Manage Security Risks

### Security Audit — Botium Toys
An internal security audit conducted on the fictional organisation **Botium Toys** as part of Course 2 coursework. The audit follows a real-world methodology covering:

- Scope and goals definition
- Risk assessment
- Controls and compliance checklist evaluation — NIST CSF, PCI DSS, GDPR, SOC
- Findings and remediation recommendations

📁 [View Full Audit](./course-02-managing-security-risks/botium-toys-security-audit/security-audit-report.md)

---

## Course 3 — Connect and Protect: Networks and Network Security

### tcpdump Analysis 1 — DNS Port Unreachable
Network traffic analysis investigating a service
outage affecting `yummyrecipesforme.com`. Used
tcpdump to identify that DNS port 53 was
unreachable — preventing domain resolution and
causing the reported connection errors.

📁 [View Analysis](./course-03-networks/tcpdump-traffic-analysis-1/)

### tcpdump Analysis 2 — Brute Force and Malware Redirect
Investigated a multi-stage attack involving a
brute force compromise of an admin account,
malicious JavaScript injection into website
source code, and HTTP-based malware delivery
redirecting users to a fake website. Identified
DNS and HTTP as the protocols involved.

📁 [View Analysis](./course-03-networks/tcpdump-traffic-analysis-2/)

### Wireshark Analysis — SYN Flood DoS Attack
Packet capture analysis of a SYN flood Denial
of Service attack against a web server. Identified
the attack pattern across 150+ SYN packets from
a single source IP, documented server degradation
across packet frames, and recommended controls
including SYN rate limiting, SYN cookies, and
IDS/IPS deployment.

📁 [View Analysis](./course-03-networks/wireshark-traffic-analysis/)

### Incident Response Report — ICMP Flood DoS Attack
Applied the NIST Cybersecurity Framework v2.0
across all six core functions — including Govern,
which was added in the 2024 update — to analyse
an ICMP flood DoS attack and develop a structured
security improvement plan.

📁 [View Report](./course-03-networks/incident-response-report/)

---

## Course 4 — Tools of the Trade: Linux and SQL

### Linux — File Permissions Management
Examined and updated file system permissions for
a research team using `chmod` and `ls -la`.
Applied the principle of least privilege to ensure
users held only the access their role required —
covering read, write, and execute permissions
across visible and hidden files and directories.

📁 [View Lab](./course-04-linux-sql/linux-labs/)

### SQL — Security Investigation Using Filters
Used SQL filters — AND, OR, NOT, LIKE — to query
`log_in_attempts` and `employees` tables as part
of a security investigation into suspicious login
activity and employee machine update requirements.
Six targeted queries written and documented with
full analysis.

📁 [View Lab](./course-04-linux-sql/sql-labs/)

---

## Course 5 — Assets, Threats, and Vulnerabilities

### Asset Classification — Home Network Inventory
Identified and classified devices connected to
a home-based business network. Applied data
sensitivity classifications — Restricted,
Confidential, Internal-only, Public — to
determine which assets require the most
protection.

📁 [View Activity](./course-05-assets-threats/asset-classification/)

### Risk Scoring Assessment — Commercial Bank
Evaluated five identified risks to a commercial
bank's funds using a structured risk register.
Scored each risk by likelihood and severity to
produce a priority score guiding remediation
planning.

📁 [View Activity](./course-05-assets-threats/risk-scoring/)

### Data Handling Practices — NIST SP 800-53 AC-6
Applied NIST SP 800-53 AC-6 least privilege
controls to a data leak incident at an
educational technology company. Identified
control failures, reviewed the framework,
and recommended four specific enhancements
to prevent recurrence.

📁 [View Activity](./course-05-assets-threats/data-handling-practices/)

### Access Control Investigation — AAA Analysis
Investigated an unauthorised payroll transaction
by reviewing event logs and cross-referencing the
employee directory. Identified a former contractor's
administrator account active four years after
contract end — and a systemic absence of role-based
access control across the entire organisation.

📁 [View Activity](./course-05-assets-threats/aaa-improvement/)

### USB Drive Attack Vector Analysis
Safely investigated a USB drive found in a
hospital car park using a virtualised environment.
Analysed the contents for PII risk, documented
attacker mindset, and recommended technical,
operational, and managerial controls to mitigate
USB baiting attacks.

📁 [View Activity](./course-05-assets-threats/usb-attack-vectors/)

### PASTA Threat Model — Sneaker Marketplace App
Applied the full seven-stage PASTA framework to
a mobile application for buying and selling
sneakers. Identified SQL injection and session
hijacking as primary attack paths and recommended
layered controls across authentication,
encryption, and access management.

📁 [View Activity](./course-05-assets-threats/pasta-threat-model/)

### Vulnerable System Analysis — Portfolio Activity
Conducted a vulnerability assessment for an
e-commerce company with a publicly accessible
database server. Identified three threat sources,
scored risks using NIST SP 800-30 Rev. 1, and
proposed a structured remediation strategy.

📁 [View Activity](./course-05-assets-threats/vulnerable-system-analysis/)

---

## Course 6 — Sound the Alarm: Detection and Response

### Incident Handler's Journal
A four-entry structured incident journal
documenting security investigations completed
throughout the course — covering a healthcare
ransomware attack, phishing email and malware
analysis, file hash investigation using
VirusTotal linking to the BlackTech threat actor,
and SIEM and IDS monitoring using Splunk,
Chronicle, and Suricata.

📁 [View Journal](./course-06-detection-response/incident-handlers-journal.md)

---

## Course 7 — Automate Cybersecurity Tasks with Python

### IP Allow List Update Algorithm
Developed a Python algorithm to automate IP
address allow list management at a healthcare
organisation. The algorithm reads the current
allow list, cross-references it against a remove
list, removes unauthorised IP addresses, and
writes the updated list back to the file.
Demonstrates file handling, string and list
manipulation, iterative logic, and conditional
evaluation applied to a real access control task.

📁 [View Project](./course-07-python-automation/python-file-update/)

---

## Course 8 — Put It to Work: Prepare for Cybersecurity Jobs

Covered professional competencies for security
roles — incident communication, escalation
procedures, stakeholder reporting, community
engagement, and AI-assisted security workflows.
No technical portfolio activity — professional
skills are demonstrated through deliverables
across Courses 2 through 7.

📁 [View Course Notes](./course-08-job-preparation/)


## Technical Environment

Labs and practical work in this portfolio are completed using:

- **Primary lab machine:** HP Pavilion — Windows 11 running VirtualBox
- **VMs:** Kali Linux, Metasploitable 2, DVWA, Ubuntu Server
- **Secondary machine:** M1 MacBook Air — browser-based labs and documentation
- **Privacy/OPSEC awareness:** Tails OS

---

## Certifications In Progress

| Certification | Status |
|--------------|--------|
| Google Cybersecurity Professional Certificate | ✅ Complete |
| CompTIA Security+ SY0-701 | 🔄 Studying |
| eJPT | 📅 Planned |
| CEH | 📅 Planned |

---

*Repository maintained by Amal Shaji — coursework is completed.*
