# Incident Handler's Journal

| Field | Detail |
|-------|--------|
| **Analyst** | Amal Shaji |
| **Course** | Google Cybersecurity Professional Certificate — Course 6 |
| **Framework** | NIST Incident Response Lifecycle |

---

## About This Journal

This journal documents security incidents
investigated throughout Course 6. Each entry
follows a structured format recording the
incident description, tools used, the 5 W's
analysis, and additional analytical notes.
Entries span multiple incident types and tools
— reflecting the breadth of detection and
response work covered in this course.

---

## Entry 1

| Field | Detail |
|-------|--------|
| **Date** | July 23, 2024 |
| **Entry** | #1 |

### Description

Documenting a ransomware incident at a healthcare
clinic. The incident occurred in two phases:

**Phase 1 — Detection and Analysis**
Systems became inaccessible due to encrypted
files following a phishing attack. Analysis
aligned with the NIST Incident Response
Lifecycle, focusing on identifying the attack
vector and scope of compromise.

**Phase 2 — Containment, Eradication, and Recovery**
The clinic shut down systems and sought external
technical assistance for eradication and
recovery.

---

### Tools Used
- Wireshark
- tcpdump

---

### The 5 W's

| | |
|-|--|
| **Who** | Organised cybercriminal group targeting healthcare and transportation industries |
| **What** | Ransomware infection encrypting critical patient data and medical records |
| **Where** | Internal network of the healthcare clinic |
| **When** | Tuesday morning at approximately 9:00 AM |
| **Why** | Attackers gained access via targeted phishing emails containing malicious attachments. Once access was established, ransomware was deployed to encrypt critical files. Financial motivation confirmed by ransom note demanding payment for decryption key |

---

### Additional Notes

Network traffic analysis revealed suspicious
outbound connections post-infection which indicates
possible Command and Control (C2) communication
between compromised systems and attacker
infrastructure. This pattern is consistent with
ransomware operators maintaining persistence and
exfiltrating data prior to full encryption.

---

## Entry 2

| Field | Detail |
|-------|--------|
| **Date** | July 25, 2024 |
| **Entry** | #2 |

### Description

Analysis of a phishing email and malicious
attachment that led to the initial compromise.
This entry covers the detection and escalation
decisions made within the incident response
lifecycle following identification of the
malicious file.

---

### Tools Used
- Email analysis
- Threat intelligence lookup

---

### The 5 W's

| | |
|-|--|
| **Who** | Threat actor using a spoofed identity — impersonating "Def Communications" to appear legitimate |
| **What** | Phishing email delivering malware — `bfsvc.exe` — disguised as a legitimate attachment |
| **Where** | Employee email system |
| **When** | July 20, 2022 at 09:30 AM |
| **Why** | Social engineering attack exploiting user trust and the absence of email sender verification controls |

---

### Additional Notes

File hash analysis confirmed the attachment
`bfsvc.exe` as malicious and linked to known
malware — **Flagpro**. The hash was flagged
by threat intelligence sources. The incident
ticket was correctly escalated to Tier 2 SOC
for deeper investigation and containment.

---

## Entry 3

| Field | Detail |
|-------|--------|
| **Date** | July 25, 2024 |
| **Entry** | #3 |

### Description

Investigation of a suspicious file hash to
determine whether it represented a legitimate
threat. The file `bfsvc.exe` was identified by
its SHA-256 hash:

```
54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b
```

This entry aligns with the Detection and
Analysis phase — focusing on alert validation
and threat actor attribution using threat
intelligence sources.

---

### Tools Used
- VirusTotal — threat intelligence platform
- Hash analysis tools

---

### The 5 W's

| | |
|-|--|
| **Who** | Advanced threat actor associated with **BlackTech** — a known nation-state affiliated threat group |
| **What** | Malicious file identified by SHA-256 hash — linked to **Flagpro** malware |
| **Where** | Endpoint within the organisational network |
| **When** | Alert triggered at 1:20 PM after IDS detected the file and notified the SOC |
| **Why** | Malware delivered via phishing email and executed by user — consistent with BlackTech's known tactics of using spear phishing for initial access |

---

### Additional Notes

The file hash was flagged as malicious by over
50 vendors on VirusTotal. Attribution to
BlackTech (a known advanced threat actor)
increases the severity of this incident
significantly. This confirms the attack is
part of a broader targeted campaign rather
than an opportunistic infection, and warrants
escalated response procedures and potential
regulatory notification.

---

## Entry 4

| Field | Detail |
|-------|--------|
| **Date** | July 27, 2024 |
| **Entry** | #4 |

### Description

Use of SIEM and IDS tools to monitor, detect,
and analyse suspicious activity across the
network. This entry supports the Detection and
Analysis phase by demonstrating how log
aggregation and rule-based detection improve
visibility into potential threats.

---

### Tools Used
- Splunk — SIEM
- Chronicle — Cloud-native SIEM
- Suricata — Network IDS/IPS

---

### The 5 W's

| | |
|-|--|
| **Who** | Potential external attackers generating malicious network traffic |
| **What** | Suspicious network activity identified through log analysis and IDS alerts |
| **Where** | Network environment monitored through SIEM and IDS tools |
| **When** | During ongoing monitoring of network traffic and log aggregation |
| **Why** | Detection of anomalous traffic patterns and known malicious signatures triggered alerts requiring investigation |

---

### Additional Notes

Splunk and Chronicle were used for log querying
and correlation — identifying patterns across
multiple log sources that would not be visible
in isolation. Suricata identified specific
alerts including **"GET on WIRE"** with a
severity level of 3, indicating confirmed
suspicious traffic matching known attack
signatures.

These tools collectively demonstrate the
importance of centralised monitoring and
detection infrastructure. Without SIEM
aggregation and IDS rule-based alerting,
the suspicious activity in entries 1 through
3 would have had a significantly longer dwell
time before detection.

---

## Journal Summary

| Entry | Incident Type | Tools | Phase |
|-------|--------------|-------|-------|
| 1 | Ransomware — healthcare clinic | Wireshark, tcpdump | Detection and Analysis / Containment and Recovery |
| 2 | Phishing email — malware delivery | Email analysis, threat intel | Detection and Analysis |
| 3 | Malicious file hash — Flagpro/BlackTech | VirusTotal, hash tools | Detection and Analysis |
| 4 | Suspicious network activity | Splunk, Chronicle, Suricata | Detection and Analysis |

---

*Completed by Amal Shaji — Google Cybersecurity
Professional Certificate, Course 6: Sound the
Alarm: Detection and Response*
