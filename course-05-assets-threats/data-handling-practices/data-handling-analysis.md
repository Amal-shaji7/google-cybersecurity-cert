# Data Handling Practices Analysis
## Applying NIST SP 800-53 AC-6 — Least Privilege

| Field | Detail |
|-------|--------|
| **Analyst** | Amal Shaji |
| **Organisation** | Educational Technology Company |
| **Control Applied** | NIST SP 800-53 AC-6 — Least Privilege |
| **Objective** | Identify the factors that led to a data leak and recommend control enhancements to prevent recurrence |

---

## Incident Summary

A customer success representative was granted access
to an internal folder containing confidential
documents related to an unannounced product which
included customer analytics and marketing materials.
The manager who granted access forgot to revoke it
after the meeting.

During a sales call, the representative intended to
share a link to the promotional materials with a
business partner. Instead, they accidentally shared
a link to the entire internal folder. The business
partner subsequently posted the link on their
company's social media page, publicly exposing
confidential business plans.

---

## Control

**Least Privilege** — NIST SP 800-53 AC-6

Only the minimal access and authorisation required
to complete a task or function should be provided
to users. Processes, user accounts, and roles
should be enforced to prevent users from operating
at privilege levels beyond what their business
objectives demand.

---

## Issue(s) — What Factors Contributed to the Data Leak?

The data leak occurred due to two compounding
failures of the least privilege principle.

First, the manager granted broader folder access
than the role required and failed to revoke it
after the meeting concluded. Second, the sales
representative had access to confidential internal
documents which included product development plans and customer
analytics that were entirely irrelevant to their
sales function. This access should never have been
provisioned in the first place.

These combined failures allowed sensitive business
plans to be accidentally shared with an external
party and subsequently exposed publicly which was an
incident that correctly implemented least privilege
controls would have prevented entirely.

---

## Review — What Does NIST SP 800-53 AC-6 Address?

NIST SP 800-53 AC-6 defines least privilege as
providing users only the minimal access and
authorisation required to complete their specific
task or function. It requires that processes, user
accounts, and roles are enforced to prevent users
from operating at privilege levels beyond what
their business objectives demand.

AC-6 also provides control enhancements which can practical
measures organisations can implement to strengthen
least privilege including role-based access
restrictions, automatic access revocation after a
defined period, activity logging of provisioned
accounts, and regular privilege audits.

---

## Recommendation(s) — Control Enhancements

**1. Restrict access based on user role**
Sales representatives should only have access to
promotional materials relevant to their specific
function. Internal product development folders,
customer analytics, and confidential business plans
should be restricted to personnel with a documented
business need and needs to be enforced at the system level rather
than relying on individual judgement.

**2. Automatically revoke access after a defined period**
Shared access to sensitive resources should expire
automatically after a set timeframe. The manager's
failure to manually unshare the folder after the
meeting would have been entirely mitigated if the
system revoked access without requiring human
intervention.

**3. Regularly audit user privileges**
Scheduled privilege audits should be conducted to
ensure access levels remain appropriate to each
employee's current role and responsibilities.
Regular audits identify and close overly broad
permissions before they result in an incident which as a 
privilege creep is a well-documented path to data
exposure.

**4. Maintain activity logs of provisioned accounts**
Access activity logs should record who accessed
which resources and when. This supports faster
incident investigation, creates an audit trail for
compliance purposes, and acts as a deterrent
against careless data handling behaviour.

---

## Justification — Why These Controls Address the Issues

Role-based access restrictions would have prevented
the sales representative from ever having visibility
into the internal product folder thereby eliminating the
root cause of this incident before it could occur.

Automatic access revocation removes dependence on
individual employees remembering to unshare
resources, closing a gap that human error will
reliably exploit given enough time and enough
people.

Regular audits and activity logging create an
ongoing governance layer that identifies privilege
creep before it leads to a breach. Together these
controls shift data protection from a
people-dependent process to a system-enforced
one — significantly reducing the likelihood of
a similar incident occurring again.

---

*Completed by Amal Shaji — Google Cybersecurity
Professional Certificate, Course 5: Assets,
Threats, and Vulnerabilities*
