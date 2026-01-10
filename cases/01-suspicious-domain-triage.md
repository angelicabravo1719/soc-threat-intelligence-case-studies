# 01 — Suspicious Link / Domain Click (Beginner-Friendly Triage)

## Learning Note (Honest + Clear)
This is a **practice scenario** (sanitized and not from a real company incident).  
I’m showing **how I would think through the problem**, what evidence I would look for, and what actions I would recommend.

---

## What happened (Trigger)
A user clicked a link from an unexpected message. A new browser tab opened that looked like a login page. The user closed the tab. We don’t know if they typed their password.

---

## The 4 things I’m trying to figure out
1) Is the link **malicious** (phishing/malware) or **safe**?
2) Did the user type credentials or download anything?
3) What accounts/systems could be affected?
4) What should we do **right now** to reduce risk?

---

## What we know vs what we don’t know (Scope)
### What we know
- Who clicked it (the user)
- About when they clicked it (time window)
- Where it came from (email/text/chat)
- The domain/URL (the website address)

### What we don’t know yet
- If they entered a password
- If anything downloaded
- If the link redirected to other sites

### Safe assumption
Treat it as suspicious until we confirm it’s safe.

---

## First 10 minutes (simple checklist)
- Save the link (URL) and the time it was clicked (sanitize if needed)
- Save the original message (screenshot or copy)
- Check if the web address looks like a **lookalike** (example: “micros0ft” with a zero)
- Do quick OSINT checks (is the domain known bad? is it new?)
- Ask the user: “Did you type your password? Did you download anything?”
- Write a short summary of what we found and what we recommend next

---

## What evidence I would collect (in plain language)

### From the message (email/text/chat)
- Screenshot of the message
- Sender info (who it came from)
- Any attachments
- If email: the “email headers” (shows where it really came from)

### From the computer/browser (if available)
- Browser history (shows the site visited and time)
- Downloads list (shows if a file was saved)
- Any security warnings/alerts that popped up

### From company logs (if you have access in a real job)
- DNS logs (shows what website names the computer tried to reach)
- Proxy/firewall logs (shows what sites were contacted and how much data moved)
- Login/auth logs (shows if there were weird logins after the click)

---

## What I can do now vs what I’d ask for on a real security team

### What I can do now (as a learner)
- Spot lookalike domains and phishing patterns
- Use public info (OSINT) to check if the domain seems shady
- Think in timelines (message → click → website → possible login)
- Write clean notes and an executive summary

### What I would ask for in an enterprise/SOC
- SIEM view (one timeline that combines logs)
- EDR/endpoint tool info (did anything run/download?)
- Web proxy logs (exact URLs and redirects)
- Auth logs (any suspicious logins)

---

## What I think is happening (Analysis)
Most likely: **phishing** (a fake login page trying to steal credentials).

### Why
- The message was unexpected
- The page looked like a login page
- Suspicious links often use lookalike web addresses

### What would confirm it
- The domain has bad reputation or was registered recently
- Logs show the user visited a known phishing site
- Login logs show unusual sign-ins right after the click

### Other possibilities (less likely)
- A harmless redirect or marketing link (still needs validation)

---

## How I decide what to do next (Decision Rules)
- If the domain clearly looks fake AND OSINT is bad → treat as phishing and recommend blocking it
- If the user typed their password → reset password + confirm MFA + review sign-in activity
- If something downloaded → treat as potential malware and request endpoint checks
- If we can’t confirm impact yet → document, monitor, and warn others if similar messages exist

---

## Recommended actions

### Right now
- Preserve the message + URL + timestamps
- Confirm if the user entered credentials
- If credentials might be exposed: reset password and check MFA/sign-ins

### Soon
- Block the domain if confirmed malicious
- Look for other users who got the same message

### Longer-term
- Short phishing awareness reminder for users
- Improve email filtering rules/playbooks for “password reset” scams

---

## MITRE ATT&CK (simple mapping)
- **Phishing link click** (getting the user to visit the site)
- **Credential theft risk** (trying to capture username/password)

---

## Confidence (how sure am I?)
- Confidence: Low / Medium / High
- What would make me more sure:
  - DNS/proxy logs confirming the exact site visited and redirects
  - Auth logs showing suspicious logins after the click
  - Confirmation whether the user entered credentials or downloaded a file

---

## Executive Summary (easy to read)
A user clicked a suspicious link from an unexpected message and saw what looked like a login page. This is likely a phishing attempt (confidence: <Low/Med/High>) because the behavior matches common credential-stealing scams. The immediate next step is to preserve the message and link, confirm whether credentials were entered, and—if so—reset the password and review recent sign-ins. If the domain is confirmed malicious, it should be blocked and other users should be warned about similar messages.
