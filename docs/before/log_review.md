
In most environment, there are more logs generated in a day that most security staff could review in possibly months if not year. As such, most log reviews will be based on rules and automation up to the point of a manual review.
Rules ideally match your risk assessment and threat model.
Infrastructure rules are a good based but in most cases, business context is key.

## Coverage

### Base

* Authentication activities (logged in/out, elevation of privileges...)
* Critical activities aka Do your homework to find what it is your context, especially business context

### Linux

* ssh
* sudo
* su
* cron, at
* ntp
* Mail
* Process activity (auditd, osquery, kunai, EDR...)
* Network state change, vpn...

### Macos

### Windows

* Process activity (EventID 4688, sysmon, osquery, EDR...)
* Scheduled Activities
* RDP, TerminalServices
* Network state change, vpn...

### IoT/Network
(network appliances, camera, physical security systems like badges control points...)

* Dhcp
* Tftp

### Applications

* Web logs
* Web proxy
* File storage, file transfer tools (sftp, samba/win shares, moveit...)
* Database, selection by CRUD, stored procedures for example depending on criticality/volumes

### Cloud

* CSPM
* SSO
* File storage (s3 buckets, azure storage...)


## Validation

* Expected data is present: by process, by eventid
  * Authentication
  * Critical activities like elevation of privilege, backup/restore, data dump/takeout, change of access
* Expected non-relevant data is not present: noise, sensitive data (password, PII/PHI...), high volume ops errors/warnings
* Base set of use cases and alerts working. Example criteria: for a given period like last 30 days, match at least once (in your lab normally), but not more than ten times a day (else, probably too noisy aka need tuning. or major problem)

## References

* [Guide to Computer Security Log Management, NIST SP800-92](https://csrc.nist.gov/publications/detail/sp/800-92/final)
* [Effective Daily Log Monitoring, PCI DSS](https://www.pcisecuritystandards.org/documents/Effective-Daily-Log-Monitoring-Guidance.pdf)
* [Logging Cheat Sheet, OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html), [A09:2021  Security Logging and Monitoring Failures](https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/)
* [M-21-31 MEMORANDUM FOR THE HEADS OF EXECUTIVE DEPARTMENTS AND AGENCIES, USA, Aug 2021](https://www.whitehouse.gov/wp-content/uploads/2021/08/M-21-31-Improving-the-Federal-Governments-Investigative-and-Remediation-Capabilities-Related-to-Cybersecurity-Incidents.pdf) - Appendix C: Logging Requirements  Technical Details
* [Designing systems for investigability is an underrated discipline. Someone should write a book, think of it like thread modeling. Any new application or feature should have a review for how and what it logs for both security and debugging. Aug 2020](https://twitter.com/davehull/status/1294646265016393731)
* [Get your logging act together, loggers! Dec 2018](https://www.hexacorn.com/blog/2018/12/05/get-your-logging-act-together-loggers/)
* [Creating Audit Logs for Security Professionals, Jan 2023](https://medium.com/@julieasparks/creating-audit-logs-for-security-professionals-2f81b4046bce)
* https://audit-logs.tax, https://github.com/shellcromancer/audit-log-wall-of-shame
* Company's logging policy, standard, RACI and whatever applicable references
* Environment's risk assessment and threat model
* https://www.malwarearchaeology.com/cheat-sheets
* https://what2log.com/
* Linux
* Macos
* Windows:
  * https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/plan/appendix-l--events-to-monitor
  * https://learn.microsoft.com/en-us/windows/security/threat-protection/use-windows-event-forwarding-to-assist-in-intrusion-detection
  * jpcert: https://jpcertcc.github.io/ToolAnalysisResultSheet/, https://github.com/JPCERTCC/LogonTracer
  * https://github.com/mdecrevoisier/Splunk-input-windows-baseline
  * https://www.13cubed.com/downloads/windows_event_log_cheat_sheet.pdf
