# Case 03 – Suspicious Encoded PowerShell Activity

## Executive Summary

A suspicious PowerShell execution event was identified involving the use of an encoded command-line argument. Because PowerShell encoding is commonly used to conceal command intent, the activity was selected for investigation to determine whether it represented legitimate administrative activity or potential malicious behavior.

The investigation focused on decoding the command, analyzing its functionality, reviewing associated process activity, and determining whether the observed behavior aligned with known malicious PowerShell techniques.

The encoded command was successfully decoded and determined to execute the PowerShell cmdlet `Get-Process`, which performs process enumeration on a Windows system. No evidence of malware execution, persistence mechanisms, privilege escalation, or external communication was identified.

Based on the available evidence, the activity was classified as legitimate administrative behavior and closed as benign.

---

## Investigation Overview

| Investigation Detail | Information |
|---|---|
| Case ID | CASE-003 |
| Investigation Type | Endpoint Investigation / PowerShell Analysis |
| Detection Source | PowerShell Monitoring Alert |
| Initial Severity | Medium |
| Analyst Objective | Determine whether encoded PowerShell execution was malicious |
| Investigation Status | Closed – Benign Activity |

---

## Alert Details

A monitoring alert identified PowerShell executing with encoded command-line arguments.

Encoded PowerShell commands are commonly used for:

- Administrative automation
- Script execution
- Configuration management
- Command obfuscation
- Malware delivery and execution

Because encoded commands conceal the underlying command from casual review, further analysis was required to determine the true purpose of the execution.

---

## Evidence Collected

### Evidence Sources

- PowerShell Command Review
- Command Decoding Analysis
- Process Enumeration Output
- Analyst Review
- IOC Correlation

### Key Findings

- PowerShell executed using an encoded command.
- The command was successfully decoded.
- Decoded command performed process enumeration.
- No file downloads were observed.
- No external network communications were identified.
- No persistence mechanisms were detected.
- No privilege escalation behavior was observed.

---

## PowerShell Execution Details

### Encoded Command

```powershell
powershell.exe -EncodedCommand RwBlAHQALQBQAHIAbwBjAGUAcwBzAA==
```

### Decoded Command

```powershell
Get-Process
```

### Command Function

The `Get-Process` cmdlet retrieves information regarding processes currently running on a Windows system.

The command is commonly used by:

- System Administrators
- IT Support Personnel
- Security Analysts
- Incident Responders

for system monitoring and troubleshooting activities.

---

## Behavioral Analysis

The decoded command was analyzed to determine whether it exhibited characteristics commonly associated with malicious PowerShell activity.

| Behavior | Observed |
|---|---|
| Process Enumeration | Yes |
| File Download | No |
| External Network Connection | No |
| Registry Modification | No |
| Persistence Creation | No |
| Privilege Escalation | No |
| Credential Access | No |

The observed behavior was consistent with legitimate administrative activity.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID | Evidence |
|---|---|---|---|
| Discovery | Process Discovery | T1057 | Get-Process enumerates active processes |
| Execution | PowerShell | T1059.001 | PowerShell used to execute command |
| Defense Evasion | Obfuscated/Encoded Files and Information | T1027 | Encoded PowerShell command observed |

---

## Indicators of Compromise (IOCs)

| IOC Type | Value | Context |
|---|---|---|
| Process Name | powershell.exe | PowerShell execution |
| Encoded Command | RwBlAHQALQBQAHIAbwBjAGUAcwBzAA== | Encoded PowerShell argument |
| Decoded Command | Get-Process | Process enumeration activity |
| Hostname | WIN-WS-001 | Investigated endpoint |
| User Account | angel | Executing user |

---

## Analyst Assessment

The investigation successfully decoded and reviewed the PowerShell command associated with the alert.

Although encoded PowerShell execution is frequently associated with attacker tradecraft, the decoded command performed only process enumeration and did not demonstrate behaviors commonly associated with malicious activity.

The command did not attempt to:

- Download external content
- Establish network connections
- Modify system configurations
- Create persistence mechanisms
- Escalate privileges
- Access credentials

Based on the collected evidence, the activity was determined to be consistent with legitimate administrative or investigative use of PowerShell.

---

## Recommendations

- Continue monitoring PowerShell activity for encoded commands.
- Review command behavior rather than relying solely on encoded-command detections.
- Maintain PowerShell logging where available.
- Investigate future encoded commands on a case-by-case basis.
- Preserve evidence for training and analyst development purposes.

---

## Conclusion

The investigation identified PowerShell execution using an encoded command-line argument and successfully decoded the underlying command.

Analysis determined that the command performed only process enumeration through the `Get-Process` cmdlet and did not exhibit characteristics commonly associated with malicious PowerShell activity.

This case demonstrates the importance of validating command behavior before classifying activity as malicious and highlights the role of PowerShell analysis within SOC investigation workflows.

---

## Investigation Workflow

1. PowerShell alert identified
2. Encoded command collected
3. Base64 string decoded
4. Decoded command reviewed
5. Process behavior analyzed
6. MITRE ATT&CK mapping performed
7. IOC documentation completed
8. Analyst assessment documented

---

## Supporting Artifacts

Additional investigation artifacts can be found within the following folders:

- `evidence/`
- `iocs/`
- `screenshots/`
