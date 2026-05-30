# Identified IOCs – Case 03

| IOC Type | Value | Source | Context |
|---|---|---|---|
| Process Name | powershell.exe | PowerShell Log | Suspicious process execution |
| Command Line | powershell.exe -EncodedCommand SQBFAFgA... | PowerShell Log | Encoded PowerShell execution |
| Hostname | WIN-WS-001 | PowerShell Log | Affected endpoint |
| User Account | jdoe | PowerShell Log | Associated user |
| Timestamp | 2026-05-15 14:22 EST | PowerShell Log | Initial execution event |

---

## IOC Analysis

### Process Activity

The investigation identified execution of PowerShell with encoded command-line arguments. Encoded PowerShell execution is commonly used by system administrators for automation purposes but is also frequently leveraged by threat actors to conceal activity.

### Risk Factors

- Encoded command execution observed
- PowerShell scripting activity detected
- User workstation involved
- Command content not yet validated
- Potential obfuscation indicators present

### Analyst Assessment

The identified indicators warrant additional investigation due to the use of encoded command-line arguments. At the current stage of analysis, the activity remains suspicious but unconfirmed pending command decoding and process review.
