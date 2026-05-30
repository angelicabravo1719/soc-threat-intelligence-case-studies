## Selected Indicator

- URL: hxxp://123.10.239[.]8:56074/i
- Domain: N/A (IP-based URL)
- Source: URLHaus
- Date Reviewed: May 29 2026
- Reason Selected: Listed in URLHaus as a potentially malicious URL.

## Initial Observations

- URL uses a direct IP address rather than a registered domain.
- Non-standard port (56074) observed.
- URL was identified through a public malware/threat intelligence feed.
- Further validation required.

## VirusTotal Findings

### Detection Ratio

4/92 security vendors flagged the URL as malicious.

### Observed Characteristics

- Direct IP-based URL
- Non-standard port (56074)
- HTTP response status 200 OK
- Content type identified as application/zip
- Tags included downloads-zip and downloads-elf

### Vendor Detections

- BitDefender: Malware
- G-Data: Malware
- GreyNoise: Malicious
- Lionic: Malicious

### Initial Assessment

The URL appears to host downloadable content rather than a traditional webpage. The use of a direct IP address, non-standard port, downloadable archive content, and multiple malicious detections increases the likelihood that the URL is associated with malware distribution activity.
