# Metrics and Quality assurance

Metrics are a requirement to evaluate impact and improvements over incidents
Those should help to identify easily which risk, platform or component is most often at stake and where improvements are more valuable.

## Recommendations

* Easy
* Automatable
* Context. Numbers should always include a narrative/story to help interpret them. Eventually have an annex that helps to interpret number.
* Fit for audience
  * Operations or Tactical
  * Management or Strategical

## Common metrics

* Number of incidents per severity, per hour of day or day of week, per application/platform or geography
* Mean-Time-To-Acknowledge
* Mean-Time-To-Repair (MTTR) or Contain or Fix, Cost of repair (hours)
* Mean-Time-Between-Failure (MTBF)
* Availability: either as uptime, either as successful requests (if using Error budget)
* Error budget (Google Site Reliability Engineering): one minus the availability target

## More targeted security metrics

* Dwell time: time between cause of incident/compromission and discovery
* Identified loss, money, time, staff involved, systems rebuilt
* Source of notification: automated system, manual, 3rd party
* Controls involved
* KillChain, MITRE ATT&CK
* Outcome: false-positive, true-positive, duplicate...
* Repetitive/Can be automated/Was automated?
* Consistency and Documentation (per process)
* Log source cost and detections
* [cost of data / number (or quality) of detection rules](https://www.linkedin.com/posts/secops-at-home_siem-siemdeployment-secops-activity-7388831993267912704-fH7-)
* Critical incidents
* Notable incidents (of interest but no major impact)

## Board metrics

This is usually a one-slider, short and crisp (or 3C, Clear, Concise, Consistent) with Top1-3 Business risks. It is ideally aligned to precise company risks register (ex: Ransomware, Data breach, Data leak of top project, Insider Threat, Compromise of financial systems, Supply-chain compromise...).

* Prepared for a major cyber incident
  * Last updated
    * Quarterly review - contacts, systems, tools verified against current reality
    * Named roles tied to current people - not job titles
  * Last tested
    * Escalation paths verified after-hours - not just in business hours
    * Retainer SLA tested - not assumed
  * Last executed
    * One live drill annually - not a tabletop, an actual activation
* Repeated security incidents in a department
* Above SLA/SLO response time
* How compare to peer organizations and sector
* Budget cost comparison: security investments, loss related, insurance cover, ROI of current program
* Controls most/least efficient
* Patching cadence grade
* Incident response grade
* Shadow IT

* Financial Risk Exposure
* Supply Chain or Third-party risks

What changed in how budget requests were presented:
* Technical controls replaced with business risk scenarios
* Every line item tied to a specific threat with estimated impact cost
* Board required to formally sign off on every denied item as accepted risk

## Check or Quality Assurance

Shewhart or Deming Wheel, ISO9001 and others
Plan-Do-*Check*-Act or PDCA

<https://en.wikipedia.org/wiki/PDCA#/media/File:PDCA_Process.png>

* Peer review and dual control is critical in security.
* Make it easy: random selection, google/o365 short form for quick evaluation
  * Appropriate handling, good communication, lessons learned...
* Share back: in ticketing, in team chat, to analyst...

Image: (<https://twitter.com/jhencinski/status/1254465280367083521>)

## References

* [Vocabulary for Event Recording and Incident Sharing (VERIS)](http://veriscommunity.net/)
* [Error Budgets and Risks, Marc Alvidrez, Google, SRECon 2015 ](https://www.usenix.org/conference/srecon15/program/presentation/alvidrez)
* [Computer Security Incident Handling Guide SP800-61r2, NIST](https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-61r2.pdf): 3.4.2 Using Collected Incident Data
* [Using Metrics to Mature Incident Response Capabilities, Mandiant, 2014 – DRAIN CVR](https://www.nist.gov/system/files/documents/2016/09/16/mandiant_rfi_response.pdf)
* [ETSI GS ISI 003 V1.2.1 (2018-01) Information Security Indicators (ISI); Key Performance Security Indicators (KPSI) to evaluate the maturity of security event detection](https://www.etsi.org/deliver/etsi_gs/isi/001_099/003/01.02.01_60/gs_isi003v010201p.pdf)
* [SEF-05: Incident Response Metrics, CSA Cloud Controls Matrix](https://csf.tools/reference/cloud-controls-matrix/version-3-0-1/sef/sef-05/)
* [Lessons learned from the Microsoft SOC, Part 1: Organization, Feb 2019](https://www.microsoft.com/security/blog/2019/02/21/lessons-learned-from-the-microsoft-soc-part-1-organization/): Time to acknowledge (TTA), Time to remediate (TTR), Incidents remediated (manually/with automation), Escalations between each tier
* [Use Case Applicability: How to better integrate Continuous Improvement into Security Monitoring, Jun 2019](https://github.com/d3sre/Use_Case_Applicability)
* [How do you measure #SOC quality?
1. ISO 2859-1 (#AQL) to determine sample size
2. #Python #Jupyter notebook to perform random selection
3. Check sheet to spot defects
4. Process runs every 24 hrs
5. (Digestible) #Metrics to improve
How'd we get there? Story in /thread, Apr 2020](https://twitter.com/jhencinski/status/1254465280367083521)
* [Hey SOC peeps, if you have to use a SINGLE metric to communicate #SOC value proposition to stakeholders (esp laypeople), what is it and how does it define value? Jul 2020](https://twitter.com/MalwareJake/status/1282762490758209537)
* [Performance metrics, part 1: Measuring SOC efficiency, Sep 2020](https://expel.io/blog/performance-metrics-measuring-soc-efficiency/): When do alerts show up? When do alerts show up? When do alerts show up?
* [Performance metrics, part 2: Keeping things under control, Oct 2020](https://expel.com/blog/performance-metrics-keeping-things-under-control/)
* [How to create (and share) good cybersecurity metrics, Mar 2021](https://expel.com/blog/how-to-create-and-share-good-cybersecurity-metrics/)
* [Performance metrics, part 3: Success stories, May 2021](https://expel.com/blog/performance-metrics-part-3-success-stories/)
* [How to measure SOC quality, Jun 2021](https://expel.com/blog/how-to-measure-soc-quality/)
* [11 Strategies of a World-Class Cybersecurity Operations Center, MITRE, Mar 2022](https://www.mitre.org/sites/default/files/2022-04/11-strategies-of-a-world-class-cybersecurity-operations-center.pdf): Strategy 10: Measure Performance to Improve Performance, references

* [PDCA (plan–do–check–act or plan–do–check–adjust)](https://en.wikipedia.org/wiki/PDCA)
* [ISO 2859-1:1999 Sampling procedures for inspection by attributes — Part 1: Sampling schemes indexed by acceptance quality limit (AQL) for lot-by-lot inspection](https://www.iso.org/standard/1141.html)
* [Here's your Michelin star (✨) for cooking SOC metrics to perfection. Mar 2026](https://www.linkedin.com/posts/rafal-kitab_soc-metrics-cookbook-ugcPost-7439800779848323072-37cJ): "1. Downgrade alert's severity 2. Reset SLA on escalation 3. include automation 4. selective sampling 5. fabricating a tech issue [...] These are the most common ways I've seen SOC metrics misrepresented, caught by actually reading SLA reports and validating them by hand (zero trust, baby)."
* [The only SOC workload numbers that are worth anything are alerts per analyst AFTER finetuning AND automation separated between in-house and MSSP SOCs. Mar 2026](https://www.linkedin.com/posts/rafal-kitab_the-only-soc-workload-numbers-that-are-worth-activity-7444715233413312512-UqO4)

* [TOP 10 CYBERSECURITY POSTURE METRICS EVERY CISO SHOULD USE, Aug 2023](https://clusis.com/wp-content/uploads/2023/08/top10cybersecurityposturemetricseverycisoshoulduse.pdf)
* [Board-Level Cybersecurity Metrics, Apr 2026](https://www.nacdonline.org/all-governance/governance-resources/governance-research/director-handbooks/2026-cyber-risk-oversight/cyber-risk-handbook-toolkit-2026/board-level-cybersecurity-metrics/)
* [A CISO was asked by the board whether the company was prepared for a major cyber incident... May 2026](https://www.linkedin.com/posts/marius-poskus_cybersecurity-ciso-leadership-activity-7455167778522701825-iBGx)
* [A CISO submitted a security budget request for $1.2M Endpoint detection. Identity governance. Third-party risk programme Denied "We need stronger business justification." May 2026](https://www.linkedin.com/posts/marius-poskus_cybersecurity-ciso-leadership-activity-7457704111908540417-RnRQ)
* [An AI agent closed 9,000 alerts in your SOC last month.  Every dashboard was green. Every KPI looked healthy.  That is not the number that should keep you awake at night. Jun 2026](https://www.linkedin.com/posts/csimonnet_the-best-thing-your-soc-did-last-quarter-activity-7471502380958748672-C0__), [The best thing your SOC did last quarter is not on the dashboard. An AI agent closed nine thousand alerts in your SOC last month. Every tile was green. That is not the number that should keep you up at night. The number that should is the one nobody logged: the sign](https://cyrilsimonnet.substack.com/p/the-best-thing-your-soc-did-last)
  * [SOC Capacity Modeling: How Many Alerts Can Your Team Really Handle? Dec 2025](https://www.prophetsecurity.ai/blog/soc-capacity-modeling-how-many-alerts-can-your-team-really-handle)
  > Step 1: Estimate your available capacity
  > Each analyst works an 8 hour shift, but you only get about 70% of that as productive time once you account for breaks, meetings, 1:1s, handoffs, and general noise. That gives you roughly 5.6 hours
  > Step 2: Look at your arrival rate
  > So, our arrival rate is: 100 alerts per day.
  > Step 3: Approximate your service time
  > 90% of alerts triaged and closed in about 5 minutes
  > 10% that turn into 20–25 minute investigations
  > Arrival rate = 100 alerts per day
  > Service time ≈ 7 minutes per alert
  > That means in this fictional setup, utilization is around 70%.
  > Step 4: Sit with what 70% really feels like
  > If the bottleneck in this system is clearly human capacity, what would it look like to exploit that constraint using AI agents to handle most of the alert triage?
  > Rewriting the capacity equation
  > The SOC analyst role shifts from “touch every alert” to “reviewer and decision-maker on the ones that matter.” You keep the same team, but you reclaim most of their time from repetitive triage and redirect it into investigations, threat hunting, and improving detections, without having to double headcount or spend more just to stand still.
* [Your SOC closes 10,000 cases a year.   It learns from zero of them. [...] Here’s the fix. The Feedback Loop Framework:](https://www.linkedin.com/posts/zosa-a13164192_your-soc-closes-10000-cases-a-year-it-activity-7474083661567426561-oMmP)
* [Show your success with true positive and false negative metrics. Especially with false negatives. Jun 2026](https://www.linkedin.com/posts/mehmetergene_showing-your-ai-success-based-on-false-positive-activity-7466507470404771841-lG1u)
