
Incident templates

## Incident bridge structure

## Documents

* Incident Report
  * Executive summary
  * Recommendations: can align format on other teams (pentest, architecture review...) and map to NIST 800-53 Security Control, CIS and other frameworks. align on business objectives.
  * per section, classification and audience to allow easy redact.
  * Annex: Attacker Profile, TTPs per ATT&CK MITRE, IOC, Vulnerability scan...
* Post-Mortem (unless you include it in incident report)

## Emails

Each of those can have variant depending on audience: security stakeholders, executives, all employees...

* Incident alert
* Threat alert
* Vulnerability alert
* VIP / Management / Technical communication
* Internal Communication: Intranet publication, Email, Conference
* External Communication: Press Release, Press Conference

### Vulnerability alert
Subject: 
Internal Rating
CVSS (https://www.first.org/cvss/calculator/4.0)
EPSS (ex: https://www.cvedetails.com/epss/epss-score-history.html?delta=110; https://github.com/theowni/EPSS-Calculator)
CISA KEV
Public Exploit: trivial? popular tools Metasploit, Nuclei?

Summary
(5 Ws, business impact, exploited? internet-facing or customer-facing?)

Details

Mitigation
(patch, workaround, custom config...)

Detections
(sigma, yara, logs...)

References
(vendor)
(isc sans)
(security vendors, blogs...)
https://vulnerability.circl.lu/

Exploitation path
https://www.linkedin.com/posts/laurent-biagiotti-19779284_cve-2025-xxxx-ce-nest-pas-quun-num%C3%A9ro-activity-7321071823452872704-DNcs
https://github.com/Galeax/CVE2CAPEC
https://galeax.github.io/CVE2CAPEC/

## Others

text message, phone call or similar depending on your environment

## References

* [Mandiant APT1, Feb 2013](https://www.mandiant.com/resources/apt1-exposing-one-of-chinas-cyber-espionage-units)
* [Incident Response Fundamentals  Communication, Sean Mason, Sep 2017](https://blogs.cisco.com/security/incident-response-fundamentals-communication)
* [Ransomware attack on City of Pensacola, Executive Summary, Jan 2020](https://www.cityofpensacola.com/DocumentCenter/View/18879/Deloitte-Executive-Summary-PDF?bidId=)
* [When we spot #redteam we report: 
- Exec summary 
- Key findings (how'd they get in, what'd they do?)
- Timeline of events (1st alert, remediation)
- ATT&CK tactics & details
- Popped accounts, hosts, NBIs/HBIs
- How to kick 'em out 
- How to improve
Any 🔑 items missing? Jun 2020](https://twitter.com/jhencinski/status/1278017846732378113)
* [Forensic reports in a nutshell... May 2021 - xkcd](https://twitter.com/XRY_mike/status/1391358750670344192)
* [TheDFIRReport, 2020-2022](https://thedfirreport.com/)

* [Common Vulnerability Scoring System SIG](https://www.first.org/cvss/)
* [Exploit Prediction Scoring System (EPSS)](https://www.first.org/epss/)
* [Known Exploited Vulnerabilities (KEV) Catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog)
* https://github.com/alexdevassy/AI-Powered-Vulnerability-Impact-Analyzer
