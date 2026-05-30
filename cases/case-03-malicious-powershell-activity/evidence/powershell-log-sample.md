# Simulated PowerShell Execution Log

| Timestamp | Host | User | Process | Command |
|---|---|---|---|---|
| 2026-05-30 21:15 EST | WIN-WS-001 | angel | powershell.exe | powershell.exe -EncodedCommand RwBlAHQALQBQAHIAbwBjAGUAcwBzAA== |

---

## Alert Context

A monitoring alert identified PowerShell executing with encoded command-line arguments.

The use of encoded PowerShell commands is commonly associated with:

- Administrative automation
- System management
- Script execution
- Command obfuscation

Because encoded commands can conceal intent, analysts must decode and review the command before determining risk.

The command was selected for investigation to determine whether the activity was legitimate or suspicious.
