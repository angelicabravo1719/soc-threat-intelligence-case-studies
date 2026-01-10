# 01 — Suspicious Domain Click Triage

## Learning Context (Simulated Case)
This is a **sanitized, scenario-based exercise**. I am documenting:
- what evidence I would collect (or request),
- how I would analyze it,
- and what actions/recommendations I would make.

I separate **facts vs assumptions** and include a confidence level.

---

## Trigger
User reports clicking a link from an unexpected message; a new browser tab opened to a login-looking page. User closed the tab. Credential entry is unknown.

---

## Key Questions (What I need to determine)
1) Was this link malicious (phishing/malware) or benign?
2) Did the user enter credentials or download anything?
3) What systems/accounts could be impacted?
4) What is the recommended containment action right now?

---

## Scope & Assumptions
- Known:
  - User identity (internal) and approximate time of click
  - Source channel (email/chat/SMS) and the visible link text
- Unknown:
  - Whether credentials were entered
  - Whether a download occurred
  - Redirect chain and final destination(s)
- Assumptions (clearly labeled):
  - Treat as suspicious until validated via artifacts and OSINT

---

## Quick Triage Checklist (First 10 Minutes)
- Capture full URL (sanitize) + timestamp of click
- Identify where link came from (email, chat, SMS) and preserve message
- Check for obvious typosquatting / lookalike patterns
- Perform basic OSINT reputation checks (multi-source)
- Determine if credentials were entered or any file was downloaded
- Document findings + confidence and recommend immediate action

---

## Indicators & Artifacts to Collect

### From the user / message
- Screenshot or preserved copy of the message
- Sender address + reply-to (if email)
- Subject line and any attachments

### From the browser / endpoint (if available)
- Browser history entry + timestamp
- Download history (any file saved)
- User report of credential entry or prompts
- Endpoint security alert details (if any)

### From network/security logs (enterprise-request list)
- DNS query logs (domain resolution + timestamps)
- Proxy/firewall logs (destination, bytes transferred, user-agent)
- Authentication logs (new sign-ins shortly after click)

---

## What I can do today vs what I would request in an enterprise

### I can do today (training/lab context)
- Basic OSINT validation (reputation checks, typosquat reasoning, source comparison)
- Network fundamentals reasoning (DNS, TLS visibility limits, timeline thinking)
- Clear documentation: evidence log structure + executive summary

### I would request in an enterprise environment (if available)
- SIEM timeline view (auth, DNS, proxy, endpoint alerts correlated by time)
- Proxy / firewall logs (destinations, user-agent, bytes transferred)
- EDR telemetry (process execution, downloads, persistence indicators)
- File access / cloud audit logs (bulk downloads, external shares, new destinations)

---

## Analysis (What I think is happening)
- Likely scenario: credential phishing via a lookalike login page (typosquat / brand impersonation)
- Key checks:
  - Compare domain to legitimate brand domains (lookalike characters, extra words, unusual TLD)
  - OSINT: reputation + WHOIS pattern checks (recent registration, privacy-protected registrar, etc.)
  - Timeline correlation across message → click → DNS/proxy/browser events
- Alternative explanations:
  - Benign redirect/marketing tracker (lower likelihood if domain pattern is suspicious)
- What would confirm/deny:
  - Evidence of form submission (POST) to credential endpoint
  - Auth logs showing suspicious login attempts after click
  - Any downloaded file or new process execution on the endpoint

---

## Decision Points (How I decide what to do next)
- If domain is a clear lookalike + low reputation → treat as phishing and recommend blocking
- If user entered credentials → prioritize password reset + MFA verification + auth log review
- If a download occurred → treat as potential malware and request endpoint triage
- If no evidence of impact but suspicious indicators exist → document + monitor + awareness notification

---

## Recommendations

### Immediate
- Preserve the original message and capture the full URL (sanitized) with timestamps
- If confidence is high: block the domain at DNS/proxy controls (enterprise context)
- If credential entry is suspected: reset password + verify MFA + review recent sign-ins

### Short-term
- Search for similar messages across the org (if tooling allows) and warn targeted groups
- Add/adjust email filtering rules for the sender/domain patterns

### Long-term
- Awareness training on phishing indicators (lookalike domains, urgent password resets)
- Improve detection/response playbooks for suspicious link clicks (standard artifacts + timeline)

---

## MITRE ATT&CK (High-Level Mapping)
- Initial Access: Phishing (user clicked a suspicious link)
- Credential Access: Potential credential harvesting via lookalike login page

---

## Confidence
- Confidence level: (Low / Medium / High)
- What would increase confidence:
  - DNS/proxy logs confirming destination and redirect chain
  - Auth logs showing anomalous sign-ins after the click
  - Confirmation whether credentials were entered / file downloaded

---

## Executive Summary (Stakeholder-Friendly)
A user clicked a link from an unexpected message that directed them to a suspicious domain consistent with a lookalike/typosquat pattern. Based on initial review and OSINT validation, this activity is assessed as likely credential-phishing (confidence: <Low/Med/High>). Immediate recommended actions are to preserve the original message, block the domain (if confirmed malicious), and verify whether credentials were entered; if so, reset credentials and review authentication logs for anomalous sign-ins. Next steps include correlating DNS/proxy/browser timestamps (if available) and issuing a brief awareness note if similar messages are circulating.
