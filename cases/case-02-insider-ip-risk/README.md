# Case 02 – Insider IP Risk Investigation

## Executive Summary

A suspicious authentication event was identified involving a privileged user account successfully authenticating from an unfamiliar source IP address outside normal business hours. The activity triggered review due to deviations from the user's expected access patterns and subsequent access to multiple enterprise resources, including a privileged administrative system.

The investigation focused on reviewing authentication activity, evaluating behavioral indicators, assessing infrastructure context, and determining whether the observed activity was consistent with legitimate user behavior or potential unauthorized access.

Based on the available evidence, the activity was assessed as suspicious but unconfirmed. Several risk factors were identified, including after-hours access, unfamiliar infrastructure, and privileged resource interaction. However, no direct evidence of account compromise or malicious activity was identified during the investigation.

---

## Investigation Overview

| Investigation Detail | Information |
|---|---|
| Case ID | CASE-002 |
| Investigation Type | Authentication Investigation / Insider Risk Review |
| Detection Source | Authentication Monitoring Alert |
| Initial Severity | Medium |
| Analyst Objective | Validate legitimacy of suspicious authentication activity |
| Investigation Status | Closed – Suspicious Activity Observed |

---

## Alert Details

A successful authentication event involving a privileged user account was identified originating from an unfamiliar source IP address. The authentication occurred outside normal business hours and was followed by access to multiple enterprise resources.

Initial review identified several characteristics requiring additional validation:

- Authentication outside expected business hours
- Unfamiliar source infrastructure
- Privileged account involvement
- Access to multiple enterprise resources
- Administrative system interaction

The authentication sequence was reviewed to determine whether the observed behavior aligned with expected user activity.

---

## Evidence Collected

### Evidence Sources

- Authentication Log Review
- Geolocation Analysis
- Infrastructure Ownership Review
- IOC Correlation
- Behavioral Analysis

### Key Findings

- Successful authentication recorded
- MFA approval completed successfully
- Activity occurred outside expected business hours
- Multiple resources accessed within a short timeframe
- Administrative system access observed
- Source infrastructure was unfamiliar to the user profile

---

## Authentication Timeline

| Timestamp | User | Source IP | Resource |
|---|---|---|---|
| 2026-05-13 22:41 EST | privileged-user | 203.0.113.45 | Internal Portal |
| 2026-05-13 22:44 EST | privileged-user | 203.0.113.45 | File Share |
| 2026-05-13 22:49 EST | privileged-user | 203.0.113.45 | Admin Console |

The observed activity demonstrated progression across multiple resources following successful authentication.

---

## Behavioral Analysis

Several aspects of the activity deviated from the established user baseline:

| Observation | Assessment |
|---|---|
| After-hours login | Unusual |
| Unfamiliar infrastructure | Unusual |
| Privileged account access | Elevated Risk |
| MFA approval | Reduces likelihood of unauthorized access |
| Multiple resource access | Requires validation |

While no single indicator independently confirmed malicious activity, the combination of observed behaviors justified additional investigation.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID | Evidence |
|---|---|---|---|
| Initial Access | Valid Accounts | T1078 | Successful authentication using valid credentials |
| Persistence | External Remote Services | T1133 | Authentication originating from external infrastructure |
| Defense Evasion | Use of Legitimate Credentials | T1078 | Successful login without authentication failures |
| Discovery | Account Discovery | T1087 | Potential access to enterprise resources following authentication |

---

## Indicators of Compromise (IOCs)

| IOC Type | Value | Context |
|---|---|---|
| IP Address | 203.0.113.45 | Source authentication infrastructure |
| User Account | privileged-user | Account associated with alert |
| Authentication Result | Success | Successful login event |
| MFA Status | Approved | MFA validation recorded |
| Resource | Internal Portal | Initial accessed resource |
| Resource | File Share | Secondary accessed resource |
| Resource | Admin Console | Privileged resource accessed |

---

## Analyst Assessment

The investigation identified authentication activity that deviated from expected user behavior and therefore warranted additional review. Several risk indicators were present, including unfamiliar infrastructure, after-hours access, and privileged account involvement.

At the same time, successful MFA validation and the absence of confirmed malicious activity reduced confidence that the event represented unauthorized access.

Based on the available evidence, the activity was classified as suspicious but unconfirmed. Additional user verification and historical authentication review would be recommended before escalating the event as a confirmed security incident.

This investigation demonstrates the importance of combining authentication telemetry, behavioral analysis, and infrastructure context when evaluating potentially suspicious login activity.

---

## Recommendations

- Validate activity directly with the affected user
- Review historical authentication patterns
- Monitor for additional anomalous logins
- Increase alerting sensitivity for privileged accounts
- Review MFA enrollment and authentication history
- Preserve authentication records for future correlation
- Conduct additional investigation if similar activity recurs

---

## Conclusion

The investigation identified unusual authentication activity involving a privileged user account accessing enterprise resources from unfamiliar infrastructure outside normal business hours.

Although no confirmed compromise was identified, the combination of behavioral deviations and privileged resource access justified additional scrutiny and monitoring. The activity remains classified as suspicious but unconfirmed based on the available evidence.

This case highlights the importance of contextual authentication analysis and demonstrates how analysts assess risk using behavioral indicators rather than relying solely on reputation-based detections.

---

## Investigation Workflow

1. Authentication alert identified
2. Authentication logs reviewed
3. Resource access sequence analyzed
4. Geolocation context evaluated
5. Infrastructure ownership reviewed
6. IOC correlation performed
7. MITRE ATT&CK mapping completed
8. Analyst assessment documented

---

## Supporting Artifacts

Additional investigation artifacts can be found within the following folders:

- `evidence/`
- `iocs/`
- `screenshots/`
