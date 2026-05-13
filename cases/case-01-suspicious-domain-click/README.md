# Case 01 – Suspicious Domain Click Investigation

## Executive Summary

A user reported interacting with a suspicious Microsoft 365 login page after clicking a link received through email communication. Initial review identified the domain as recently registered and designed to imitate a legitimate authentication portal. Further investigation revealed indicators consistent with credential harvesting activity commonly associated with phishing campaigns targeting enterprise users.

The investigation focused on validating the legitimacy of the domain, identifying associated indicators of compromise (IOCs), assessing potential risk exposure, and documenting findings for escalation and remediation purposes.

Based on the available evidence, the activity was assessed as malicious with moderate-to-high confidence due to domain impersonation behavior, suspicious registration characteristics, and phishing-related infrastructure indicators identified through OSINT analysis.

---

## Investigation Overview

| Investigation Detail | Information |
|---|---|
| Case ID | CASE-001 |
| Investigation Type | Phishing / Suspicious Domain Investigation |
| Detection Source | User-reported suspicious email link |
| Initial Severity | Medium |
| Analyst Objective | Validate domain legitimacy and assess phishing risk |
| Investigation Status | Closed – Malicious Activity Confirmed |

---

## Alert Details

A user reported receiving an email containing a hyperlink directing them to what appeared to be a Microsoft 365 authentication portal. After clicking the link, the user observed unusual formatting and reported the activity to the security team for validation.

Initial triage identified several suspicious characteristics including:
- Recently registered domain activity
- Typosquatting behavior
- Suspicious hosting reputation
- Login page impersonation
- Potential credential harvesting indicators

The domain was isolated for further analysis and reviewed through multiple OSINT and threat intelligence sources.

---

## Evidence Collected

### Evidence Sources
- WHOIS domain registration lookup
- VirusTotal domain analysis
- URLScan page behavior review
- DNS resolution checks
- Screenshot comparison against legitimate login portals

### Key Findings
- Domain registration age was less than 30 days
- Domain naming convention attempted to imitate Microsoft authentication services
- Hosting infrastructure showed low reputation scoring
- External intelligence sources flagged suspicious activity associations
- Login page appearance attempted to mimic legitimate Microsoft branding

---

## OSINT Findings

| Source | Finding |
|---|---|
| WHOIS Lookup | Recently registered domain with limited registration history |
| VirusTotal | Suspicious reputation and phishing-related detections identified |
| URLScan.io | Login page impersonation behavior observed |
| DNS Review | Hosted on infrastructure with limited reputation history |
| AbuseIPDB | Related infrastructure showed prior abuse reports |

The collected OSINT data supported the assessment that the domain was likely being used for phishing and credential harvesting operations.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---|---|---|
| Initial Access | Phishing: Spearphishing Link | T1566.002 |
| Credential Access | Input Capture | T1056 |
| Reconnaissance | Gather Victim Identity Information | T1589 |
| Defense Evasion | Masquerading | T1036 |

---

## Indicators of Compromise (IOCs)

| IOC Type | Value | Context |
|---|---|---|
| Domain | login-microsoft-authenticate[.]com | Suspected phishing domain |
| URL | hxxps://login-microsoft-authenticate[.]com | Credential harvesting page |
| IP Address | 185.xxx.xxx.xxx | Hosting infrastructure |
| Email Subject | “Account Verification Required” | Social engineering lure |

---

## Analyst Assessment

Based on the evidence collected during the investigation, the domain activity was assessed as malicious with moderate-to-high confidence. The domain demonstrated characteristics commonly associated with phishing infrastructure, including impersonation of trusted services, recent registration activity, and suspicious reputation indicators identified through external intelligence platforms.

No confirmed credential compromise was identified during the investigation; however, due to the nature of the interaction, the affected user account should be monitored for suspicious authentication activity and password reset procedures should be considered.

The investigation highlights the continued risk posed by credential harvesting campaigns leveraging trusted brand impersonation techniques to target enterprise users.

---

## Recommendations

- Block the identified domain and associated IP infrastructure
- Reset credentials for potentially affected accounts
- Review authentication logs for anomalous login activity
- Increase monitoring for similar phishing indicators
- Conduct phishing awareness reinforcement for affected users
- Enable or verify MFA enforcement on impacted systems
- Preserve collected evidence for future reference and correlation

---

## Conclusion

The investigation determined that the reported domain activity was consistent with a phishing and credential harvesting attempt targeting enterprise authentication workflows. Through OSINT validation, IOC enrichment, and evidence correlation, the domain was confirmed as suspicious and appropriate remediation recommendations were documented for escalation and defensive response activities.

---

## Supporting Artifacts

Additional investigation artifacts can be found within the following folders:

- `evidence/`
- `iocs/`
- `screenshots/`
