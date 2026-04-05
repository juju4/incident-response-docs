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
* BlueTeamVillage Project Obsidian: [DC30](https://github.com/blueteamvillage/Project-Obsidian-DC30/tree/main/Threat-Hunting), [DC31](https://github.com/blueteamvillage/Project-Obsidian-DC31/tree/master/CTH), [DC33](https://github.com/blueteamvillage/dc33-presentations/tree/main/101-Content/ThreatHunting-101)
* [The RESPONDS Threat Hunting Framework, May 2025](https://www.themikewylie.com/the-responds-threat-hunting-framework/)

* [Elevate Your Threat Hunting with Elastic](https://www.elastic.co/security-labs/elevate-your-threat-hunting), [Building effective threat hunting and detection rules in Elastic Security, Aug 2025](https://www.elastic.co/blog/elastic-security-building-effective-threat-hunting-detection-rules)
* [Threat hunting in Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/hunting?tabs=defender-portal)
* [Threat Hunting with Splunk: Hands-on Tutorials for the Active Hunter](https://www.splunk.com/en_us/blog/security/hunting-with-splunk-the-basics.html)

* [Threat Hunting Metrics: The Good, The Bad and The Ugly, Aug 2023](https://kostas-ts.medium.com/threat-hunting-metrics-the-good-the-bad-and-the-ugly-d662907379b2)
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
* [How to build your first threat hunting hypothesis (in 5 simple steps) Feb 2026](https://www.linkedin.com/posts/khristina-filippova_socanalyst-threathunting-mitreattack-activity-7425524717131972608-25w2)
* <https://github.com/davidalonsod/Dalonso-Security-Repo/tree/main/Use%20Cases%20Threat%20Hunting>
* [When to Stop Hunting The Art of Knowing You’ve Looked Hard Enough. Mar 2026](https://dispatch.thorcollective.com/p/when-to-stop-hunting)
* [Cutting Through the Noise: A Technique-Based Approach to Hunting Web-Delivered Malware, Apr 2026](https://censys.com/blog/technique-based-approach-hunting-web-delivered-malware/) "Technique-based HTTP body hunting using Censys, combining behavioral signal stacking with iterative negation and body hash frequency analysis, can reliably surface untagged malicious infrastructure at scale. The methodology described in this report reduced the entire observable web to 42 actionable results with a confirmed malicious hit rate exceeding 20%."
