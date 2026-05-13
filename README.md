# SOC Threat Intelligence Case Studies

This repository contains structured SOC-style threat intelligence and incident investigation case studies designed to simulate real-world analyst workflows. The investigations focus on identifying, validating, documenting, and communicating security events through a combination of OSINT research, IOC analysis, MITRE ATT&CK mapping, evidence correlation, and escalation-oriented reporting.

The purpose of this repository is to strengthen practical cybersecurity analysis skills while demonstrating structured investigative thinking, technical documentation, and risk-focused communication commonly used within SOC, threat intelligence, and incident response environments.

---

## Scope of Work

The investigations within this repository focus on:

- SOC-style alert triage and incident investigation workflows
- OSINT validation and threat enrichment techniques
- IOC analysis and contextual risk assessment
- MITRE ATT&CK framework mapping
- Evidence collection and correlation
- Escalation-ready analyst documentation
- Translating technical findings into business-relevant risk
- Differentiating confirmed evidence from assumptions during investigations

---

## Investigation Methodology

Each case study follows a structured investigation approach intended to mirror operational SOC and threat analysis workflows:

1. Initial alert or suspicious activity identification
2. Evidence collection and validation
3. IOC enrichment and OSINT investigation
4. MITRE ATT&CK tactic and technique mapping
5. Risk and impact assessment
6. Analyst findings and escalation recommendations
7. Documentation of investigation artifacts and supporting evidence

---

## Investigation Categories

- Phishing and suspicious domain investigations
- Insider threat and unauthorized access analysis
- PowerShell and endpoint activity investigations
- IOC validation and enrichment workflows
- OSINT-based threat verification
- Escalation-ready SOC documentation
- Threat triage and evidence correlation

---

## Tools & Frameworks

| Category | Tools / Frameworks |
|---|---|
| OSINT | VirusTotal, URLScan.io, WHOIS, AbuseIPDB |
| Network Analysis | Wireshark |
| Documentation | Markdown, evidence logging, IOC tracking |
| Frameworks | MITRE ATT&CK, NIST Incident Response Lifecycle |
| Operating Systems | Windows, Ubuntu (WSL) |
| Investigation Workflow | IOC enrichment, evidence correlation, escalation documentation |

---

## Current Investigations

| Case | Focus Area | Status |
|---|---|---|
| Case 01 – Suspicious Domain Click | Phishing / OSINT Investigation | In Progress |
| Case 02 – Insider IP Risk | Unauthorized Access Analysis | In Progress |
| Case 03 – Malicious PowerShell Activity | Endpoint / Execution Analysis | In Progress |

---

## Repository Structure

```plaintext
soc-threat-intelligence-case-studies/
│
├── README.md
│
├── cases/
│   ├── case-01-suspicious-domain-click/
│   ├── case-02-insider-ip-risk/
│   └── case-03-malicious-powershell-activity/
│
├── templates/
│   ├── investigation-template.md
│   ├── incident-report-template.md
│   ├── evidence-log-template.md
│   └── ioc-template.md
│
└── diagrams/
