# Access Control Investigation
## Authentication and Authorization Analysis — Payroll Incident

| Field | Detail |
|-------|--------|
| **Analyst** | Amal Shaji |
| **Organisation** | Small growing business |
| **Incident Type** | Unauthorised payroll transaction |
| **Objective** | Investigate the incident, identify access control failures, and recommend mitigations |

---

## Incident Summary

A deposit was made from the business to an unknown
bank account. The finance manager confirmed they did
not authorise the transaction. The payment was stopped
before completion. An investigation was initiated
to identify how the transaction occurred and prevent
recurrence.

The investigation involved reviewing the system event
log, cross-referencing findings against the employee
directory, identifying the likely threat actor, and
documenting the access control failures that enabled
the incident.

---

## Event Log Review

| Field | Detail |
|-------|--------|
| Event Type | Information |
| Event Source | AdsmEmployeeService |
| Event Category | None |
| Event ID | 1227 |
| Date | 10/03/2023 |
| Time | 8:29:57 AM |
| User | Legal\Administrator |
| Computer | Up2-NoGud |
| IP Address | 152.207.255.255 |
| Description | Payroll event added. FAUX_BANK |

---

## Employee Directory — Relevant Findings

| Name | Role | Status | Authorization | End Date | Last Access |
|------|------|--------|--------------|----------|-------------|
| Robert Taylor Jr | Legal attorney | Contractor | Admin | 12/27/2019 | 8:29:57 AM — 5 days ago |
| Joanne Phelps | Sales associate | Seasonal | Admin | 1/31/2020 | 1:24:57 PM — 2 years ago |
| Lei Chu | Marketing | Part-time | Admin | 1/31/2020 | 3:05:00 PM — 2 days ago |
| Amanda Pearson | Manufacturer | Contractor | Admin | No end date | 6:24:19 PM — 3 months ago |

All employees and contractors in the directory hold
Admin authorisation regardless of role, including
graphic designers, sales associates, and seasonal
workers.

---

## Investigation Notes

- The event took place on 10/03/2023 at 8:29:57 AM
— early morning access from an external public IP
outside normal working patterns
- The user account `Legal\Administrator` was cross-
referenced to Robert Taylor Jr, a contractor whose
contract ended on 12/27/2019
- IP address 152.207.255.255 is a public external
address — not an internal company IP — confirming
access originated from outside the organisation's
network
- The computer hostname `Up2-NoGud` does not
correspond to any recognisable company device which
confirms access from a personal or external machine
- The payroll event references `FAUX_BANK` — an
unrecognised external bank account with no
association to legitimate business operations
- Two additional accounts with expired contracts
remain active — Joanne Phelps and Lei Chu — both
with end dates in January 2020 but still accessible
in 2023

---

## Issues Identified

**1. Dormant contractor account retained administrator access**
Robert Taylor Jr's account remained fully active
four years after his contract ended on 12/27/2019.
His administrator authorisation gave him unrestricted
access to payroll systems with no legitimate business
justification. No account deprovisioning process
was in place to deactivate the account upon contract
completion.

**2. Systemic absence of role-based access control**
Every employee in the directory holds Admin
authorisation regardless of their role or
responsibility level. A graphic designer, sales
associates, a marketing employee, seasonal
contractors, and the company owner all hold
identical administrator access. This represents
a complete failure of the least privilege principle
across the entire organisation — not an isolated
incident.

**3. Multiple expired accounts remain active**
At least three accounts belonging to individuals
with defined end dates remain active — Robert Taylor
Jr (ended 12/27/2019), Joanne Phelps (ended
1/31/2020), and Lei Chu (ended 1/31/2020). Lei Chu's
account was accessed as recently as 2 days ago
despite the contract ending over three years prior.

**4. Contractor account with no defined end date**
Amanda Pearson is listed as a contractor with no
end date. Contractor accounts must always have a
defined expiry date to ensure timely deprovisioning.
An open-ended contractor account with Admin
authorisation is an uncontrolled persistent risk.

---

## Recommendations

**1. Implement automatic account expiry**
All accounts should be configured to deactivate
automatically upon the employment or contract end
date. Contractor accounts specifically must never
remain active beyond their defined end date.
Immediate deprovisioning is required for Robert
Taylor Jr, Joanne Phelps, and Lei Chu. Amanda
Pearson's account requires an end date to be
defined immediately.

**2. Enforce role-based access control**
Admin authorisation must be revoked from all
employees who do not require it for their specific
role. A graphic designer, sales associate, marketing
employee, and seasonal contractor have no business
justification for administrator level access. Access
should be scoped strictly to job function.


**3. Enable Multi-Factor Authentication**
MFA must be enforced on all accounts especially
administrator accounts and any account with access
to financial or payroll systems. An external public
IP address accessing a privileged account with no
MFA in place is an unacceptable control gap. MFA
would have added a barrier that significantly
reduced the likelihood of successful unauthorised
access even with valid credentials.

**4. Conduct an immediate access audit**
All active accounts must be reviewed against current
employment and contractor status. Any account
belonging to an individual who is no longer actively
engaged with the organisation must be deactivated
immediately. This audit should be repeated on a
defined schedule, quarterly at minimum.

**5. Establish a formal contractor access policy**
All contractor accounts must have a defined end
date, access scoped to their specific function,
and automatic deactivation upon contract completion.
Contractors must never hold administrator level
access unless explicitly justified, documented, and
time-limited. Privileged contractor actions should
be logged and reviewed.

---

## Summary

This incident was not an isolated access control
failure. It revealed systemic weaknesses across
the organisation's entire identity and access
management practice. Every employee holds
administrator access regardless of role, multiple
expired accounts remain active, and no automatic
deprovisioning process exists.

The immediate threat was Robert Taylor Jr's dormant
contractor account being used to initiate a
fraudulent payroll transaction four years after his
contract ended. The underlying cause was an
organisation that had never implemented role-based
access control, account lifecycle management, or
MFA at any level.

The five recommended controls directly address each
identified failure — shifting access management from
a manual, people-dependent process to a system-
enforced one that does not rely on individuals
remembering to revoke access or limit their own
permissions.

---

*Completed by Amal Shaji — Google Cybersecurity
Professional Certificate, Course 5: Assets,
Threats, and Vulnerabilities*
