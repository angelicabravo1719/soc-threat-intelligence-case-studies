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

## URLScan Findings

### Scan Result

URLScan was unable to successfully retrieve content from the target IP address.

### Observations

- URLScan reported that the website could not be scanned successfully.
- No webpage content was rendered.
- No screenshot preview was generated.
- The target may be unavailable, temporarily offline, protected, or no longer serving content.

### Analyst Interpretation

The inability to retrieve content does not indicate that the URL is benign. Combined with the VirusTotal detections and malware-related tags, the unavailable infrastructure may be consistent with short-lived or unstable malicious infrastructure commonly observed during malware distribution campaigns.

## AbuseIPDB Findings

### IP Address

123.10.239.8

### Reputation Information

- Abuse Confidence Score: 16%
- Reports: 2
- ASN: AS4837
- ISP: China Unicom Henan Province Network
- Usage Type: Fixed Line ISP
- Country: China
- City: Zhengzhou, Henan

### Analyst Interpretation

The IP address has been reported within AbuseIPDB and carries a moderate abuse reputation score. While the confidence score alone is not sufficient to classify the infrastructure as malicious, the reputation data supports additional scrutiny when combined with the VirusTotal detections, malware-related tags, and URLHaus listing.

The infrastructure appears to be associated with a residential or fixed-line provider rather than a major cloud hosting provider. Additional context should be considered alongside all other evidence sources before determining final risk.
