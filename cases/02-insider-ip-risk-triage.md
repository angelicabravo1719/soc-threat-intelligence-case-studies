# 02 — Possible Insider / IP Risk (Beginner-Friendly Triage)

## Learning Note (Honest + Clear)
This is a **practice scenario** (sanitized and not from a real company incident).  
I’m documenting how I would think through a potential insider/IP risk situation: what signals matter, what evidence to gather, and how to recommend next steps **without jumping to conclusions**.

---

## What happened (Trigger)
A user account is showing unusual behavior: a spike in file access/downloads and/or activity involving external storage or external sharing. We need to determine if this is normal work activity or a potential risk.

---

## The 4 things I’m trying to figure out
1) Is this behavior **normal** for the user’s job, or unusual?
2) What data might be involved (sensitivity / IP / confidential info)?
3) Is there any sign of **data leaving** the company (exfiltration)?
4) What should we do **right now** to reduce risk while staying fair and accurate?

---

## What we know vs what we don’t know (Scope)
### What we know
- Who the user is + their role/team (if available)
- What systems were involved (file server, SharePoint/Drive, code repo, etc.)
- Rough timing (when the unusual activity occurred)

### What we don’t know yet
- Whether the user had a valid business reason (deadline, role change, project)
- Whether the files were sensitive
- Whether the data actually left the environment (uploaded/shared/copied)

### Safe assumption
Treat it as **sensitive** and preserve evidence, but avoid labeling intent until evidence supports it.

---

## First 10 minutes (simple checklist)
- Identify the user + time window of activity
- Confirm what “unusual” means (higher volume than baseline? off-hours? new destination?)
- Preserve the most important logs (timestamps matter)
- Determine what data types were accessed (sensitive vs normal)
- Check if any “data leaving” path exists (external share, uploads, USB)
- Write a short summary: facts, what’s unknown, and recommended next step

---

## What evidence I would collect (in plain language)

### From file access / content systems
- File access logs (which folders/files, how many, what times)
- Sensitivity labels (if the org uses them) or location of sensitive projects
- Bulk actions (mass downloads, mass copy, zip/compression)

### From cloud collaboration tools (SharePoint/Google Drive/OneDrive/etc.)
- Audit logs: new external shares, link creation, permission changes
- Large downloads or sync behavior
- New external domains or recipients

### From endpoint (the user’s computer) — if available
- USB insertion events / file copy to removable drives
- New compression tools or unusual processes
- Large archive creation (zip/rar/7z)

### From identity/authentication (logins)
- VPN/logins at unusual hours
- New devices or new locations
- Multiple failed logins or “impossible travel” style patterns

### HR/Context signals (only via proper channels)
- Departure notice / resignation timeline
- Recent access changes or role transitions
- Prior policy reminders or prior issues (if applicable)

---

## What I can do now vs what I’d ask for on a real security team

### What I can do now (as a learner)
- Explain common insider/IP risk patterns (staging, bulk downloads, off-hours activity)
- Think in timelines and correlate “what happened first”
- Document facts vs assumptions clearly
- Propose fair next steps that preserve evidence and reduce risk

### What I would ask for in an enterprise/SOC
- SIEM view: file access + cloud audit + auth + endpoint events in one timeline
- EDR telemetry: processes, archives created, external device activity
- DLP alerts: attempted uploads/shares of sensitive files (if available)
- Case management context and approved escalation path (security/HR/legal)

---

## What I think might be happening (Analysis)
This situation could be **benign or risky**. My job is to evaluate signals without assuming intent.

### Benign possibilities
- Deadline-driven work (end-of-quarter / deliverable crunch)
- Role change requiring access to new files
- Approved transfer or backup process

### Higher-risk possibilities
- “Staging” behavior: collecting and bundling files (zip/rar) before transfer
- New external destinations: personal email, personal cloud, unfamiliar domains
- Off-hours bulk access + new device/location
- Accessing data unrelated to job role (“curiosity browsing” in sensitive areas)

### What would confirm higher risk
- Evidence of data leaving: external shares, uploads, USB copying
- Strong anomalies vs baseline (volume/time/type of data)
- Correlation with departure timeline (if known via proper channels)

---

## How I decide what to do next (Decision Rules)
- If there is clear evidence of data leaving to an unapproved destination → escalate and contain quickly
- If it’s unusual but impact is unclear → preserve evidence, limit exposure carefully, and keep investigating
- If behavior matches a valid business reason (confirmed) → document and close or monitor

---

## Recommended actions

### Right now
- Preserve logs and document timeline (who/what/when)
- Identify whether sensitive/IP data was involved
- Look for clear “data leaving” signals (external share/upload/USB)

### Soon
- Escalate through the correct internal process (security/HR/legal) if risk is credible
- Reduce exposure with minimal disruption (least privilege / temporary controls) if appropriate
- Create an investigation-ready summary: facts, confidence, next steps

### Longer-term
- Improve controls and monitoring around sensitive repositories
- Training/awareness for safe handling of confidential/IP material
- Review access policies (least privilege) and offboarding process

---

## Confidence (how sure am I?)
- Confidence: Low / Medium / High
- What would make me more sure:
  - Cloud audit logs confirming external shares/uploads
  - Endpoint evidence of USB copying or archive creation
  - Baseline comparison showing activity is truly abnormal for that role

---

## Executive Summary (easy to read)
A user account showed unusual file access behavior that could indicate either normal work activity or potential insider/IP risk. At this stage, intent is unknown, so the priority is to preserve evidence, clarify whether sensitive data was involved, and determine if any data left the environment via external sharing, uploads, or removable media. If evidence suggests an unapproved transfer path, the recommended next step is escalation through the proper security/HR/legal process and careful containment actions (least privilege, temporary restrictions) while maintaining accurate documentation. Confidence will increase with cloud audit logs, endpoint indicators (USB/archive creation), and baseline comparisons for the user’s normal activity.

