# Security Audit — Botium Toys

## Scenario Overview

**Botium Toys** is a fictional small US-based toy company with a growing 
online presence. The IT department is under increasing pressure to support 
the business internationally while ensuring compliance with regulations 
around online payments and EU operations.

The IT manager requested an internal security audit to assess the current 
security posture, identify risks, and ensure compliance with relevant 
regulations.

This audit was completed as part of Course 2 of the Google Cybersecurity 
Professional Certificate.

---

## Audit Methodology

This audit follows a structured approach aligned with the 
**NIST Cybersecurity Framework (CSF)**:

1. **Define scope and goals** — establish what is being audited and why
2. **Conduct risk assessment** — identify current risks to assets, 
operations, and compliance
3. **Evaluate controls** — assess which controls are in place and 
which are missing
4. **Check compliance** — evaluate against PCI DSS, GDPR, and SOC 
Type 1 and 2
5. **Document findings** — summarise gaps and provide actionable 
recommendations

---

## Files In This Folder

| File | Description |
|------|-------------|
| `audit-scope-and-goals.md` | Defined audit scope, goals, and current assets |
| `controls-compliance-checklist.md` | Full controls and compliance checklist with pass/fail evaluation and explanations |
| `audit-findings-recommendations.md` | Summary of findings and prioritised remediation recommendations |

---

## Frameworks Referenced

- **NIST Cybersecurity Framework (CSF)**
- **PCI DSS** — Payment Card Industry Data Security Standard
- **GDPR** — General Data Protection Regulation
- **SOC Type 1 and Type 2** — System and Organisation Controls

---

## Key Findings Summary

- Multiple critical controls not in place including encryption, 
IDS, backups, and least privilege
- Significant compliance gaps across PCI DSS and partial gaps 
in GDPR and SOC
- Two GDPR positives confirmed — 72-hour breach notification 
plan in place and privacy policies actively enforced
- Immediate remediation recommended for encryption, role-based 
access control, and disaster recovery
- Additional recommendations raised for IDS deployment, password 
management, legacy system monitoring, and data classification

---

*Completed by Amal Shaji — Google Cybersecurity Professional 
Certificate, Course 2: Play It Safe: Manage Security Risks*
