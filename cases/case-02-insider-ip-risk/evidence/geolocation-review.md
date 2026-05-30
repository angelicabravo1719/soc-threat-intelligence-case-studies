# Geolocation Review

## Investigation Objective

Determine whether the source IP address is consistent with the expected behavior of the authenticated user.

---

## Source IP

203.0.113.45

---

## Reported Location

- Country: Simulated External Region
- City: Unknown
- ISP/Provider: Under Review
- ASN: Under Review

---

## Expected User Behavior

- Expected Region: South Florida
- Expected Login Hours: 8:00 AM – 6:00 PM EST
- Expected Access Sources: Known corporate or residential infrastructure
- Account Type: Privileged User

---

## Observed Authentication Activity

| Timestamp | Resource |
|---|---|
| 2026-05-13 22:41 EST | Internal Portal |
| 2026-05-13 22:44 EST | File Share |
| 2026-05-13 22:49 EST | Admin Console |

---

## Behavioral Analysis

Several characteristics of the authentication activity deviated from the user's expected baseline:

- Login occurred outside normal business hours.
- Authentication originated from unfamiliar infrastructure.
- Multiple enterprise resources were accessed within a short timeframe.
- Activity included access to a privileged administrative resource.

No previous authentication history was available for comparison during this investigation.

---

## Analyst Assessment

Geolocation data alone cannot determine whether activity is malicious. However, when combined with after-hours access, unfamiliar infrastructure, and privileged account activity, the authentication event presents an elevated risk profile.

Additional validation should include:

- User verification
- Historical authentication review
- MFA validation
- Infrastructure reputation analysis

At the current stage of the investigation, the activity remains suspicious but unconfirmed.
