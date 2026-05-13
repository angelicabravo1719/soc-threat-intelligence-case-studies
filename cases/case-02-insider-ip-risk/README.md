# Case 02 – Insider IP Risk Investigation

## Executive Summary

Unusual authentication activity was identified involving an internal user account accessing enterprise resources from an unfamiliar external IP address. Initial review indicated that the login behavior deviated from the user’s normal geographic and behavioral patterns, raising concerns regarding possible unauthorized access, credential misuse, or insider-related activity.

The investigation focused on validating the legitimacy of the IP address, reviewing authentication context, identifying anomalous access behavior, and assessing potential organizational risk exposure. OSINT enrichment and infrastructure analysis were performed to support the investigation and determine whether escalation or containment actions were necessary.

Based on the available evidence, the activity was assessed as suspicious pending additional authentication validation and user verification. Several indicators suggested elevated risk, including unusual login timing, geographic inconsistency, and infrastructure reputation concerns.

---

## Investigation Overview

| Investigation Detail | Information |
|---|---|
| Case ID | CASE-002 |
| Investigation Type | Insider Risk / Suspicious Authentication Activity |
| Detection Source | Authentication monitoring alert |
| Initial Severity | Medium |
| Analyst Objective | Validate legitimacy of external login activity |
| Investigation Status | Monitoring / Under Review |

---

## Alert Details

An authentication monitoring alert identified a successful login attempt associated with a privileged internal user account originating from an unfamiliar external IP address. The event occurred outside the user’s typical behavioral baseline and involved access to internal enterprise resources.

Initial triage identified several unusual characteristics including:
- Geographic login inconsistency
- Access outside normal business hours
- Login from unfamiliar infrastructure
- Elevated account privilege exposure
- Potential credential misuse indicators

The associated IP address and authentication context were isolated for further investigation and OSINT validation.

---

## Evidence Collected

### Evidence Sources
- Authentication logs
- IP reputation analysis
- Geolocation review
- WHOIS and ASN lookup
- Historical user access pattern comparison
- OSINT infrastructure review

### Key Findings
- IP address originated from an unfamiliar geographic region
- Login activity occurred outside the user’s typical access window
- Infrastructure reputation required further validation
- No immediate evidence of successful lateral movement identified
- Additional user verification recommended

---

## OSINT Findings

| Source | Finding |
|---|---|
| AbuseIPDB | Infrastructure reputation review performed |
| WHOIS Lookup | IP ownership and ASN information identified |
| Geolocation Review | Login activity originated from unusual geographic region |
| Historical Authentication Review | Behavior deviated from prior login patterns |
| Threat Intelligence Review | No confirmed attribution identified during initial analysis |

The collected findings supported continued monitoring and additional authentication validation procedures.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---|---|---|
| Initial Access | Valid Accounts | T1078 |
| Persistence | External Remote Services | T1133 |
| Defense Evasion | Use of Legitimate Credentials | T1078 |
| Discovery | Account Discovery | T1087 |

---

## Indicators of Compromise (IOCs)

| IOC Type | Value | Context |
|---|---|---|
| IP Address | xxx.xxx.xxx.xxx | Suspicious authentication source |
| User Account | privileged-user | Monitored account activity |
| Authentication Timestamp | TBD | Login outside behavioral baseline |
| ASN/Provider | TBD | Infrastructure ownership context |

---

## Analyst Assessment

Based on the available evidence, the authentication activity was assessed as suspicious due to deviations from the user’s established access behavior and the use of unfamiliar external infrastructure. While no confirmed account compromise was identified during the investigation, the observed activity warranted additional validation procedures and continued monitoring.

The investigation highlighted the importance of behavioral authentication monitoring, infrastructure reputation analysis, and contextual review when evaluating potentially unauthorized access events involving privileged accounts.

At the current stage of analysis, the activity remains under review pending confirmation from the affected user and additional authentication log correlation.

---

## Recommendations

- Validate login activity directly with the affected user
- Review MFA activity associated with the account
- Continue monitoring for additional anomalous authentication attempts
- Review access logs for unusual resource interaction
- Increase alerting sensitivity for privileged account activity
- Conduct password reset procedures if compromise indicators increase
- Preserve authentication logs and supporting evidence for continued analysis

---

## Conclusion

The investigation identified suspicious authentication behavior involving an internal privileged account accessing enterprise resources from unfamiliar external infrastructure. While no confirmed compromise was identified during the initial investigation phase, the activity demonstrated several elevated-risk characteristics requiring continued monitoring, user validation, and additional authentication analysis.

The case reinforces the importance of contextual authentication monitoring and rapid analyst review when investigating potential insider risk or unauthorized access scenarios.

---

## Supporting Artifacts

Additional investigation artifacts can be found within the following folders:

- `evidence/`
- `iocs/`
- `screenshots/`
