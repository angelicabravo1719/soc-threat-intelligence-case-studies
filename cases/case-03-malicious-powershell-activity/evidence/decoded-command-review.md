# Decoded Command Review

## Encoded Command

```powershell
powershell.exe -EncodedCommand RwBlAHQALQBQAHIAbwBjAGUAcwBzAA==
```

## Decoded Command

```powershell
Get-Process
```

## Command Purpose

The Get-Process cmdlet retrieves information about processes currently running on a Windows system.

The command is frequently used by:

- System administrators
- IT support personnel
- Security analysts
- Incident responders

to review system activity and identify running processes.

## Analyst Review

The decoded command was reviewed and determined to perform process enumeration only.

The command did not:

- Download files
- Execute remote content
- Modify registry settings
- Create persistence
- Escalate privileges
- Communicate externally

## Supporting Evidence

- powershell-process-enumeration.png
- encoded-command-generation.png

## Analyst Assessment

The encoded PowerShell command was successfully decoded and analyzed.

Although encoded commands are commonly associated with suspicious activity, the decoded command performed only process enumeration and demonstrated behavior consistent with legitimate administrative activity.

No malicious activity was identified during analysis.
