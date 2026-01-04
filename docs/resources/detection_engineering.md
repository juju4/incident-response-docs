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
* Time/Work/Maintenance needed

Per log source
* Availability, latency, coverage, tampering per source/environment
* MITRE D3FEND

## hunt/logs check

ad dc
software distribution chain (wsus, sccm...)
monitoring systems (solarwinds, nagios...)
ai tools usage (web, purview...)
storage accounts, s3
sharepoint, dropbox, box...
whatsapp, telegram...
non-human identities, service accounts
code repo, cicd
exfil dns, email/smtp...
wifi bridge, rogue ap
networks logs, dhcp, switches...
VM vmware/hyperv, WSL evasion
browsers extensions
IDE/vscode extensions
VDI
[Be KVM, Do Fraud, Nov 2025](https://blog.grumpygoose.io/be-kvm-do-fraud-8ab523d26c9d)
[Do Tigers Really Change Their Stripes? May 2025](https://www.huntress.com/blog/do-tigers-really-change-their-stripes), [This is how to uncover infected hosts in seconds.](https://www.linkedin.com/posts/mauricefielenbach_cybersecurity-incidentresponse-dfir-activity-7395422365498699776-e0aR): "hunt for suspicious scheduled tasks executing binaries from %LOCALAPPDATA%"


## Resources

* [Detection Engineering Maturity Matrix](https://detectionengineering.io)
* [Attack Flow, MITRE CTID](https://ctid.mitre.org/projects/attack-flow/), https://github.com/center-for-threat-informed-defense/attack-flow
* [Summiting the Pyramid, MITRE CTID](https://center-for-threat-informed-defense.github.io/summiting-the-pyramid/)
* [Open Threat Informed Detection Engineering](https://github.com/OpenTideHQ), [OpenTIDE mirror](https://code.europa.eu/ec-digit-s2/opentide), [[2024 03 11] OpenTIDE 1.0 Release](https://code.europa.eu/groups/ec-digit-s2/opentide/-/wikis/Blog/%5B2024-03-11%5D-OpenTIDE-1.0-Release)
  * [Repository of TLP:CLEAR OpenTide Objects that can be shared within the community](https://github.com/OpenTideHQ/ShareTide)
  * [Rendered documentation for the ShareTide project](https://github.com/OpenTideHQ/WikiTide)
  * [WhitePaper](https://github.com/OpenTideHQ/.github/blob/main/profile/OpenTide%20White%20Paper.pdf)
* [infosecB/awesome-detection-engineering](https://github.com/infosecB/awesome-detection-engineering)
* [st0pp3r/awesome-detection-engineer](https://github.com/st0pp3r/awesome-detection-engineer/)
* [Detection Engineering Starter Pack](https://github.com/rfackroyd/detection-engineering-starter-pack)
* [Cyber Detection and Response knowledge dump](https://github.com/misterjulien/detection-and-response/wiki) - Unmaintained? Jul-Sep 2023
* [Detection knowledge repository – by Daniel Koifman](https://detections.xyz)
* [Explore supported frameworks and learn from their documentation. Learn how to write your own rules!](https://detectionstream.com/)
* <https://github.com/rabobank-cdc/DeTTECT>

* [On Detection: Tactical to Functional](https://posts.specterops.io/on-detection/home): 16 posts Jul 2022-Jan 2025
* [About Detection Engineering, Sep 2022](https://cyb3rops.medium.com/about-detection-engineering-44d39e0755f0)
* [Capturing Detection Ideas to Improve Their Impact, Oct 2022](https://cyb3rops.medium.com/capturing-detection-ideas-to-improve-their-impact-311cf4e1c7a8)
* [Security Analytics: How to rank use cases based on the "Quick Wins" approach? Apr 2017](https://detect.fyi/security-analytics-how-to-rank-use-cases-based-on-the-quick-wins-approach-d88748e5ece4)
* [How to prioritize a Detection Backlog? May 2024](https://detect.fyi/how-to-prioritize-a-detection-backlog-84a16d4cc7ae)
* [Baselines 101: Building Resilient, Frictionless SIEM Detections, Feb 2025](https://detect.fyi/baselines-101-building-resilient-frictionless-siem-detections-64dcbfb5afce): Detection Use Case: DCSync Attack & baseline periodic search
* [Tactical Tuning by Combinational Reduction, Apr 2025](https://detect.fyi/tactical-tuning-by-combinational-reduction-afc65cb0ef41)
* [Step-by-Step Guide: SOC Automation — SMB Threat Hunting & Incident Response Lab, Apr 2025](https://detect.fyi/step-by-step-guide-soc-automation-smb-threat-hunting-incident-response-lab-b6e48da2750d) with vmware, Windows AD, Kali Linux, Splunk SOAR Phantom and Enterprise
* [Can We Stop Documenting Our Detections? Apr 2025](https://detect.fyi/can-we-stop-documenting-our-detections-ded2201ec09b)
https://detect.fyi/do-you-know-your-detection-surface-8981289b0d25), https://github.com/gjGatos/detection_documentation_analysis
* [What is Detection as Code? How to implement Detection-as-Code, Apr 2025](https://medium.com/@tahirbalarabe2/what-is-detection-as-code-how-to-implement-detection-as-code-ae8e3bac22f7)
* [The Detection Opportunity Cost, May 2025](https://detect.fyi/the-detection-opportunity-cost-8cc0630a0266), [Without going through a hundred questions from yet another "Maturity Model" framework, how can you quickly assess how far you are when it comes to the #DetectionEngineering practice? Jul 2025](https://www.linkedin.com/posts/inode_the-detection-opportunity-cost-activity-7343518338599301120-rhD-?rcm=ACoAAAIGzIQBJurhY8wOgrgOI8TMc__UTmvGSUc)
* [The Detection Engineering Field Manual is a series of "quick-hit" posts about Detection Engineering, Security Engineering and Incident Response. These posts serve as a resource for security engineers to understand and orient the field of Detection quickly, and stem from years of practice and interviewing 100s of security people into my teams and organizations.](https://www.detectionengineering.net/s/field-manual)

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
* [Detection Engineering: Practicing Detection-as-Code – Versioning – Part 5, Sep 2025](https://blog.nviso.eu/2025/09/09/detection-engineering-practicing-detection-as-code-versioning-part-5/) on Sentinel
* [Detection Gaps: The Hidden Enemy in SOC Threat Hunting & Detection Engineering, Sep 2025](https://detect.fyi/detection-gaps-the-hidden-enemy-in-soc-threat-hunting-detection-engineering-764472ea975e)
* [Even if many plugins are fine, the bad ones are BAD, Sep 2025](https://dispatch.thorcollective.com/p/even-if-many-plugins-are-fine-the) - browsers extensions
* [The Present and Future of Managed Detection and Response, Sep 2025](https://detect.fyi/the-present-and-future-of-managed-detection-and-response-01a72088e6f6)
* [More than “plausible nonsense”: A rigorous eval for ADÉ, our security coding agent, Sep 2025](https://sublime.security/blog/more-than-plausible-nonsense-a-rigorous-eval-for-ade-our-security-coding-agent/): Detection Accuracy, Robustness, Economic Cost, [Evaluating LLM Generated Detection Rules in Cybersecurity, Sep 2025](https://arxiv.org/html/2509.16749v1)
* [Probabilities and low signal-to-noise in threat detection, Sep 2025](https://jvehent.org/2025/09/15/probability-signal-noise-detection.html)
* [The missing link in MDR. Spoiler, it starts with a Detection Engineering framework. Oct 2025](https://detect.fyi/the-missing-link-in-mdr-spoiler-it-starts-with-a-detection-engineering-framework-5f836347c92f)
* [Detection Engineering: Practicing Detection-as-Code – Monitoring – Part 7, Oct 2025](https://blog.nviso.eu/2025/10/07/detection-engineering-practicing-detection-as-code-monitoring-part-7/)
* [Detecting the Cisco ASA RCE Exploitation 5500-X series attack? Oct 2025](https://detecteam.com/blog/detecting-the-cisco-asa-rce-exploitation-5500-x-series-breach/)
* [Practical Resources for Detection Engineers. || Starters 🕵🏻 and Pro ||, Oct 2025](https://medium.com/@goodycyb/practical-resources-for-detection-engineers-starters-and-pro-219d04fcdd78)
* [Why following a standard alert output (schema)? Oct 2025](https://www.linkedin.com/posts/inode_soar-mcp-ai-activity-7382436862168117248-aHka)
* [Beyond the Alert: The Art and Science of Modern Detection Engineering. Oct 2025](https://medium.com/@7yr4n7/beyond-the-alert-the-art-and-science-of-modern-detection-engineering-1e0ebc76b59d)
* [Unveiling the GUARD framework to automate security detections at GitLab, Nov 2024](https://about.gitlab.com/blog/unveiling-the-guard-framework-to-automate-security-detections-at-gitlab/)
* [Critical Asset Analysis for Detection Engineering, Oct 2025](https://detect.fyi/critical-asset-analysis-for-detection-engineering-72b8051df149)
* [Detecting Abuse of OpenEDR’s Permissive EDR Trial: A Security Researcher’s Perspective, Oct 2025](https://kostas-ts.medium.com/detecting-abuse-of-openedrs-permissive-edr-trial-a-security-researcher-s-perspective-fc55bf53972c)
* [Adversary Tactics and Exploitation Paths in SharePoint Online, Aug 2025](https://guardz.com/blog/adversary-tactics-and-exploitation-paths-in-sharepoint-online/), [SharePoint Online Recon v1.1](https://github.com/guardzcom/security-research-labs/blob/main/SPO_Ext_Recon.ps1)
* [We Have To Talk About Service Accounts! Oct 2025](https://medium.com/@Debugger/we-have-to-talk-about-service-accounts-ab5f586ad444)
* [Building a Threat-Driven SIEM: From TTPs to Detection Priorities, Oct 2025](https://secopsathome.com/2025/10/06/building-a-threat-driven-siem-from-ttps-to-detection-priorities/)
* [The Hierarchy of SOC Needs, Oct 2025](https://buildingsecops.com/posts/the-hierarchy-of-soc-needs/): Alert Management, Detection Coverage, Threat Awareness, Threat Discovery, Posture Improvement
* [Technique Research Reports: Capturing and Sharing Threat Research, Nov 2025](https://medium.com/@vanvleet/technique-research-reports-capturing-and-sharing-threat-research-003c80ac9a4d)
* [Introducing the DRAPE Index: How to measure (in)success in a Threat Detection practice? Nov 2025](https://detect.fyi/introducing-the-drape-index-how-to-measure-in-success-in-a-threat-detection-practice-154fd977f731), <https://github.com/inodee/drape/>
* [Detection Quality Indicators: A Structured Approach to Better Detections, Nov 2025](https://1nf3rn0-h.medium.com/detection-quality-indicators-a-structured-approach-to-better-detections-ee8d93cc6ba2)
* [Rethinking Benign Alerts: A New Perspective for Detection Engineering, Dec 2025](https://detect.fyi/rethinking-benign-alerts-a-new-perspective-for-detection-engineering-525f701d66b7): "Breaking down the false TP/FP dichotomy in the SOC... However, we cannot wait until that happens, we must test our detections!"
* [Writing Battle-Tested Sigma Rules for Real-World ATT&CK Techniques, Dec 2025](https://medium.com/@sujalchauhan921/writing-battle-tested-sigma-rules-for-real-world-att-ck-techniques-e443ceda3496)
* [Threat Hunting step-by-step: Collecting Web Shells 🐚 using Ephemeral Baselines](https://detect.fyi/threat-hunting-step-by-step-collecting-web-shells-using-ephemeral-baselines-bb68d6476e9b): "Turning a KQL hunting query into a Defender detection rule to spot unusual web server processes using simple statistics."
* ?[The moment every SOC analyst dreads:You deploy a new detection rule. Within hours, 1,000+ alerts flood your queue. Your team is drowning in noise.](https://www.linkedin.com/posts/charles-ngor-17878886_the-moment-every-soc-analyst-dreads-you-ugcPost-7407458820991500288-0-aJ)
* [That's a very old view of sigma and disregard the fact the sigma is a format not limited to SigmaHQ which aims to be generic. [...] Dec 2025](https://www.linkedin.com/posts/nasreddinebencherchali_sigma-works-amazing-in-dfir-and-rapid-triage-activity-7407883437237293056-0t9i), [Why Venture Capital Is Betting Against Traditional SIEMs, Dec 2025](https://raffy.ch/blog/2025/12/17/why-venture-capital-is-betting-against-traditional-siems/): "The challenge is that many of these still sit atop the same primitives. For example, SIGMA is widely used as a community detection language, but it is fundamentally limited: it is mostly single-event, cannot express event ordering or causality, has no native temporal abstractions or entity-centric modeling, and cannot natively express thresholds, rates, cardinality, or statistical baselines."
* [How data science can boost your detection engineering maintenance and keep you from herding sheep, Dec 2025](https://medium.com/falconforce/how-data-science-can-boost-your-detection-engineering-maintenance-and-keep-you-from-herding-sheep-8713b7220776)

### Tools

* [SysInternals Process Monitor](https://learn.microsoft.com/en-us/sysinternals/downloads/procmon)
* [Atomic Red Team](https://www.atomicredteam.io), https://github.com/redcanaryco/atomic-red-team
* [detection.studio - Convert Sigma rules to SIEM queries, directly in your browser.](https://github.com/northsh/detection.studio)
* [A comprehensive AI-powered detection engineering platform for security teams to explore MITRE ATT&CK, build SIGMA rules, and visualize attack paths.](https://github.com/karmine05/DEF3ND)
* [AI-powered cybersecurity attack flow visualization tool using MITRE ATT&CK](https://github.com/davidljohnson/flowviz)
* [Analyzing Sentinel Data with Python, Oct 2025](https://www.techchat.blog/2025/10/19/analyzing-sentinel-data-with-python/): kql, pandas, sentinel notebook, spark notebook
* [ADX to Sentinel - Continuous Data Pipeline](https://github.com/LaurieRhodes/ADX-to-LogAnalytics-Scanner)
* [A cross-platform baselining, threat hunting, and attack surface analysis tool for security teams.](https://github.com/redcanaryco/surveyor)
* [UEBA in Microsoft Sentinel: Stop Wasting Time on Behavioral Analytics, Dec 2025](https://www.itprofessor.cloud/microsoft-sentinel-ueba/) "The problem isn't UEBA. The problem is everyone treats it like a fire-and-forget feature instead of what it actually is: a data science problem that requires baseline tuning, entity context, and honest assessment of whether your data is good enough to detect anything real."


* [Carefully watch this video and witness how AI fails on detection engineering. 
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
* [SOCPrime](https://socprime.com/)
* [DetectionStream, Unify detection engineering across Sigma, Nova, and beyond](https://detectionstream.com/)
* [SigmaHQ Quality Assurance Pipeline, Nov 2025](https://blog.sigmahq.io/sigmahq-quality-assurance-pipeline-d99eaba1760e), <https://github.com/SigmaHQ/sigma-rules-validator>, <https://github.com/NextronSystems/evtx-baseline>

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
* https://github.com/mattnovitsch/M365/wiki
* [Threat Hunting and Detection - KQL](https://github.com/Cyb3r-Monk/Threat-Hunting-and-Detection)
* [Elastic  Protections Artifacts](https://github.com/elastic/protections-artifacts) with rules
* <https://github.com/SlimKQL/Hunting-Queries-Detection-Rules/>
* [KQL Sentinel & Defender queries](https://github.com/HybridBrothers/Hunting-Queries-Detection-Rules/tree/main)
* [Ultimate Health Check For Microsoft Sentinel: Boost Security & Savings, Jun 2025](https://charbelnemnom.com/ultimate-health-check-for-microsoft-sentinel/)
* [Effective Tips To Manage Microsoft Defender XDR Tables, Oct 2025](https://charbelnemnom.com/manage-microsoft-defender-xdr-tables/)
* [Cutting Through The Noise: Reducing Fortinet Teardown Traffic In Microsoft Sentinel, Oct 2025](https://www.hanley.cloud/2025-10-16-Cutting-Through-the-Noise-Reducing-Fortinet-Teardown-Traffic-in-Microsoft-Sentinel/)
* [Defender XDR VS Microsoft Sentinel table changes, Oct 2025](https://hybridbrothers.com/posts/defender-xdr-vs-sentinel-table-changes/)
* [KQL Queries. Microsoft Defender, Microsoft Sentinel](https://github.com/alexverboon/Hunting-Queries-Detection-Rules)
* [Detecting Risky Password Reset Activity in Microsoft Sentinel, Dec 2025](https://beemermeup.github.io/LargeAmountOfPasswordResetsByUsers.html)
* [Automate the conversion and deployment of Sigma Rules to Grafana Alerting via GitHub Actions](https://github.com/grafana/sigma-rule-deployment)
* [Convert Sigma rules to Wazuh rules](https://github.com/theflakes/sigma_to_wazuh), [StoW - Sigma to Wazuh rule converter in GO](https://github.com/theflakes/StoW)

Linux
* [Linux Detection Engineering -  A primer on persistence mechanisms, Aug 2024](https://www.elastic.co/security-labs/primer-on-persistence-mechanisms)
* [PANIX - Persistence Against \*NIX](https://github.com/Aegrah/PANIX)

Macos
* [coreSigma: Expanding Sigma Detection for macOS, Nov 2025](https://nebulock.io/blog/coresigma-expanding-sigma-detection-for-macos)
