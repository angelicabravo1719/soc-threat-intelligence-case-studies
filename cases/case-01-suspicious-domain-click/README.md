# Case 01 – Suspicious URL and Infrastructure Analysis

## Executive Summary

A suspicious URL was identified through URLHaus and selected for passive threat intelligence analysis. The investigation focused on validating the reputation of the associated infrastructure, identifying potential indicators of compromise (IOCs), and assessing whether the observed activity demonstrated characteristics commonly associated with malware distribution.

The investigation was conducted using publicly available threat intelligence and OSINT resources, including URLHaus, VirusTotal, URLScan, AbuseIPDB, and WHOIS infrastructure analysis. Findings revealed multiple malicious vendor detections, downloadable archive content, ELF-related indicators, and hosting on a direct public IP address utilizing a non-standard service port.

Based on the collected evidence, the indicator was assessed as suspicious with moderate confidence and demonstrated characteristics commonly associated with malware delivery infrastructure.

---

## Investigation Overview

| Investigation Detail | Information                                                       |
| -------------------- | ----------------------------------------------------------------- |
| Case ID              | CASE-001                                                          |
| Investigation Type   | Threat Intelligence / Infrastructure Analysis                     |
| Detection Source     | URLHaus                                                           |
| Initial Severity     | Medium                                                            |
| Analyst Objective    | Validate the legitimacy and risk associated with a suspicious URL |
| Investigation Status | Closed – Suspicious Activity Identified                           |

---

## Alert Details

The investigated indicator originated from URLHaus, a public threat intelligence platform used to track potentially malicious URLs and malware distribution infrastructure.

The URL under investigation was:

```text
hxxp://123.10.239[.]8:56074/i
```

Initial observations identified several characteristics warranting further investigation:

* Direct IP-based URL rather than a registered domain
* Non-standard service port (56074)
* Association with downloadable content
* Listing within a public malware tracking platform
* Potential malware distribution indicators

The indicator was subjected to passive analysis through multiple intelligence sources.

---

## Evidence Collected

### Evidence Sources

* URLHaus
* VirusTotal
* URLScan
* AbuseIPDB
* WHOIS Infrastructure Review

### Key Findings

* URL listed within URLHaus malware tracking database
* VirusTotal identified multiple malicious detections
* Downloadable ZIP archive content observed
* ELF-related indicators identified
* Infrastructure hosted on a direct public IP address
* Service operated over a non-standard port
* URLScan was unable to successfully retrieve page content
* AbuseIPDB contained prior abuse reports associated with the IP address

---

## OSINT Findings

| Source     | Finding                                                     |
| ---------- | ----------------------------------------------------------- |
| URLHaus    | Indicator listed within malware tracking database           |
| VirusTotal | 4 security vendors identified malicious activity            |
| VirusTotal | Content type identified as application/zip                  |
| VirusTotal | Tags included downloads-zip and downloads-elf               |
| URLScan    | Unable to successfully retrieve content                     |
| AbuseIPDB  | IP address contained prior abuse reports                    |
| WHOIS      | Infrastructure owned by China Unicom Henan Province Network |

The collected intelligence suggested the infrastructure was associated with suspicious activity and warranted additional review.

---

## MITRE ATT&CK Mapping

| Tactic               | Technique                      | ID        | Evidence                                   |
| -------------------- | ------------------------------ | --------- | ------------------------------------------ |
| Initial Access       | Phishing: Spearphishing Link   | T1566.002 | Suspicious URL delivery                    |
| Execution            | User Execution                 | T1204     | Downloadable content delivered from URL    |
| Resource Development | Acquire Infrastructure         | T1583     | Infrastructure hosted on public IP address |
| Command and Control  | Non-Application Layer Protocol | T1095     | Non-standard port usage observed           |

---

## Indicators of Compromise (IOCs)

| IOC Type       | Value                               | Context                                     |
| -------------- | ----------------------------------- | ------------------------------------------- |
| URL            | hxxp://123.10.239[.]8:56074/i       | Suspicious URL selected for investigation   |
| IP Address     | 123.10.239.8                        | Infrastructure serving downloadable content |
| Port           | 56074                               | Non-standard service port                   |
| ASN            | AS4837                              | Infrastructure ownership                    |
| Organization   | China Unicom Henan Province Network | Network owner                               |
| Country        | China                               | Infrastructure location                     |
| Content Type   | application/zip                     | Downloadable archive content                |
| File Indicator | downloads-elf                       | Potential Linux executable delivery         |

---

## Analyst Assessment

Based on passive threat intelligence analysis, the investigated URL demonstrated multiple indicators consistent with suspicious or potentially malicious activity.

The indicator was identified through URLHaus and subsequently reviewed using VirusTotal, URLScan, AbuseIPDB, and WHOIS infrastructure analysis. VirusTotal identified multiple vendor detections and classified the content as a downloadable ZIP archive with ELF-related indicators. Additional analysis revealed the infrastructure was hosted on a direct public IP address using a non-standard service port.

While AbuseIPDB reporting alone was insufficient to classify the infrastructure as malicious, the combination of threat intelligence sources, downloadable content indicators, and malicious vendor classifications increased the overall risk assessment.

No direct interaction with the URL was performed during the investigation. Findings were based exclusively on passive OSINT and threat intelligence sources.

---

## Recommendations

* Block the identified URL and associated IP address if observed within the environment
* Monitor for related infrastructure and indicators
* Review security controls capable of detecting suspicious downloads
* Continue monitoring threat intelligence sources for updated classifications
* Preserve collected evidence for future correlation activities
* Educate users regarding suspicious links and downloadable content

---

## Conclusion

The investigation identified a suspicious URL associated with downloadable archive content and multiple malicious detections across public threat intelligence platforms.

Analysis of supporting infrastructure revealed hosting on a public IP address associated with China Unicom network infrastructure and operation over a non-standard service port. While infrastructure ownership alone did not indicate malicious activity, the totality of evidence supported classification of the indicator as suspicious and worthy of further monitoring.

This case demonstrates the importance of correlating multiple threat intelligence sources when evaluating potentially malicious infrastructure and highlights the value of passive OSINT techniques within SOC investigation workflows.

---

## Investigation Workflow

1. Indicator identified through URLHaus
2. Reputation review performed using VirusTotal
3. Infrastructure analysis attempted through URLScan
4. IP reputation reviewed through AbuseIPDB
5. WHOIS and infrastructure ownership validated
6. Indicators documented and correlated
7. MITRE ATT&CK mapping performed
8. Analyst assessment completed

---

## Supporting Artifacts

Additional investigation artifacts can be found within the following folders:

* `evidence/`
* `iocs/`
* `screenshots/`
