# Case 01 — Suspicious Domain Click

## Scenario

A simulated SOC alert flagged a domain interaction from an end-user endpoint. The objective was to determine whether the domain posed a credible threat, assess potential impact, and produce an escalation-ready finding.

---

## Initial Signal

- **Alert Type:** Suspicious domain activity  
- **Source:** Simulated SOC alert / log review  
- **Indicator:** `secure-login-verify[.]net` flagged for investigation  

---

## Scope Definition

- **Who:** End user (simulated internal employee)  
- **What:** HTTP GET request to flagged domain following email link click  
- **When:** 2024-11-14 09:32 UTC  
- **Where:** Windows endpoint, corporate network segment  

---

## Artifacts Collected

- Domain name and full URL string  
- WHOIS registration data  
- VirusTotal scan results (screenshot)  
- URLScan.io behavioral report (screenshot)  
- DNS resolution history  

---

## Analysis

### Domain Reputation

- **VirusTotal detection ratio:** 7/94 vendors flagged as malicious  
- **Notable flags:** Phishing (Fortinet, Kaspersky), Suspicious (BitDefender)  
- **Observation:** Domain categorized as credential harvesting by multiple vendors  

---

### WHOIS Analysis

- **Domain age:** Registered 6 days prior to alert  
- **Registrar:** NameSilo LLC  
- **Suspicious patterns:** Newly registered domain, privacy-protected registrant, no prior web presence  

---

### Behavioral Indicators

- Domain name mimics a login/verification portal (“secure-login-verify”), consistent with phishing patterns  
- No legitimate business association identified  
- URLScan results showed a login form with no SSL certificate on the landing page  

---

## Validation (OSINT)

Cross-referenced findings across multiple OSINT sources, including VirusTotal, URLScan.io, and WHOIS data.

All sources consistently indicated:
- Newly registered domain with no legitimate history  
- Multiple vendor detections  
- Structural indicators consistent with credential phishing  

**Confidence Level:** High  

---

## Risk Assessment

- **Risk Level:** High  

- **Reasoning:**  
  Domain exhibits multiple high-confidence phishing indicators, including recent registration, vendor detection overlap, credential-harvesting structure, and absence of a legitimate business identity  

- **Potential Impact:**  
  Credential compromise if user entered login information, leading to possible account takeover or lateral movement depending on access level  

---

## Recommendation

- Block `secure-login-verify[.]net` at the DNS or proxy layer  
- Conduct a follow-up with the affected user to determine whether credentials were entered  
- If credentials were submitted:
  - Initiate immediate password reset  
  - Review account activity within a 48-hour window  
- Add domain as an IOC to internal threat intelligence tracking  

---

## Analyst Takeaway

This investigation highlights that no single indicator should drive a final decision. While domain naming and age raised initial suspicion, escalation was justified only after consistent validation across multiple independent OSINT sources.

The ability to quickly correlate findings and document a clear, defensible conclusion is critical in reducing response time and limiting potential business impact in a real SOC environment.
