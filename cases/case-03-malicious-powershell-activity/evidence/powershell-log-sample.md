# Simulated PowerShell Execution Log

| Timestamp | Host | User | Process | Command |
|---|---|---|---|---|
| 2026-05-15 14:22 EST | WIN-WS-001 | jdoe | powershell.exe | powershell.exe -EncodedCommand SQBFAFgA... |

---

## Alert Context

A security monitoring alert identified PowerShell executing with encoded command-line arguments on a Windows workstation.

The use of encoded commands does not automatically indicate malicious activity; however, attackers frequently use encoded PowerShell commands to:

- Obfuscate activity
- Evade basic detections
- Download payloads
- Execute scripts
- Perform reconnaissance

Additional analysis is required to determine the legitimacy of the command.
