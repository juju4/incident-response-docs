# Hunting

> "Find Evil"
> "Threat hunting is the practice of proactively searching for cyber threats that are lurking undetected in a network".
> "Hunting is the discovery of malicious artifacts or detection methods *not accounted for* in passive monitoring capabilities"

Reviewing logs or code outside of an incident can be hunting.

## Process

TBD from your context and below resources.

* Hypothesis & Scope, Questions to answer
* Validate available data source, possible queries, known detections (internal & external)
* ...

## Metrics

* Frequency
* Escalation (Incidents, others)
* Environment and process documentation
* New detections
* New logs to be onboarded, onboarded

* Percent of hunts that produced actionable findings
* Time spent per hunt (measured by quality and outcome, not just effort)
* Data sources used vs. needed (highlighting visibility gaps)
* Repeatability of hunts (can findings or methods be reused?)
* Number of new or improved detections
* Policy or process improvements initiated from hunt findings
* Gaps identified and closed (e.g., visibility gaps, misconfigurations)
* Techniques currently covered compared to known TTPs relevant to your organization
* Alignment of data sources to attack surface (are you hunting where it matters?)
* Percentage of hunt topics derived from threat intelligence
* Average time from hypothesis to conclusion
* Number of hunts conducted per quarter
* Ratio of ad hoc vs. planned hunts
* Documentation completeness and reuse rate
* Number of team members leading hunts
* Contributions to internal knowledge bases
* Cross-team briefings or presentations generated from hunt findings
* Use digestible visuals (bar charts, trend lines).
* Highlight trends over time (not just hunt-by-hunt).
* Translate technical wins into business language.

## Example themes

To complement with latest news/threat

* LLMNR
* Webserver webshell
* File transfer tool compromise
* Browser extensions
* IDE extensions
* M365 Apps
* Azure Apps registrations

## References

* [Blue Team Handbook: SOC, SIEM, and Threat Hunting by Don Murdoch](http://www.blueteamhandbook.com/)

* [The ThreatHunting Project - sqrrl archive 2015-2018](https://www.threathunting.net/sqrrl-archive), [A Framework forCyber Threat Hunting](https://www.threathunting.net/files/framework-for-threat-hunting-whitepaper.pdf) - Threat Hunting loop
* [TaHiTI Threat Hunting Methodology, 2018](https://www.betaalvereniging.nl/en/safety/tahiti/)
* [OTHF Open Threat Hunting Framework 2022-2023](https://github.com/TactiKoolSec/OTHF)
* [Introducing the PEAK Threat Hunting Framework, Apr 2023](https://www.splunk.com/en_us/blog/security/peak-threat-hunting-framework.html): Prepare, Execute, and Act with Knowledge
* [Open Threat Informed Detection Engineering is a comprehensive framework to enable Threat & Detection Modelling and Detection-as-Code in a unified workflow](https://github.com/OpenTideHQ)
* F3EAD: Find, Fix, Finish, Exploit, Analyze and Disseminate. [Intelligence Concepts — F3EAD, Mar 2015](https://sroberts.io/posts/intelligence-concepts-f3ead/)
* [How to start Threat Hunting (even if your team is small!), Jul 2020](https://svch0st.medium.com/how-to-start-threat-hunting-even-if-your-team-is-small-a31e656b8ba1), [Library of threat hunts to get any user started!](https://github.com/svch0stz/TheThreatHuntLibrary) (unmaintained)
* BlueTeamVillage Project Obsidian: [DC30](https://github.com/blueteamvillage/Project-Obsidian-DC30/tree/main/Threat-Hunting), [DC31](https://github.com/blueteamvillage/Project-Obsidian-DC31/tree/master/CTH), [DC33](https://github.com/blueteamvillage/dc33-presentations/tree/main/101-Content/ThreatHunting-101)
* [The RESPONDS Threat Hunting Framework, May 2025](https://www.themikewylie.com/the-responds-threat-hunting-framework/)
* [A community-driven repository for threat hunting ideas, methodologies, and research that serves as a central gathering place for hunters to share knowledge, collaborate on techniques, and advance the field of threat hunting.](https://github.com/THORCollective/HEARTH/tree/main)

* [DFRWS US 2022  - Workshop: Velociraptor: Digging Deeper (4 Hours)](https://docs.velociraptor.app/presentations/2022_dfrws_us/#workshop-velociraptor-digging-deeper-4-hours)
* [Using Velociraptor to Detect and Hunt for Affected Systems: Unknown Malware Analysis, Feb 2025](https://daniyyell.com/threat hunting/tools/malware analysis/Using-Velociraptor-to-Detect-and-Hunt-for-Affected-Systems-Unknown-Malware-Analysis/)
* [Elevate Your Threat Hunting with Elastic](https://www.elastic.co/security-labs/elevate-your-threat-hunting), [Building effective threat hunting and detection rules in Elastic Security, Aug 2025](https://www.elastic.co/blog/elastic-security-building-effective-threat-hunting-detection-rules)
* [Threat hunting in Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/hunting?tabs=defender-portal)
* <https://github.com/davidalonsod/Dalonso-Security-Repo/tree/main/Use%20Cases%20Threat%20Hunting> (Sentinel)
* [Threat Hunting with Splunk: Hands-on Tutorials for the Active Hunter](https://www.splunk.com/en_us/blog/security/hunting-with-splunk-the-basics.html)

* [Threat Hunting Hypothesis Examples: Five Hunts to Start Out, May 2022](https://www.intel471.com/blog/threat-hunting-hypothesis-examples-five-hunts-to-start-out)
* [5 Threat Hunting Tips from a Seasoned Hunt Team, May 2022](https://www.intel471.com/blog/5-threat-hunting-tips-from-a-seasoned-hunt-team)
  > Threat Hunting Tips #1 - Know what is normal for your environment, then you'll be able to spot the abnormal easier.
  > Threat Hunting Tips #2 - When building a hunt, start general and work your way to specific based on your hypothesis. By doing this it creates context and understanding of what it is you are looking at in your environment
  > Threat Hunting Tips #3 - Sometimes better to hunt on things you understand and know and then pivot vs hunting on things outside your expertise and trying to pivot to something you know
  > Threat Hunting Tips #4 - Not every hypothesis will be successful and sometimes it might fail. But don't be discouraged, go back and test again!
  > And finally... #5 - Knowing your toolset and its data capabilities is just as important as executing your hunt. False Negatives lurk around every corner if you aren’t validating the expected data even exists in your tools.
* [50 Threat Hunting Hypothesis Examples, Mar 2023](https://www.intel471.com/blog/50-threat-hunting-hypothesis-examples)
* [Art of the Hunt: Building a Threat Hunting Hypothesis List, May 2023](https://www.intel471.com/blog/art-of-the-hunt-building-a-threat-hunting-hypothesis-list)
* [Threat Hunting Metrics: The Good, The Bad and The Ugly, Aug 2023](https://kostas-ts.medium.com/threat-hunting-metrics-the-good-the-bad-and-the-ugly-d662907379b2)
* [From Instinct to Insight: Why Metrics Are Essential to Threat Hunting Success, May 2025](https://www.splunk.com/en_us/blog/security/from-instinct-to-insight-why-metrics-are-essential-to-threat-hunting-success.html), [Threat Hunting Metrics: The Framework That Proves ROI, May 2026](https://www.youtube.com/watch?v=zbDrWI4zMWE)
* [This is my advice for people getting started in Threat Hunting and building out metrics for a program: Focus on Outcomes, Sep 2025](https://www.linkedin.com/posts/william-t_that-is-my-advice-for-people-getting-started-activity-7376004202445160448-cmqw)
* [Baseline Bonanza: Ten Baseline Hunts You Should Do (and How to Do Them), Sep 2025](https://dispatch.thorcollective.com/p/baseline-bonanza-ten-baseline-hunts)
* [I really believe threat hunting is one of the areas where AI actually makes SecOps better. Nov 2025](https://www.linkedin.com/posts/filipstojkovski_i-really-believe-threat-hunting-is-one-of-activity-7394781860825825281-r5fI)
* [Threat Hunting 🏹 , Nov 2025](https://www.linkedin.com/posts/jay-kerai-cyber_thruntandchill-security-defender-activity-7395430371581964288-oczZ)
> Threat Hunting should be:
> - TTP (Tactics Techniques or Procedures) or IOA (Indicator of Attack) based (you will find many attack chains have crossover. Having some good detection will pay itself off in future)
> - Feed into Preventative controls (it is fairly common to find potential hardening/actions to take post a hunt)
> - Feed into new detection rules (fidelity test)
> - Not just be limited to a threat hunting team, SOC analysts should get involved too (remember they are the first on the scene to alerts)
> - Not get too caught up in Attribution of attackers, Attackers can "share" TTPs (I have already proved attribution can be spoofed in an earlier post, using TTPs casts your net wider already)
> - Work with other technical teams to understand what normal business operations are to sift out BAU from logs.
* [Add Punycode to your Threat Hunting Routine. Punycode patterns in DNS queries make excellent hunting opportunities. Jan 2026](https://isc.sans.edu/diary/Add%20Punycode%20to%20your%20Threat%20Hunting%20Routine/32640)
* [Hunting in Microsoft Sentinel: What Hunting Actually Is and Why You Need It, Jan 2026](https://www.itprofessor.cloud/hunting-microsoft-sentinel/)
* [How to build your first threat hunting hypothesis (in 5 simple steps), Feb 2026](https://www.linkedin.com/posts/khristina-filippova_socanalyst-threathunting-mitreattack-activity-7425524717131972608-25w2)
* <https://github.com/davidalonsod/Dalonso-Security-Repo/tree/main/Use%20Cases%20Threat%20Hunting>
* [When to Stop Hunting The Art of Knowing You’ve Looked Hard Enough. Mar 2026](https://dispatch.thorcollective.com/p/when-to-stop-hunting)
* [Cutting Through the Noise: A Technique-Based Approach to Hunting Web-Delivered Malware, Apr 2026](https://censys.com/blog/technique-based-approach-hunting-web-delivered-malware/) "Technique-based HTTP body hunting using Censys, combining behavioral signal stacking with iterative negation and body hash frequency analysis, can reliably surface untagged malicious infrastructure at scale. The methodology described in this report reduced the entire observable web to 42 actionable results with a confirmed malicious hit rate exceeding 20%."
* [Three New Ways to Use HEARTH What Can I Hunt?, Coverage Map, and Context Graph. Apr 2026](https://dispatch.thorcollective.com/p/three-new-ways-to-use-hearth), <https://hearth.thorcollective.com/>
* [Threat Hunting Case Study: FileFix, Jun 2026](https://www.intel471.com/blog/threat-hunting-case-study-filefix)
