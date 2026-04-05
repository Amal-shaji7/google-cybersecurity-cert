# PASTA Threat Model Framework
## Sneaker Marketplace Mobile App

## Overview

This activity applied the PASTA (Process for Attack Simulation and Threat Analysis) framework 
to a mobile application being developed for a
sneaker buying and selling marketplace.

Working through all seven stages of PASTA, this
analysis moves from business objectives and
technical scope through data flow decomposition,
threat identification, vulnerability analysis,
attack tree modelling, and final security control
recommendations.

---

## Files In This Folder

| File | Description |
|------|-------------|
| `pasta-threat-model.md` | Full seven-stage PASTA analysis for the sneaker marketplace app |
| `data-flow-diagram.png` | Application data flow diagram — user to product search process to database |
| `attack-tree.png` | Attack tree diagram — user data threats via SQL injection and session hijacking |

---

## Framework Applied

| Framework | Description |
|-----------|-------------|
| PASTA | Process for Attack Simulation and Threat Analysis — a seven stage risk-centric threat modelling methodology |

---

## Technologies Evaluated

| Technology | Security Relevance |
|-----------|-------------------|
| API | Primary attack surface — handles all data exchange between users, sellers, and systems |
| PKI — AES and RSA | Encrypts sensitive data in transit and at rest |
| SHA-256 | Hashes passwords and sensitive user data |
| SQL | Database query layer — vulnerable to injection without prepared statements |

---

## Skills Demonstrated

- Structured threat modelling using PASTA
- Business and security objective analysis
- Technology stack security evaluation
- Data flow decomposition and process analysis
- Threat identification and vulnerability analysis
- Attack tree interpretation
- Security control recommendation aligned
to identified threats

---

*Completed by Amal Shaji — Google Cybersecurity
Professional Certificate, Course 5: Assets,
Threats, and Vulnerabilities*
