# Detection Engineering

## Strategy

* Know risks and priorities to define a strategy
  * Risks: ransomware, data breach, insider threat, network access/bridge, cloud storage, file transfer...
  * Domains: host/os, host/browser, host/office, host/other, network, cloud, application
  * Track behavior and immutable artifacts, not base IOC
  * Take decision based on data
  * Provide whatever is necessary to make a decision early

* If multiple defenders (MSSP, Joint-Venture...), identify where can add value to either validate coverage, either extend it.

## Process

* Workflow & Roles&Responsibilities
  * Detection-as-code, version control
  * CI/CD to evaluate rules regularly (lint, test), ideally in short cycles
  * Set a threshold to enable/disable/ask manual review
  * There should be at least on TP and one FP test cases.
  * New rule should have a preprod timeperiod (1d to 1w) where their alerting is handled by author team as final validation before be passed to normal operations

* Detection Lifecycle Management (DLM, DDLC...)

## Tools

### Version Control

* Git-based (Github, AzureDevops...)
* Actions
  * lint
  * testing
  * metrics
  * chain deployment between tier/geographic instances

### Metrics

Per rule

* Triggered in past period(s)
* True-Positive and False-Positive in past period(s)
* MTTD, MTTR
* Automated or not
* Mapped to MITRE ATT&CK and critical risks

Per log source
* Availability, latency, coverage, tampering per source/environment
* MITRE D3FEND

## Resources

* [Detection Engineering Maturity Matrix](https://detectionengineering.io)
* [Attack Flow, MITRE CTID](https://ctid.mitre.org/projects/attack-flow/), https://github.com/center-for-threat-informed-defense/attack-flow
* [Summiting the Pyramid, MITRE CTID](https://center-for-threat-informed-defense.github.io/summiting-the-pyramid/)
* [Open Threat Informed Detection Engineering](https://github.com/OpenTideHQ), [OpenTIDE mirror](https://code.europa.eu/ec-digit-s2/opentide), [[2024 03 11] OpenTIDE 1.0 Release](https://code.europa.eu/groups/ec-digit-s2/opentide/-/wikis/Blog/%5B2024-03-11%5D-OpenTIDE-1.0-Release)
* [infosecB/awesome-detection-engineering](https://github.com/infosecB/awesome-detection-engineering)
* [st0pp3r/awesome-detection-engineer](https://github.com/st0pp3r/awesome-detection-engineer/)
* [Detection Engineering Starter Pack](https://github.com/rfackroyd/detection-engineering-starter-pack)
* [Cyber Detection and Response knowledge dump](https://github.com/misterjulien/detection-and-response/wiki) - Unmaintained? Jul-Sep 2023
* [Detection knowledge repository – by Daniel Koifman](https://detections.xyz)

* [On Detection: Tactical to Functional](https://posts.specterops.io/on-detection/home): 16 posts Jul 2022-Jan 2025
* [About Detection Engineering, Sep 2022](https://cyb3rops.medium.com/about-detection-engineering-44d39e0755f0)
* [Baselines 101: Building Resilient, Frictionless SIEM Detections, Feb 2025](https://detect.fyi/baselines-101-building-resilient-frictionless-siem-detections-64dcbfb5afce): Detection Use Case: DCSync Attack & baseline periodic search
* [Tactical Tuning by Combinational Reduction, Apr 2025](https://detect.fyi/tactical-tuning-by-combinational-reduction-afc65cb0ef41)
* [Step-by-Step Guide: SOC Automation — SMB Threat Hunting & Incident Response Lab, Apr 2025](https://detect.fyi/step-by-step-guide-soc-automation-smb-threat-hunting-incident-response-lab-b6e48da2750d) with vmware, Windows AD, Kali Linux, Splunk SOAR Phantom and Enterprise
* [Can We Stop Documenting Our Detections? Apr 2025](https://detect.fyi/can-we-stop-documenting-our-detections-ded2201ec09b)
https://detect.fyi/do-you-know-your-detection-surface-8981289b0d25), https://github.com/gjGatos/detection_documentation_analysis
* [What is Detection as Code? How to implement Detection-as-Code, Apr 2025](https://medium.com/@tahirbalarabe2/what-is-detection-as-code-how-to-implement-detection-as-code-ae8e3bac22f7)
* [The Detection Opportunity Cost, May 2025](https://detect.fyi/the-detection-opportunity-cost-8cc0630a0266), [Without going through a hundred questions from yet another "Maturity Model" framework, how can you quickly assess how far you are when it comes to the #DetectionEngineering practice? Jul 2025](https://www.linkedin.com/posts/inode_the-detection-opportunity-cost-activity-7343518338599301120-rhD-?rcm=ACoAAAIGzIQBJurhY8wOgrgOI8TMc__UTmvGSUc)

* [Behind the Scenes with Red Canary’s Detection Engineering Team, May 2018](https://redcanary.com/blog/security-operations/detection-engineering/)
* [Kill SOC Toil, Do SOC Eng, Aug 2021](https://medium.com/anton-on-security/kill-soc-toil-do-soc-eng-50f29bfe52bd): "spending the remaining 50% on improving systems and detections with an “automate-first”, engineering mindset."
* [Future of SOC: More Security, Less Operations, Mar 2024](https://www.slideshare.net/slideshow/future-of-soc-more-security-less-operations/267023230)
* [Guide your SOC Leaders to More Engineering Wisdom for Detection(Part 9), Jul 2024](https://medium.com/anton-on-security/guide-your-soc-leaders-to-more-engineering-wisdom-for-detection-part-9-a46319bd362c)
* [The Detection Mindset, Mar 2025](https://danshiebler.com/2025-03-13-detection-mindset/)
* [My 2025 Detection Philosophy and the Pursuit of Immutable Artifacts, Mar 2025](https://detect.fyi/if-a-log-falls-in-the-siem-does-it-generate-an-alert-my-2025-detection-philosophy-5751c1a0ee56): If a log falls in the SIEM, does it generate an alert?
> Here’s what I believe separates a solid detection from the rest:
> * Balanced Scope: Neither overly specific nor too general. It captures intent, not just artifacts.
> * Resilience by Design: Built to withstand tool variations, obfuscation, and minor changes in attacker tradecraft.
> * SIEM-Aware Engineering: Designed with cost, cardinality, and performance in mind — because a well-crafted detection is worthless if it overloads your pipeline.
> * Technique-Focused: Anchored in the behavioral essence of a technique (more more known as “Immutable Artifacts.”) — not just chasing volatile IOCs or superficial strings.
* [Technique Analysis and Modeling, Mar 2025](https://medium.com/@vanvleet/technique-analysis-and-modeling-ffef1f0a595a): example Create or Modify System Process: Windows Service (T1543.003).
* [Z-Scoring Your Way to Better Threat Detection, Apr 2025](https://dispatch.thorcollective.com/p/z-scoring-your-way-to-better-threat-detection): use std deviation
* [Elastic Security Labs provides an under-the-hood look at its detection engineering processes, Apr 2025](https://www.elastic.co/blog/state-of-detection-engineering-at-elastic-2025)
* [Why is no one talking about maintenance in detection engineering? May 2025](https://medium.com/falconforce/why-is-no-one-talking-about-maintenance-in-detection-engineering-ebb5820564dc): ‘Even if it’s not broken, fix it.’
* [Detection Engineering Field Manual #1 - What is a Detection Engineer? Jun 2025](https://www.detectionengineering.net/p/detection-engineering-field-manual): role definition
* [Why You Should be Testing Your Detection Rules — Part 1, Jun 2025](https://v22bis.medium.com/why-you-should-be-testing-your-detection-rules-part-1-ab6f74fc5116): Unit testing and Linting, Integration Testing, End to End Testing
* [Detection Engineering: Practicing Detection-as-Code – Introduction – Part 1, Jul 2025](http://blog.nviso.eu/2025/07/08/detection-engineering-practicing-detection-as-code-introduction-part-1/): is/is not, DDLC. Follow-up repository, structure and branching, Azure DevOps repo, pipelines, validation (json, metadata, query...)
* [Scaling Detection-as-Code with Google SecOps: An MSSP’s Perspective, Jun 2025](https://www.googlecloudcommunity.com/gc/Community-Blog/Scaling-Detection-as-Code-with-Google-SecOps-An-MSSP-s/ba-p/915234), [Getting Started with Detection-as-Code and Google SecOps (Part 1 of 2), Jan 2024](https://security.googlecloudcommunity.com/community-blog-42/getting-started-with-detection-as-code-and-google-secops-part-1-of-2-3885)
* [Detection Engineers, what’s holding you back from moving from Atomic Detectors to Detection Models? Jun 2025 ](https://www.linkedin.com/posts/inode_threatintelligence-offensiveresearch-soc-activity-7336703364719636480-kZCh?rcm=ACoAAAIGzIQBJurhY8wOgrgOI8TMc__UTmvGSUc), https://github.com/inodee/threathunting-spl/blob/master/hunt-queries/powershell_qualifiers.md
* [Detection Engineering Framework](https://github.com/CiscoCXSecurity/Detection-Engineering-Framework)
* [Why You Should be Testing Your Detection Rules — Part 1, Jun 2025](https://v22bis.medium.com/why-you-should-be-testing-your-detection-rules-part-1-ab6f74fc5116)
* [Building a Security Operations Centre (SOC) > Detection Practices - NCSC, May 2022](https://www.ncsc.gov.uk/collection/building-a-security-operations-centre/detection/detection-practices)
* [Detecting the Most Popular MITRE Persistence Method – Registry Run Keys / Startup Folder, Jul 2025](https://www.nextron-systems.com/2025/07/29/detecting-the-most-popular-mitre-persistence-method-registry-run-keys-startup-folder/)
* [Detection Engineering: Practicing Detection-as-Code – Validation – Part 3, Aug 2025](https://blog.nviso.eu/2025/08/05/detection-engineering-practicing-detection-as-code-validation-part-3/)
* [Building a CI/CD Pipeline for RunReveal Detections: Detections-as-Code in Action, Aug 2025](https://blog.runreveal.com/runreveal-detection-cicd-guide/)
* [From Telemetry to Signals: Designing Detections with an Audience in Mind, Aug 2025](https://nasbench.medium.com/from-telemetry-to-signals-designing-detections-with-an-audience-in-mind-5faa3ec77b44)
* [The Fragile Balance: Assumptions, Tuning, and Telemetry Limits In Detection Engineering, Aug 2025](https://nasbench.medium.com/the-fragile-balance-assumptions-tuning-and-telemetry-limits-in-detection-engineering-a32ae6802995)
* [Scattered Spider: Detection Engineering Dilemma, Aug 2025](https://detecteam.com/blog/scattered-spider-detection-engineering-dilemma/)
* [Z-Score: A Metric for Measuring Detection Use Case Consolidation, Aug 2025](https://medium.com/@zied.ehg/z-score-a-metric-for-measuring-detection-use-case-consolidation-dbaa16897cbd): indicates how many distinct, logically separable use cases are included within a single consolidated rule.
* [A Detection Engineer's Guide to Cutting SIEM Costs, Sep 2025](https://www.monad.com/blog/a-detection-engineers-guide-to-cutting-siem-costs)

### Tools

* [SysInternals Process Monitor](https://learn.microsoft.com/en-us/sysinternals/downloads/procmon)
* [Atomic Red Team](https://www.atomicredteam.io), https://github.com/redcanaryco/atomic-red-team
* [detection.studio - Convert Sigma rules to SIEM queries, directly in your browser.](https://github.com/northsh/detection.studio)
* [A comprehensive AI-powered detection engineering platform for security teams to explore MITRE ATT&CK, build SIGMA rules, and visualize attack paths.](https://github.com/karmine05/DEF3ND)





[Carefully watch this video and witness how AI fails on detection engineering. 
1. The agent gets asked for finding encoded PowerShell commands but it returns a query that finds ALL PowerShell process executions without any filtering instead of only encoded commands. 

2. The agent then gets asked for filtering only admin users. This means any user with admin privileges. However, the agent just adds a filter on the username: "WHERE USER = 'admin'". 

How would you to spot these mistakes without having knowledge and skill? Are you going to let AI open the doors for attackers to breach your network?

There is a very slight chance that I'm completely wrong. That is:
- The table "anvilogic.gold.endpoint" is a special table that contains only encoded PowerShell command executions (it doesn't seem like it).
- The USER field contains privileges of the users, insted of the user name (less likely).](https://www.linkedin.com/posts/mehmetergene_as-a-former-practitioner-ive-always-been-activity-7321888302624641026-Ty7w?) - Anvilogic

### Rules

Generic
* https://github.com/SigmaHQ/sigma
* https://www.linkedin.com/posts/activity-7316076688566607873-p2s0
* https://rulehound.com/
* https://github.com/sublime-security/sublime-rules
* https://rulexplorer.io/detr/
* https://detections-digest.rulecheck.io/
* https://rules.emergingthreats.net/, https://www.openinfosecfoundation.org/rules/index.yaml and https://www.snort.org/downloads#rules
* https://github.com/SEKOIA-IO/Community/tree/main/sigma_rules
* https://blog.sekoia.io/xdr-detection-rules-at-scale/
* https://github.com/palantir/alerting-detection-strategy-framework
* https://github.com/BinaryDefense/ARC-Labs-Hunting-Queries


Vendor-based

* https://github.com/Azure/Azure-Sentinel/blob/master/Detections/readme.md
* https://github.com/CyberAutomationX/SecureAzCloud-Scripts/tree/main/KQL
* https://github.com/elastic/detection-rules
* https://github.com/splunk/security_content
* https://github.com/socfortress/Wazuh-Rules
* [Detection tuning – “Making the tuning process simple - one step at a time.”, Nov 2021](https://techcommunity.microsoft.com/blog/microsoftsentinelblog/detection-tuning-–-“making-the-tuning-process-simple---one-step-at-a-time-”/2919589)
* [Threat detection with Atomic Red Team and Azure Sentinel, Apr 2021](https://www.remotelycurious.net/post/threatlab/)
* [Sentinel for Purple Teaming, Oct 2024](https://medium.com/@iknowjason/sentinel-for-purple-teaming-183b7df7a2f4), [PurpleCloud - docs](https://www.purplecloud.network/), [PurpleCloud - github](https://github.com/iknowjason/PurpleCloud)
* [Improving automated Sentinel detection validation. Oct 2024](https://medium.com/@TimGroothuis/improving-automated-sentinel-detection-validation-02f91a9f4a21), [Azure Data Explorer Kusto emulator](https://learn.microsoft.com/en-us/azure/data-explorer/kusto-emulator-overview), <https://github.com/timtim589/KustainerValidation>
* [Automating Microsoft Sentinel Deployment with GitHub Actions, Aug 2025](https://sentinel.blog/automating-microsoft-sentinel-deployment-with-github-actions/)
* [Initial thoughts on @detectionsai.bsky.social have been pretty positive. Great platform for sharing detection and analytic content across a multiple of tools and languages (Sigma, KQL, Splunk, Yara, etc..)](https://bsky.app/profile/jhuntinfosec.com/post/3lwpbrmu7nc2h)

Linux
* https://www.elastic.co/security-labs/primer-on-persistence-mechanisms, https://www.elastic.co/security-labs/primer-on-persistence-mechanisms
[PANIX - Persistence Against *NIX](https://github.com/Aegrah/PANIX)
