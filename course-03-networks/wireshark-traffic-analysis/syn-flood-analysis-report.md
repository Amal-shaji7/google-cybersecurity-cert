# Incident Report
## Wireshark Network Traffic Analysis — SYN Flood DoS Attack

| Field | Detail |
|-------|--------|
| **Analyst** | Amal Shaji |
| **Date of Incident** | [Date] |
| **Time of Detection** | ~3.390 seconds into capture |
| **Affected System** | Web server — 192.0.2.1 |
| **Tool Used** | Wireshark |
| **Attack Source IP** | 203.0.113.0 |
| **Protocol Affected** | TCP — Port 443 (HTTPS) |

---

## Incident Summary

An automated monitoring alert indicated a problem with the 
company's web server. Attempts to visit the website returned 
a connection timeout error. A packet sniffer was deployed to 
capture traffic to and from the web server during the outage.

Analysis of the captured log revealed a sustained flood of TCP 
SYN packets originating from a single IP address — 203.0.113.0 
— targeting the web server at 192.0.2.1 on port 443. The volume 
of inbound SYN requests overwhelmed the server's available 
resources, preventing it from processing legitimate connection 
requests from real users.

The web server was taken offline temporarily to allow recovery. 
A firewall rule was applied to block traffic from 203.0.113.0 
as an immediate containment measure.

---

## Attack Identification

**Attack type:** SYN Flood — Denial of Service (DoS)

The packet capture log provides clear evidence of a SYN flood 
attack. Beginning at packet 52, a single source IP address 
(203.0.113.0) begins sending repeated TCP SYN packets to the 
web server on port 443. This continues without interruption 
through to the end of the capture at packet 214, spanning 
approximately 47 seconds of sustained flooding.

During this period the server's responses to legitimate users 
degrade visibly — moving from successful connections and HTTP 
200 responses in the early packets to RST/ACK resets and 
eventually a 504 Gateway Timeout by packet 77. Legitimate 
users attempting to connect were actively rejected as the 
server's resources became fully consumed.

---

## Understanding the Attack Mechanism

### Normal TCP Three-Way Handshake

Under normal operation, a TCP connection is established through 
a three-step process:

1. **SYN** — the client sends a SYN packet to the server 
requesting a connection. The server reserves resources in 
anticipation of completing the handshake
2. **SYN-ACK** — the server responds with a SYN-ACK packet 
accepting the connection request and confirming it is ready
3. **ACK** — the client sends a final ACK packet completing 
the handshake. The connection is now established and data 
transfer can begin

This handshake is visible in the early packets of the capture. 
Packets 47 through 51 show a legitimate connection from 
198.51.100.23 completing the full three-way handshake and 
successfully retrieving `/sales.html` with an HTTP 200 response.

### How a SYN Flood Disrupts This Process

In a SYN flood attack, a malicious actor sends a continuous 
stream of SYN packets without ever completing the handshake 
with the final ACK. Each SYN packet causes the server to 
reserve resources and wait for an ACK that never arrives. 
As the flood continues, the server's connection table fills 
entirely with these incomplete half-open connections.

Once all available resources are consumed, the server can no 
longer accept or process new legitimate connection requests — 
causing timeouts and connection failures for real users.

---

## Log Analysis

The Wireshark capture log reveals a clear and distinct attack 
pattern:

**Phase 1 — Normal traffic (Packets 47–54)**
Legitimate users at 198.51.100.23 and 198.51.100.14 connect 
successfully. Full TCP three-way handshakes complete normally. 
HTTP GET requests for `/sales.html` return HTTP 200 OK 
responses. The server is functioning normally.

**Phase 2 — Attack begins (Packets 52 onwards)**
IP address 203.0.113.0 initiates its first SYN request at 
packet 52. Unlike legitimate users, this source never completes 
the three-way handshake. SYN packets from 203.0.113.0 repeat 
at approximately every 0.3 seconds, increasing in frequency 
as the attack progresses.

**Phase 3 — Server degradation (Packets 63–83)**
The server begins responding to legitimate users with RST/ACK 
packets — actively resetting connections it can no longer 
support. Packet 77 shows the server returning an HTTP 504 
Gateway Timeout to a legitimate user at 198.51.100.5. The 
server is visibly losing capacity to service real requests.

**Phase 4 — Full saturation (Packets 84 onwards)**
From packet 84 onwards, the log is dominated almost entirely 
by SYN packets from 203.0.113.0. The server intermittently 
responds with RST/ACK resets before eventually ceasing to 
respond meaningfully at all. No successful legitimate 
connections are observed after this point.

By packet 90 onwards, 203.0.113.0 is sending SYN packets at 
approximately 3 per second continuously through to the end 
of the capture. The total volume of malicious SYN packets 
observed in this log exceeds 150 individual requests from 
a single source.

---

## Findings

The web server at 192.0.2.1 was subjected to a deliberate 
SYN flood Denial of Service attack from IP address 203.0.113.0. 
The attacker exploited the TCP three-way handshake mechanism 
by sending continuous SYN requests without completing 
connections, exhausting the server's ability to maintain its 
connection table and process legitimate traffic.

The attack directly caused the connection timeout errors 
experienced by employees attempting to access the sales 
website, and prevented customers from accessing the company's 
online services for the duration of the incident.

---

## Immediate Response Actions Taken

- Web server taken offline temporarily to allow resource 
recovery and return to normal operating status
- Firewall rule applied to block inbound traffic from 
203.0.113.0

**Limitation noted:** IP blocking is a short-term measure 
only. The attacker can bypass this control by spoofing 
alternative source IP addresses. A more robust and sustained 
response is required.

---

## Recommended Next Steps

1. **Implement SYN rate limiting** — configure the firewall 
to limit the number of SYN packets accepted from any single 
source IP per second, reducing the effectiveness of flood 
attacks regardless of the source address used
2. **Enable SYN cookies** — configure the web server to use 
SYN cookies, which avoids reserving resources until the 
three-way handshake is fully completed, making the server 
resistant to half-open connection exhaustion
3. **Deploy or tune IDS/IPS** — implement or update intrusion 
detection and prevention rules to automatically identify and 
block SYN flood patterns in real time without requiring 
manual intervention
4. **Consider upstream DDoS mitigation** — if the attacker 
escalates to spoofed or distributed sources, on-premise 
controls alone will be insufficient. Evaluate cloud-based 
DDoS mitigation services that can absorb or filter attack 
traffic before it reaches the server
5. **Review and expand monitoring** — the automated alert 
was the first indicator of this attack. Enhance monitoring 
to include TCP connection rate thresholds so that SYN flood 
patterns trigger alerts earlier — ideally before the server 
reaches saturation
6. **Document and retain evidence** — preserve the full 
Wireshark capture log for forensic purposes, potential 
legal action, and post-incident review

---

*Report completed by Amal Shaji — Google Cybersecurity 
Professional Certificate, Course 3: Connect and Protect: 
Networks and Network Security*
