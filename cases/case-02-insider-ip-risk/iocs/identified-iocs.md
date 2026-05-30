# Identified IOCs – Case 02

| IOC Type | Value | Source | Context |
|---|---|---|---|
| IP Address | 203.0.113.45 | Authentication Log | Source of suspicious authentication activity |
| User Account | privileged-user | Authentication Log | Account associated with alert |
| Authentication Result | Success | Authentication Log | Successful login event |
| MFA Status | Approved | Authentication Log | MFA approval recorded |
| Resource | Internal Portal | Authentication Log | Initial accessed resource |
| Resource | File Share | Authentication Log | Secondary accessed resource |
| Resource | Admin Console | Authentication Log | Privileged resource accessed |
| Timestamp | 2026-05-13 22:41 EST | Authentication Log | Initial authentication event |
| Timestamp | 2026-05-13 22:44 EST | Authentication Log | File Share access |
| Timestamp | 2026-05-13 22:49 EST | Authentication Log | Admin Console access |

---

## IOC Analysis

### Authentication Activity

The investigation identified successful authentication activity originating from a previously unseen source IP address associated with a privileged user account.

### Access Pattern

The authenticated session accessed multiple enterprise resources within a short timeframe, including a privileged administrative resource.

### Risk Factors

- Authentication occurred outside normal business hours.
- Source infrastructure was unfamiliar.
- Account possessed elevated privileges.
- Multiple resources were accessed following authentication.
- MFA approval was successfully completed.

### Analyst Assessment

The collected indicators do not independently confirm account compromise. However, the combination of after-hours activity, unfamiliar infrastructure, and privileged account access supports continued monitoring and additional validation procedures.
