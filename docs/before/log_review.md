# Logs review

In most environment, there are more logs generated in a day that most security staff could review in possibly months if not year. As such, most log reviews will be based on rules and automation up to the point of a manual review.
Rules ideally match your risk assessment and threat model.
Infrastructure rules are a good based but in most cases, business context is key.

Example monitoring matrix: System, OS, Comment, OS Logs, Audit Policy set, OS Log Alerting, Audit Policy Verified, Application Logs, Application Log Alerting, OS log Alerting Tested, Application Log Alerting Tested

## Coverage

### Base

* Authentication activities (logged in/out, elevation of privileges...)
* Critical activities aka Do your homework to find what it is your context, especially business context

### Linux

* kernel (audit, apparmor, selinux...)
* ssh
* sudo
* su
* cron, at
* ntp
* Mail
* Process activity (auditd, osquery, kunai, EDR...)
* Package manager history (apt, dnf...)
* Network state change, firewall, vpn...

Ensure facily and severity settings match your requirements.

### Macos

### Windows

* Process activity (EventID 4688, sysmon, osquery, EDR...)
* Accounts activity (4624, 4625, 4648, 4672, 4673, 4720, 4724, 4732, 4735, 4738)
* User creation (4720, 4722, 4724, 4738)
* Scheduled activity (129, 141, 4698, 4702)
* Services activity (7000, 7022, 7024, 7030, 7031, 7034, 7036, 7040, 7045; 4697)
* Audit policy (4719)
* Network access (5140, 5145)
* Object access (4656)
* Removable media (6416; 400, 410, 10000, 20001, 4657; MDE DeviceEvents)
* Windows time (35)
* Logs cleared (104, 1102)
* RDP, TerminalServices (1056)
* OS version (6009)
* Domain Controller (4769, 4771)
* Application error (1000)
* Network state change, vpn...
* System Log: Event IDs 4614,4610,4611, and 4622

See references for more

### IoT/Network
(network appliances, camera, physical security systems like badges control points...)

* Dhcp
* Tftp

### Applications

* Web logs
* Web proxy
* File storage, file transfer tools (sftp, samba/win shares, moveit...)
* Database, selection by CRUD, stored procedures for example depending on criticality/volumes
* Hypervisors
* HR platform
* CRM platform

### Cloud

* CSPM
* SSO
* File storage (s3 buckets, azure storage account...)

## LLMs, Chatbots

* Input, Output
* Model and training dataset version

Be mindful if logs are covered for corporate tools and dev tools (ex: M365 Copilot vs various Azure Copilot instances)

## Validation

* Expected data is present: by process, by eventid
  * Authentication
  * Critical activities like elevation of privilege, backup/restore, data dump/takeout, change of access
* Expected non-relevant data is not present: noise, sensitive data (password, PII/PHI...), high volume ops errors/warnings
* Base set of use cases and alerts working. Example criteria: for a given period like last 30 days, match at least once (in your lab normally), but not more than ten times a day (else, probably too noisy aka need tuning. or major problem)

## References

* [Guide to Computer Security Log Management, NIST SP800-92](https://csrc.nist.gov/publications/detail/sp/800-92/final)
* [Effective Daily Log Monitoring, PCI DSS](https://www.pcisecuritystandards.org/documents/Effective-Daily-Log-Monitoring-Guidance.pdf): "10.7 Retain audit trail history for at least one year, with a minimum of three months immediately available for analysis (for example, online, archived, or restorable from backup)."
* [Logging Cheat Sheet, OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html), [A09:2021  Security Logging and Monitoring Failures](https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/), [A09:2025 Security Logging & Alerting Failures, OWASP Top10 2025](https://owasp.org/Top10/2025/A09_2025-Security_Logging_and_Alerting_Failures/)
* [M-21-31 MEMORANDUM FOR THE HEADS OF EXECUTIVE DEPARTMENTS AND AGENCIES, USA, Aug 2021](https://www.whitehouse.gov/wp-content/uploads/2021/08/M-21-31-Improving-the-Federal-Governments-Investigative-and-Remediation-Capabilities-Related-to-Cybersecurity-Incidents.pdf) - Appendix C: Logging Requirements  Technical Details
* [M-26-14 MEMORANDUM FOR THE HEADS OF EXECUTIVE DEPARTMENTS AND AGENCIES, USA, May 2026](https://www.whitehouse.gov/wp-content/uploads/2026/05/M-26-14-Ensuring-Effective-and-Efficient-Agency-Logging-and-Network-Visibility-to-Defend-Against-Evolving-Cyber-Threats.pdf), [ White House charts new course for federal agencies and cybersecurity logging A Trump administration memo published last week replaces one from its predecessor, with at least one analyst fearful of potential harmful results. May 2026](https://cyberscoop.com/white-house-federal-cybersecurity-logging-rules/) - pending publication of logging reference architecture by CISA
* [Designing systems for investigability is an underrated discipline. Someone should write a book, think of it like thread modeling. Any new application or feature should have a review for how and what it logs for both security and debugging. Aug 2020](https://twitter.com/davehull/status/1294646265016393731)
* [Get your logging act together, loggers! Dec 2018](https://www.hexacorn.com/blog/2018/12/05/get-your-logging-act-together-loggers/)
* [Creating Audit Logs for Security Professionals, Jan 2023](https://medium.com/@julieasparks/creating-audit-logs-for-security-professionals-2f81b4046bce)
* [Priority logs for SIEM ingestion: Practitioner guidance, AU, May 2025](https://www.cyber.gov.au/resources-business-and-government/maintaining-devices-and-systems/system-hardening-and-administration/system-monitoring/implementing-siem-and-soar-platforms/priority-logs-for-siem-ingestion-practitioner-guidance), [pdf](https://www.cyber.gov.au/sites/default/files/2025-05/Priority%20logs%20for%20SIEM%20ingestion%20-%20Practitioner%20guidance.pdf), [Priority logs for SIEM ingestion: practitioner guidance, US, May 2025](https://media.defense.gov/2025/May/27/2003722069/-1/-1/0/PRIORITY-LOGS-FOR-SIEM-INGESTION-PRACTITIONER-GUIDANCE.PDF)
* <https://audit-logs.tax>, <https://github.com/shellcromancer/audit-log-wall-of-shame>
* Company's logging policy, standard, RACI and whatever applicable references
* Environment's risk assessment and threat model
* <https://www.malwarearchaeology.com/cheat-sheets>
* <https://what2log.com/>
* Antisyphon SOC Summit 2026: [Augmented Detection Engineering](https://www.blackhillsinfosec.com/wp-content/uploads/2026/03/TALK-4-1130-am-Wade-Wells-Augmented-Detection-Engineering.pdf)
* [What Should I Ingest Into My SIEM? Mar 2026](https://isaacdunham.github.io/posts/what-should-i-ingest-into-my-siem/)

Platforms

* Linux
* Macos
* Windows:
  * <https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/plan/appendix-l--events-to-monitor>
  * <https://learn.microsoft.com/en-us/windows/security/threat-protection/use-windows-event-forwarding-to-assist-in-intrusion-detection>
  * jpcert: <https://jpcertcc.github.io/ToolAnalysisResultSheet/>, <https://github.com/JPCERTCC/LogonTracer>
  * <https://github.com/mdecrevoisier/Splunk-input-windows-baseline>
  * <https://www.13cubed.com/downloads/windows_event_log_cheat_sheet.pdf>
  * <https://www.malwarearchaeology.com/logging>, <https://www.malwarearchaeology.com/cheat-sheets/>, <https://static1.squarespace.com/static/552092d5e4b0661088167e5c/t/5b8f091c0ebbe8644d3a886c/1536100639356/Windows+ATT&CK_Logging+Cheat+Sheet_ver_Sept_2018.pdf>
  * <https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4697>
  * <https://isc.sans.edu/forums/diary/Windows+Events+log+for+IRForensics+Part+2/21501/>
  * <https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4720>
  * <https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4732>
  * <https://xcancel.com/jepayneMSFT/status/763025567344054275>

* Azure
  * [Configure Microsoft Entra diagnostic settings for activity logs](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/howto-configure-diagnostic-settings)
  * [Configure Unified Sensor to support advanced identity detections (Preview)](https://learn.microsoft.com/en-us/defender-for-identity/deploy/prerequisites-sensor-version-3#configure-unified-sensor-to-support-advanced-identity-detections-preview) - MDI
  * [MICROSOFT EXPANDED CLOUD LOGS IMPLEMENTATION PLAYBOOK, CISA, Jan 2025](https://www.cisa.gov/sites/default/files/2025-01/microsoft-expanded-cloud-logs-implementation-playbook-508c.pdf)
  * [Microsoft Sentinel Platform: Audit Logs and Where to Find Them, Dec 2025](https://techcommunity.microsoft.com/blog/MicrosoftSentinelBlog/microsoft-sentinel-platform-audit-logs-and-where-to-find-them/4481838) `CloudAppEvents` table 
* Saas Workday
  * [Workday REST services directory: activityLogging](https://community.workday.com/sites/default/files/file-hosting/restapi/index.html#privacy/v1/get-/activityLogging)
  * [Workday User Activity Logs - Datadog](https://docs.datadoghq.com/integrations/workday/)
  * [Workday solution - Sentinel](https://marketplace.microsoft.com/en-us/product/azure-applications/azuresentinel.azure-sentinel-solution-workday?tab=Overview), [How Defender for Cloud Apps helps protect your Workday environment](https://learn.microsoft.com/en-us/defender-cloud-apps/protect-workday#connect-workday-to-microsoft-cloud-app-security)
  * [Workday integration - Sumologic](https://www.sumologic.com/help/docs/integrations/saas-cloud/workday/)
* Saas [Log Sources for Security Monitoring - Snowflake](https://snowflake-labs.github.io/Sentry/reference/log-sources.html): identifiers, views, MITRE ATT&CK

* [Creating Audit Logs for Security Professionals, Jan 2023](https://medium.com/@julieasparks/creating-audit-logs-for-security-professionals-2f81b4046bce)
* [A Brief Ode to Data Minimization, Jun 2025](https://little-flying-robots.ghost.io/a-brief-ode-to-data-minimization/?ref=knowtheory-linking-people-to-it)

* [Analyse logs in a way that leaves other sloths in the dust. ](https://github.com/francevarotz98/SlothLog) - http, ftp logs
* [Your Logs are Lying: How Network Infrastructure Impacts EDR Network Telemetry, Jul 2025](https://academy.bluraven.io/blog/how-network-infrastructure-impacts-edr-telemetry): web proxy and EDR case
* [Copilot Broke Your Audit Log, but Microsoft Won’t Tell You, Aug 2025](https://pistachioapp.com/blog/copilot-broke-your-audit-log)
* RDP: [RDP Event Log DFIR, Feb 2019](https://dfironthemountain.wordpress.com/2019/02/15/rdp-event-log-dfir/), [Windows Forensic Analysis: some thoughts on RDP related Event IDs, Jun 2020](https://andreafortuna.org/2020/06/04/windows-forensic-analysis-some-thoughts-on-rdp-related-event-ids/), [Making Sense of RDP Connection Event Logs, Nov 2020](https://frsecure.com/blog/rdp-connection-event-logs/), [Windows RDP Event IDs Cheatsheet, Feb 2022](https://www.socinvestigation.com/windows-rdp-event-ids-cheatsheet/)
* [A Primer on Forensic Investigation of Salesforce Security Incidents, Aug 2025](https://www.salesforce.com/blog/a-primer-on-forensic-investigation-of-salesforce-security-incidents/)
* [Finding Seamless SSO usage, Aug 2025](https://nathanmcnulty.com/blog/2025/08/finding-seamless-sso-usage/) - EntraID
* [Detecting Velociraptor misuse, Aug 2025](https://docs.velociraptor.app/knowledge_base/tips/velocirator_misuse/), [Velociraptor incident response tool abused for remote access, Aug 2025](https://news.sophos.com/en-us/2025/08/26/velociraptor-incident-response-tool-abused-for-remote-access/)
* [Why SIEM Rules Fail and How to Fix Them: Insights from 160 Million Attack Simulations, Aug 2025](https://thehackernews.com/2025/08/why-siem-rules-fail-and-how-to-fix-them.html), [Picus BLUE REPORT 2025](https://www.picussecurity.com/blue-report)
* [Rethinking SIEM, Oct 2025](https://zendannyy.substack.com/p/rethinking-siem)
* [I get asked all the time which tables each Sentinel connector writes to. Surprisingly, the answer isn’t straightforward: many connectors share tables, others write to multiple tables, and—until now—there hasn’t been a single, complete list. Dec 2025](https://www.linkedin.com/posts/oshezaf_i-get-asked-all-the-time-which-tables-each-activity-7401808297906814976-9Acl), <https://github.com/Azure/Azure-Sentinel/tree/master/Tools/Solutions%20Analyzer>
* [Velociraptor Misuse, Pt. II: The Eye of the Storm, Dec 2025](https://www.huntress.com/blog/velociraptor-misuse-part-two-eye-of-the-storm)
* https://github.com/Azure/Azure-Sentinel/blob/master/Tools/Solutions%20Analyzer/connector-docs/connectors-index.md
* [Log Sources Your SOC Needs for Detection, Forensics, and Hunting- MUST-HAVE, Apr 2026](https://socautomators.substack.com/p/log-sources-your-soc-needs-for-detection-78f)
* [Introducing EvidenceForge: Synthetic security logs that don’t look (as) fake, May 2026](https://blog.talosintelligence.com/introducing-evidenceforge-synthetic-security-logs-that-dont-look-as-fake/), <https://github.com/Cisco-Talos/EvidenceForge>
* [Mapping out your unknown: A threat hunter’s guide to Salesforce, Jun 2026](https://securitylabs.datadoghq.com/articles/mapping-out-your-unknown-threat-hunters-guide-to-salesforce/), [Detecting the Klue supply chain attack in Salesforce instances, Jun 2026](https://securitylabs.datadoghq.com/articles/detecting-the-klue-supply-chain-attack-in-salesforce/), [Cybercrime Breaches Klue: Salesforce Data Impacted for Many Victims, including Huntress, Jun 2026](https://www.huntress.com/blog/klue-breach-investigation)

Retention

* [Security log retention: Best practices and compliance guide, Jun 2025](https://auditboard.com/blog/security-log-retention-best-practices-guide)
* [HIPAA Data Security and Retention Requirements, Jun 2025](https://www.bytebase.com/blog/hipaa-data-security-and-retention-requirements/): "Audit Controls and Monitoring [...] 6 years. [...] medical record retention varies by state law. [...] 1 to 11 years"
* [EU Revives Plan for Year-Long Data Retention Across Digital Services, Including Encrypted Apps, Dec 2025](https://reclaimthenet.org/eu-revives-plan-for-year-long-data-retention)

LLMs, Chatbots

* [Whitepapers/GuidesGenAI Incident Response Guide 1.0, Jul 2025](https://genai.owasp.org/resource/genai-incident-response-guide-1-0/)
* [Tinker Tailor LLM Spy Investigate & Respond to Attacks on GenAI Chatbots](https://drive.google.com/file/d/1RQtcTZUdYSAUWU9zqnFsfAl6nEtCGPkY/view), Bsidesmtl, Sep 2025
> Understand the risks: architecture, data, and agency
> Implement logging for inputs, outputs, and guardrails
> Prepare your guardrail toolbox to stop incidents
* [Task 1.1: Search the audit log for Copilot interactions in Microsoft Purview ](https://microsoft.github.io/TechExcel-Elevate-your-Copilot-for-M365-technical-proficiency/docs/L5Ex01/0101.html), [How to Investigate Microsoft 365 Copilot Interactions, Mar 2025](https://nikkichapple.com/investigating-microsoft-365-copilot-interactions/)
* [Microsoft Purview protections for Copilot, Apr 2025](https://techcommunity.microsoft.com/blog/microsoftmechanicsblog/microsoft-purview-protections-for-copilot/4406384)
* [Secure and govern AI apps and agents with Microsoft Purview, Jul 2025](https://techcommunity.microsoft.com/blog/microsoft-security-blog/secure-and-govern-ai-apps-and-agents-with-microsoft-purview/4429925)
