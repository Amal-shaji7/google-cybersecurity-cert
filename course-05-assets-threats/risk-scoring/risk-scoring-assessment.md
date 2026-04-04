# Risk Scoring Assessment
## Commercial Bank — Risk Register Analysis

| Field | Detail |
|-------|--------|
| **Analyst** | Amal Shaji |
| **Organisation** | Commercial Bank |
| **Asset Assessed** | Funds |
| **Objective** | Score identified risks by likelihood and severity to prioritise remediation efforts |

---

## Operational Environment

The bank is located in a coastal area with low crime 
rates. 100 on-premise and 20 remote employees handle 
the bank's data. The customer base includes 2,000 
individual accounts and 200 commercial accounts. 
The bank's services are marketed by a professional 
sports team and ten local businesses. Strict financial 
regulations require the bank to maintain data security 
and sufficient daily cash reserves to meet Federal 
Reserve requirements.

---

## Risk Priority Formula
```
Likelihood × Severity = Priority Score
```

**Likelihood Scale:**
- 1 — Rare
- 2 — Likely
- 3 — Certain

**Severity Scale:**
- 1 — Low impact
- 2 — Moderate impact
- 3 — Catastrophic impact

---

## Risk Register

| Asset | Risk | Description | Likelihood | Severity | Priority |
|-------|------|-------------|-----------|---------|---------|
| Funds | Business email compromise | An employee is tricked into sharing confidential information | 2 | 2 | 4 |
| Funds | Compromised user database | Customer data is poorly encrypted | 3 | 3 | 9 |
| Funds | Financial records leak | A database server of backed up data is publicly accessible | 2 | 3 | 6 |
| Funds | Theft | The bank's safe is left unlocked | 2 | 3 | 6 |
| Funds | Supply chain disruption | Delivery delays due to natural disasters | 1 | 2 | 2 |

---

## Risk Analysis

### Priority 9 — Compromised User Database
Highest priority risk in the register. Poorly 
encrypted customer data across 2,200 accounts 
represents a catastrophic and near-certain threat. 
The volume of accounts and the regulatory environment 
make this the most urgent remediation target. A 
breach of this nature would trigger mandatory 
reporting obligations, significant financial 
penalties, and severe reputational damage.

### Priority 6 — Financial Records Leak
A publicly accessible backup database server is 
a critical misconfiguration that directly exposes 
financial records. Severity is catastrophic — 
financial data exposure carries regulatory and 
legal consequences. Likelihood is moderate given 
that misconfigured servers are a common and 
well-documented vulnerability class.

### Priority 6 — Theft
Despite the low crime rate environment, an unlocked 
safe represents a straightforward physical security 
failure. Severity is catastrophic given direct access 
to funds. Likelihood is scored moderate rather than 
rare because the vulnerability — an unlocked safe — 
is an active misconfiguration rather than a 
speculative threat.

### Priority 4 — Business Email Compromise
With 120 employees across on-premise and remote 
locations, the human attack surface is significant. 
Social engineering attacks targeting employees 
handling financial transactions are a well-documented 
threat to banking institutions. Likelihood and 
severity are both moderate, the impact of a single 
compromised employee is serious but typically 
contained compared to a full database breach.

### Priority 2 — Supply Chain Disruption
Lowest priority risk. The coastal location introduces 
natural disaster exposure but the likelihood of a 
supply chain disruption causing direct financial harm 
to the bank's core operations is rare. Controls such 
as cash reserve requirements already partially 
mitigate this risk.

---

## Notes — Risk Factors in Context

The bank's large employee base and extensive customer 
accounts create significant exposure to human error 
and targeted attacks. Poorly encrypted databases and 
publicly accessible backup servers represent the 
highest priority risks regardless of the low-crime 
environment. The coastal location introduces natural 
disaster risk but this remains a lower priority 
compared to the severity of potential data breaches.

---

## Prioritised Remediation Summary

| Priority | Risk | Recommended Action |
|---------|------|-------------------|
| 🔴 9 | Compromised user database | Implement strong encryption immediately — AES-256 minimum |
| 🟠 6 | Financial records leak | Audit and restrict database server access — remove public accessibility |
| 🟠 6 | Theft | Enforce physical security procedures — safe locking policy and access log |
| 🟡 4 | Business email compromise | Deploy email security controls and mandatory phishing awareness training |
| 🟢 2 | Supply chain disruption | Maintain Federal Reserve cash reserve compliance — review supplier redundancy |

---

*Completed by Amal Shaji — Google Cybersecurity
Professional Certificate, Course 5: Assets,
Threats, and Vulnerabilities*
