# Incident Response Report
## ICMP Flood DoS Attack — NIST CSF v2.0 Analysis

| Field | Detail |
|-------|--------|
| **Analyst** | Amal Shaji |
| **Incident Type** | ICMP Flood — Denial of Service (DoS) |
| **Duration** | Approximately 2 hours |
| **Framework Applied** | NIST Cybersecurity Framework v2.0 |
| **Entry Point** | Unconfigured firewall |
| **Impact** | Full internal network disruption |

---

## Summary

The organisation experienced a Denial of Service attack in which 
all internal network services suddenly stopped responding. The 
cybersecurity team identified the cause as an ICMP flood — a 
malicious actor sent a continuous stream of ICMP ping packets 
into the company's network through an unconfigured firewall, 
overwhelming network capacity and preventing all normal internal 
traffic from accessing network resources.

The incident management team responded by blocking incoming ICMP 
packets, taking all non-critical network services offline, and 
prioritising the restoration of critical services. The network 
was fully restored within two hours.

> **Classification note:** This incident is a DoS attack — 
> originating from a single malicious actor exploiting an 
> unconfigured firewall. This is distinct from a DDoS attack 
> which involves multiple coordinated distributed sources.

---

## Govern

No formal firewall configuration policy was in place at the 
time of the incident. No defined ownership existed for perimeter 
device configuration or change management. This governance gap 
directly enabled the vulnerability — the firewall remained 
unconfigured with no controls on ICMP traffic.

**Actions required:**
- Establish a network security policy defining minimum 
configuration standards for all perimeter devices
- Assign formal ownership and accountability for firewall 
configuration and change management
- Implement a risk management process that flags 
misconfigured perimeter devices as high-priority risks
- Schedule regular governance reviews to ensure policies 
are actively enforced

---

## Identify

A malicious actor targeted the organisation with an ICMP flood 
DoS attack, exploiting an unconfigured firewall at the network 
perimeter. The attack affected the entire internal network — 
all network-dependent services became unavailable for the 
duration of the incident.

**Root vulnerability:** No rate limiting, source IP 
verification, or ICMP filtering rules were configured on 
the firewall, leaving the network perimeter fully exposed 
to volumetric attacks.

**Assets affected:**
- All internal network resources
- Critical and non-critical network services
- Employee ability to conduct normal business operations 
for approximately two hours

**Action required:** Conduct regular audits of internal 
networks, systems, devices, and access privileges to 
identify configuration gaps before they can be exploited.

---

## Protect

**Controls implemented following the incident:**

- New firewall rule configured to limit the rate of 
incoming ICMP packets — preventing any single source 
from flooding the network regardless of volume
- IDS/IPS system deployed to actively filter ICMP 
traffic exhibiting suspicious characteristics before 
it reaches the internal network

**Additional controls recommended:**

- Establish a firewall configuration review schedule — 
all rules audited regularly to ensure no 
misconfigurations persist
- Implement network segmentation to isolate critical 
systems from general traffic and limit blast radius 
of future attacks
- Deliver security awareness training covering 
identification and reporting of abnormal network 
behaviour

---

## Detect

**Controls implemented following the incident:**

- Source IP address verification configured on the 
firewall to identify and block spoofed addresses on 
incoming ICMP packets
- Network monitoring software deployed to observe 
traffic patterns continuously, establish normal 
baselines, and alert on deviations consistent with 
flood attacks or other anomalous activity

**Additional controls recommended:**

- Define and document traffic volume thresholds so 
automated alerts fire before services are impacted
- Implement centralised log aggregation — firewall 
events, IDS/IPS alerts, and traffic anomalies 
feeding into a SIEM for correlation and analysis
- Establish a regular log review process to identify 
low-and-slow attack patterns that automated alerts 
may not immediately catch

---

## Respond

**Immediate actions taken during this incident:**

- Blocked all incoming ICMP packets at the firewall 
to stop the flood at the network perimeter
- Took all non-critical network services offline to 
reduce internal load and preserve capacity for 
critical operations
- Restored critical network services to resume 
essential business functions
- Investigated and confirmed root cause — 
unconfigured firewall exploited by single-source 
ICMP flood

**Response process for future incidents:**

- Isolate affected systems immediately to prevent 
disruption spreading across the network
- Prioritise restoration of critical systems and 
services before non-critical ones
- Analyse network logs for suspicious and abnormal 
activity during and after containment
- Report all incidents to upper management with 
full timeline, impact assessment, and root cause 
summary
- Report to appropriate legal authorities where 
applicable — for example where customer data or 
regulatory obligations are involved
- Develop a formal incident response playbook for 
volumetric DoS attacks covering decision trees, 
communication templates, and escalation paths

---

## Recover

**Recovery actions taken following this incident:**

- Blocked external ICMP flood traffic at the 
firewall to neutralise the attack at the perimeter
- Took non-critical services offline to reduce 
internal traffic load
- Restored critical network services first and 
monitored for stability
- Brought non-critical systems back online 
incrementally once network stability was confirmed
- Updated firewall configuration with rate limiting 
and source verification rules before declaring 
full recovery complete

**Recovery sequence for future ICMP flood incidents:**

1. Block external ICMP flood traffic at the firewall
2. Take non-critical services offline to reduce load
3. Restore critical services first — prioritise by 
business impact
4. Monitor traffic continuously until patterns 
return to established baseline
5. Bring non-critical systems back online 
incrementally — validate each before proceeding
6. Conduct post-incident review within 72 hours — 
document full timeline, confirm root cause, update 
playbooks, assign remediation owners

**Longer-term resilience improvements:**

- Develop and test a business continuity plan 
covering network attack scenarios with defined 
recovery time objectives for all critical services
- Implement redundant network paths so a single 
point of attack cannot take all services down 
simultaneously
- Schedule regular incident response exercises 
to ensure the team executes recovery efficiently 
under pressure

---

## Notes

- This report applies NIST CSF v2.0 which includes 
six core functions. Govern was added in the 2024 
update and is applied here accordingly.

---

*Report completed by Amal Shaji — Google Cybersecurity 
Professional Certificate, Course 3: Connect and Protect: 
Networks and Network Security*
