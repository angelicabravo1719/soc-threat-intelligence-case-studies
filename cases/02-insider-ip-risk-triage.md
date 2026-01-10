# 02 — Possible Insider / IP Risk (Beginner-Friendly Triage)

## Learning Note (Honest + Clear)
This is a **practice scenario** (sanitized and not from a real company incident).  
I’m documenting how I would think through a possible insider/IP risk situation in **simple, fair terms**—what I would look for, what evidence I would gather, and what actions I would recommend **without assuming bad intent**.

---

## What happened (Trigger)
A user account is showing unusual behavior: a spike in file access/downloads and activity that *might* involve sharing files outside the company. We need to figure out if this is normal work activity or a potential risk.

### Scenario (practice)
- User: Engineer on a product team  
- Time window: 9:30 PM–1:00 AM (after hours)  
- Activity: accessed ~1,200 files in “Design Docs”  
- Action: created a `.zip` file named `project_docs_backup.zip`  
- Also: created a share link to an external Gmail address  
- Context: business reason unknown (not confirmed)

---

## The 4 things I’m trying to figure out
1) Is this activity **normal** for this person’s role, or unusual?
2) What kind of files are involved—could any be **sensitive** (IP/confidential)?
3) Is there a clear sign the data **left the company** (shared, uploaded, copied)?
4) What should we do **right now** to reduce risk while staying fair and accurate?

---

## What we know vs what we don’t know (Scope)

### What we know
- Who the user is + their role/team (if available)
- Where the activity happened (file system / cloud drive / code repo, etc.)
- When it happened (time window)
- It happened after hours and was higher volume than typical
- A `.zip` was created, which can mean “bundling files together”
- A share link went to a personal email, which could be a “data leaving” path

### What we don’t know yet
- Whether there was a valid work reason (deadline, approved transfer, role change)
- Whether the files were actually sensitive
- Whether the share link was used (downloaded) or just created

### Safe assumption
Treat it as **sensitive**, preserve evidence, and avoid accusing intent until facts support it.

---

## First 10 minutes (simple checklist)
- Identify the user + exact time window
- Confirm what makes it “unusual” (after hours, volume, new destination)
- Preserve key logs (timestamps matter)
- Check what type of data was accessed (sensitive vs normal work files)
- Check for any “data leaving” path (external share, uploads, USB)
- Confirm whether external sharing is allowed and if that external recipient is approved
- Write a short summary: what we know, what we don’t know, and the next step

---

## What evidence I would collect (in plain language)

### From file access / content systems
- Which folders/files were accessed, how many, and at what times
- Whether any of the folders are known to contain sensitive/IP content
- Signs of bulk actions (mass download/copy or lots of files touched quickly)
- A short list of the top folders/files accessed + timestamps

### From cloud tools (SharePoint/Google Drive/OneDrive/etc.)
- Audit logs showing: share link created, permissions, and who it was sent to
- Whether the link allowed download and whether any download actually occurred
- Any new external recipients/domains (like personal email)

### From the user’s computer (endpoint) — if available
- Evidence the `.zip` was created (tool used + where it was created)
- Any USB use (plug-in events / file copy to removable drive)
- Any unusual new tools used for bundling or transferring files

### From login/authentication logs
- Whether the user logged in from a new device or new location
- Any unusual VPN activity or logins at strange times
- Any signs that the account could be compromised (lots of failed logins, etc.)

### HR / context signals (only through proper channels)
- Role changes, project transitions, or offboarding context (if relevant)
- Anything that helps explain whether this behavior could be normal

---

## What I can do now vs what I’d ask for on a real security team

### What I can do now (as a learner)
- Recognize common “risk patterns” (bulk access, bundling files, external sharing)
- Build a timeline and explain what happened in plain language
- Separate facts from assumptions and document confidence
- Suggest next steps that protect data without overreacting

### What I would ask for in an enterprise/SOC
- A SIEM timeline view combining file access + cloud audit + auth + endpoint logs
- Endpoint security/EDR telemetry to confirm file staging and transfers
- DLP alerts (if available) for sensitive files being uploaded/shared externally
- The approved escalation path and process (security/HR/legal)

---

## What I think might be happening (Analysis)
This could be **normal work** or a **potential risk**. My job is to evaluate signals and avoid jumping to conclusions.

### Normal possibilities
- Deadline-driven work (someone working late)
- Approved transfer/backup process
- Role or project change requiring extra file access

### Higher-risk possibilities
- “Staging” behavior: collecting lots of files and bundling them into a `.zip`
- External share to a personal email account (common risk path)
- After-hours bulk access that is unusual for the person’s baseline
- Accessing files outside the user’s normal job needs

### What would confirm higher risk
- Evidence that data actually left the company (downloaded via link, uploaded externally, copied to USB)
- Strong anomaly vs baseline (volume/time/data type doesn’t match typical work)
- Correlation with additional context (only via proper channels)

### Important note
Bulk access alone can be normal. **Bulk access + creating a zip + external sharing** is a stronger risk signal than any one event by itself.

---

## How I decide what to do next (Decision Rules)
- If there is clear evidence that sensitive data left to an unapproved destination → escalate quickly and contain
- If the activity is unusual but impact isn’t clear → preserve evidence, limit exposure carefully, keep investigating
- If a valid business reason is confirmed → document and close or monitor
- If the external share link allows download and goes to a personal email → recommend revoking the link (while preserving evidence) and escalating

---

## Recommended actions

### Right now
- Preserve logs and document the timeline (who/what/when)
- Confirm whether the accessed folder includes sensitive/IP material
- Determine whether data left the environment (external link downloads/uploads/USB)

### Soon
- Escalate through the correct internal process (security/HR/legal) if risk is credible
- Reduce exposure in a minimal-disruption way (least privilege / temporary controls) if appropriate
- Write an investigation-ready summary: facts, unknowns, confidence, next steps

### Longer-term
- Stronger controls/monitoring for sensitive repositories
- Training/awareness on handling confidential/IP data
- Review access policies (least privilege) and offboarding processes

---

## Confidence (how sure am I?)
- Confidence: Low / Medium / High
- What would make me more sure:
  - Cloud audit logs confirming the share link details and whether a download occurred
  - Endpoint evidence showing the archive was created and whether USB was used
  - Baseline comparison showing this activity is truly unusual for this role/user

---

## Executive Summary (easy to read)
A user account showed unusual after-hours activity: accessing a large number of files in “Design Docs,” creating a `.zip` archive, and creating a share link to a personal Gmail address. There may be normal explanations (working late or an approved transfer), but the combination of **bulk access + bundling files + external sharing** is a stronger signal that needs review. The immediate priority is to preserve the evidence, confirm whether sensitive/IP material was involved, and determine whether any data actually left the company (for example, whether the share link was downloaded or files were uploaded/copied). If the external share appears unapproved, the recommended next step is to revoke the link (while preserving evidence) and escalate through the proper security/HR/legal process. Confidence improves once cloud audit logs, endpoint indicators (archive creation/USB), and baseline behavior comparisons are reviewed.
