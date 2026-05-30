# Analyst Notes – Case 02

## Alert Summary

- Alert Type: Suspicious Authentication Activity
- User Account: privileged-user
- Source IP: 203.0.113# Analyst Notes – Case 02

## Alert Summary

- Alert Type: Suspicious Authentication Activity
- User Account: privileged-user
- Source IP: 203.0.113.45
- Authentication Result: Successful
- MFA Status: Approved
- Severity: Medium
- Investigation Status: Under Review

---

## Initial Observations

- Login occurred outside normal business hours.
- Source IP does not match the user's expected access pattern.
- User account possesses elevated privileges.
- MFA approval was successfully completed.
- Authentication originated from unfamiliar infrastructure.
- Additional validation required to determine legitimacy.

---

## Investigation Questions

The following questions will guide the investigation:

1. Does the source IP belong to known user infrastructure?
2. Does the geolocation align with expected user behavior?
3. Has the account previously authenticated from this IP address?
4. Were additional resources accessed after authentication?
5. Is the IP address associated with abuse reports or suspicious activity?
6. Is there evidence of credential misuse or unauthorized access?

---

## Working Hypotheses

### Hypothesis 1

The authentication activity represents legitimate user access from a previously unseen location.

### Hypothesis 2

The authentication activity originated from a VPN, proxy service, or cloud-hosted infrastructure.

### Hypothesis 3

The authentication activity may represent unauthorized use of valid credentials.

---

## Evidence Collected

### Authentication Logs

The following authentication events were identified:

| Timestamp | User | Source IP | Resource |
|---|---|---|---|
| 2026-05-13 22:41 EST | privileged-user | 203.0.113.45 | Internal Portal |
| 2026-05-13 22:44 EST | privileged-user | 203.0.113.45 | File Share |
| 2026-05-13 22:49 EST | privileged-user | 203.0.113.45 | Admin Console |

### Observed Behavior

- Successful authentication occurred outside normal business hours.
- MFA approval was successfully completed.
- The same source IP accessed multiple enterprise resources.
- Access included a privileged administrative resource.
- Activity occurred within a short timeframe following authentication.

### Preliminary Assessment

The observed authentication sequence may be consistent with legitimate administrative activity; however, the combination of unfamiliar infrastructure, privileged account access, and after-hours activity warrants additional investigation.

### Authentication Logs

- Authentication succeeded.
- MFA approval recorded.
- Activity occurred outside normal business hours.

### Infrastructure Review

- Pending investigation.

### Geolocation Review

- Pending investigation.

### Reputation Analysis

- Pending investigation..45
- Severity: Medium
- Status: Under Review

## Initial Observations

- Login occurred outside normal business hours.
- Source IP is unfamiliar.
- User account possesses elevated privileges.
- MFA approval was successful.
