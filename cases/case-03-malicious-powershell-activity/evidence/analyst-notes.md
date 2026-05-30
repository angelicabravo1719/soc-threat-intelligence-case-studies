# Analyst Notes – Case 03

## Alert Summary

- Alert Type: Suspicious Encoded PowerShell Activity
- Hostname: WIN-WS-001
- User Account: jdoe
- Process Name: powershell.exe
- Severity: Medium
- Investigation Status: Under Review

---

## Initial Observations

- PowerShell executed with encoded command-line arguments.
- Encoded PowerShell commands are frequently used for both legitimate administration and malicious activity.
- Additional analysis is required to determine command intent.
- No evidence of malicious execution has been confirmed at this stage.

---

## Investigation Questions

1. What command was executed?
2. Does the decoded command perform administrative or malicious actions?
3. Was PowerShell launched by a trusted process?
4. Did the command attempt to download files or communicate externally?
5. Were additional processes spawned?
6. Is there evidence of persistence or privilege escalation?

---

## Working Hypotheses

### Hypothesis 1

The activity represents legitimate administrative PowerShell usage.

### Hypothesis 2

The activity originated from an automation or system management process.

### Hypothesis 3

The activity may represent suspicious PowerShell execution requiring escalation.

---

## Evidence Collected

### PowerShell Activity Review

- PowerShell command execution reviewed.
- Process enumeration performed using Get-Process.
- Running processes successfully identified.

### Screenshot Evidence

- powershell-process-enumeration.png

### Command Analysis

- Pending decoding and validation.

### Threat Intelligence Review

- Pending investigation.

---

## Current Assessment

At the current stage of the investigation, insufficient evidence exists to classify the activity as malicious.

Additional command analysis and behavioral review are required before determining final disposition.
