# Analyst Notes – Case 03

## Alert Summary

- Alert Type: Suspicious PowerShell Execution
- Hostname: WIN-WS-001
- User Account: jdoe
- Process Name: powershell.exe
- Severity: Medium
- Investigation Status: Under Review

---

## Initial Observations

- PowerShell executed with encoded command-line arguments.
- Activity originated from a user workstation.
- Encoded commands are frequently used for automation but may also be used to conceal malicious activity.
- Additional review is required to determine intent.

---

## Investigation Questions

The following questions will guide the investigation:

1. What command was executed?
2. Was the command legitimate administrative activity?
3. Was PowerShell launched by a trusted parent process?
4. Did the command attempt to download content or communicate externally?
5. Were additional suspicious processes created?
6. Is there evidence of persistence, privilege escalation, or credential access?

---

## Working Hypotheses

### Hypothesis 1

The activity represents legitimate administrative or automation-related PowerShell usage.

### Hypothesis 2

The activity originated from a script or software deployment process.

### Hypothesis 3

The activity may represent suspicious PowerShell execution requiring escalation.

---

## Evidence Collected

### PowerShell Logs

- Pending investigation.

### Command-Line Analysis

- Pending investigation.

### Process Execution Review

- Pending investigation.

### Threat Intelligence Review

- Pending investigation.
