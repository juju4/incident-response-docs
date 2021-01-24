---
cover: assets/img/covers/security_incident.png
description: Checklist of actions for responding to a security incident at PagerDuty.
---
<div id="reviewed-dates">
  <span><strong>Last Reviewed:</strong> <abbr title="We recommend you include with this document the date you last reviewed your process.">YYYY-MM-DD</abbr></span>
  <span><strong>Last Tested:</strong> <abbr title="We recommend you include with this document the date you last tested your process.">YYYY-MM-DD</abbr></span>
</div>

!!! warning "Incident Commander Required"
     As with all major incidents at PagerDuty, security incidents will also involve an Incident Commander who will delegate the tasks to relevant responders. Tasks may be performed in parallel as assigned by the IC. Page one at the earliest possible opportunity `!ic page`.

!!! question "Not Sure it's a Security Incident?"
    Trigger the process anyway. It's better to be safe than sorry. The Incident Commander will make a determination on if response is needed.

## Checklist
Details for each of these items are available in the next section.

1. Observe
1. Orient
1. Decide
1. Act

---

## Attack Mitigation
Stop the attack as quickly as you can, via any means necessary. Shut down servers, network isolate them, turn off a data center if you have to. Some common things to try,

* Shutdown the instance from the provider console (do not delete or terminate if you can help it, as we'll need to do forensics).
* If you happen to be logged into the box you can try to,
    * Reinstate our default iptables rules to restrict traffic.
    * `kill -9` any active session you think is an attacker.
    * Change root password and update /etc/shadow to lock out all other users.
    * `sudo shutdown now`

## Cut Off Attack Vector
Identify the likely attack vectors and path/fix them so they cannot be re-exploited immediately after stopping the attack.

* If you suspect a third-party provider is compromised, delete all accounts except your own (and those of others who are physically present) and immediately rotate your password and MFA tokens.
* If you suspect a service application was an attack vector, disable any relevant code paths, or shut down the service entirely.

## Assemble Response Team
Identify the key responders for the security incident and keep them all in the loop. Set up a secure method of communicating all information associated with the incident. Details on the incident (or even the fact that an incident has occurred) should be kept private to the responders until you are confident the attack is not being triggered internally.

* Page an Incident Commander if not already done so. They will also appoint the usual incident command roles. The incident command team will be responsible for keeping documentation of actions taken, and for notifying internal stakeholders as appropriate.
* Give the project an innocuous codename that can be used for chats/documents so if anyone overhears they don't realize it's a security incident. (e.g. sapphire-unicorn).
* Start the voice call if not already in progress.
* Setup chat room using the codename of the incident.
* Invite all responders to the voice call and chat room.
    1. The **security team should always be included**.
    1. A representative for any affected services should be included.
    1. Executive stakeholders and legal counsel should be invited at earliest possible opportunity, but prioritize operational responders first.
* Do not communicate with anyone not on the response team about the incident until forensics have been performed. The attack could be happening internally.
* Prefix all emails, and chat topics with "Attorney Work Project".

## OODA Loop: Observe, Orient, Decide, Act [John Boyd]
Don't be rash or act too quickly! Security incident is grave concern but with inappropriate action, you might

* destroy evidence
* alert the attacker you are aware of his presence. It might trigger compromission vectors you are unaware of or destructive actions
* lose time and resources by non-prioritized actions

John Boyd, USAF Colonel developped the decision cycle nicknamed OODA loop

* Observe
* Orient
* Decide
* Act

It's repeated multiple times during an incident to react in the right manner at the actions of the opponent.

### **Observe**
Assess the situation.

Know the criticity of impacted assets. You will not react in the same way if your primary corporate website is impacted or if it's an obscure webserver.
Depending on known criticity, eventual customer concerns, action might be done faster. For example, if data leak transfer is discovered, some might choose to stop it directly. That might trigger attacker's backup plan. In the end, it's a business decision.

#### Passive assessment
On first discovery, you want to avoid alerting attacker meaning don't interact too soon with systems which are identified suspicious, at least not in a different way than usual.

* check network equipment (log, netflow, pcap...)
* check remote logs (syslog, performance...
* deploy extra sensors (taps, honeypots...) if you miss visibility on the impacted network zone
* review system criticity, backup and continuity plan existence and validity

#### Active assessment
At some point, you will decide to do full or partial host assessment

* collect live artifacts
    * memory
    * traffic or system like for example: tcpdump, sysdig
    * other tools: fastir, loki, ...
    * if virtualized or container, take full snapshot. Take care that container snapshot are NOT equivalent of a VM snapshot.
* collect disk image

These steps are essentials to identify 

1. Indicators of Compromise (IP, domain, hash...) and Indicator of Attacks (behavior like email calling browser calling powershell)
1. Any covert channel
1. Other compromised systems

1 and 2 will help to sweep Information system to ensure full scope of incident is evaluated before taking action.

### **Orient**
Analyze findings
It's recommended to use Analysis of Competing Hypotheses or ACH when establishing hypotheses vs evidence scenariis.

#### Identify Timeline of Attack
Work with all tools at your disposal to identify the timeline of the attack, along with exactly what the attacker did.

* Any reconnaissance the attacker performed on the system before the attack started.
* When the attacker gained access to the system.
* What actions the attacker performed on the system, and when.
* Identify how long the attacker had access to the system before they were detected, and before they were kicked out.
* Identify any queries the attacker ran on databases.
* Try to identify if the attacker still has access to the system via another back door. Monitor logs for unusual activity, etc.

#### Compromised Data
Using forensic analysis of log files, time-series graphs, and any other information/tools at your disposal, attempt to identify what information was compromised (if any),

* Identify any data that was compromised during the attack.
    * Was any data exfiltrated from a database?
    * What keys were on the system that are now considered compromised?
    * Was the attacker able to identify other components of the system (map out the network, etc)?
* Find exactly what customer data has been compromised, if any.

#### Disk Forensic Analysis
Depending on situation, this can happen during or after the incident.

* Take any read-only images you created, any access logs you have, and comb through them for more information about the attack.
* Identify exactly what happened, how it happened, and how to prevent it in future.
* Keep track of all IP addresses involved in the attack.
* Monitor logs for any attempt to regain access to the system by the attacker.

#### Assess Risk
Based on the data that was compromised, assess the risk to other systems.

* Does the attacker have enough information to find another way in?
* Were any passwords or keys stored on the host? If so, they should be considered compromised regardless of how they were stored.
* Any user accounts that were used in the initial attack should rotate all of their keys and passwords on every other system they have an account.


### **Decide**
Decide a course of action. Remember it can be step by step. OODA is a loop which will be repeated.
It can be adding new sensor, disrupt attacker communication while pursuing analysis or cut it.
As in chess or go, you should be able to foresee next attacker steps following your action.

### **Act**

#### Attack Mitigation
Stop the attack as quickly as you can, via any means necessary. Shut down servers, network isolate them, turn off a data center if you have to. Some common things to try,

* Shutdown the instance from the provider console (do not delete or terminate if you can help it, as we'll need to do forensics).
* If you happen to be logged into the box you can try to,
    * Re-instate our default iptables rules to restrict traffic.
    * `kill -9` any active session you think is an attacker.
    * Change root password, and update /etc/shadow to lock out all other users.
    * `sudo shutdown now`

#### Cut Off Attack Vector
Identify the likely attack vectors and path/fix them so they cannot be re-exploited immediately after stopping the attack.

* If you suspect a third-party provider is compromised, lock all accounts except your own (and those of others who are physically present) and immediately rotate your password and MFA tokens.
* If you suspect a service application was an attack vector, disable any relevant code paths, or shut down the service entirely.

#### Contain and/or Isolate Affected Instances
Any instances which were affected by the attack should be isolated from any other instances. As soon as possible, an image of the system should be taken and put into a read-only cold storage for later forensic analysis.

* Blacklist the IP addresses for any affected instances from all other hosts.
* Turn off and shutdown the instances immediately if you didn't do that to stop the attack.
* Take a disk image for any disks attached to the instances, and ship them to an off-site cold storage location. You should make sure these images are read-only and cannot be tampered with.

#### Apply Additional Mitigations
Start applying mitigations to other parts of your system.

* Rotate any compromised data.
* Restore from backup that you have validated as safe.
* Identify any new alerting which is needed to notify of a similar breach.
* Alert any IP addresses associated with the attack. (blocking is not that useful. As most of us know, compromised IP are cheap resources and turn-over is pretty fast. Advanced attacker will do one-time usage)
* Identify any keys/credentials that are compromised and revoke their access immediately.

## Communication

### Internal Communication
**Delegate to:** VP or Director of Engineering

Communicate internally only once you are confident that the attack was not sourced internally.

* Don't go into too much detail.
* Overview the timeline.
* Discuss mitigation steps taken.
* Follow up with more information once it is known.

### Liaise With Law Enforcement / External Actors
**Delegate to:** VP or Director of Engineering

Work with law enforcement to identify the source of the attack, letting any system owners know that systems under their control may be compromised, etc.

* Contact local law enforcement.
* Contact federal law enforcement (FBI for US).
* Contact National or partner CERT/CSIRT.
* Contact operators for any systems used in the attack, their systems may also have been compromised.
* Contact security companies to help in assessing risk and any PR next steps.
* Contact cyber insurance provider.
* Share with your partners and community through ISACs and CSIRTs to help them prevent or remediate similar attacks

### External Communication
**Delegate to:** Communication and Marketing Team

Depending on incident, you will have to communicate publicly at discovery of the incidents, a few days after or once it's closed. Many countries have now data breach notification law enforcing short delay (~1-5d) if PII are impacted. Also, some attacker will boast or push your data online.
Try to be as accurate as possible, stay factual, have a timeline of events, and know exactly what information was compromised, how it was compromised. 
You also should include any actions that customers need to take (reset password, MFA...).
Provide regular updates and if a mistake was done in the report, say it.

* Include the date in the title of any announcement so that it's never confused for a potential new breach.
* Don't say "We take security very seriously." It makes everyone cringe when they read it.
* Be honest, accept responsibility, and present the facts, along with exactly how we plan to prevent such things in future.
* Be as detailed as possible with the timeline.
* Be as detailed as possible in what information was compromised and how it affects customers. If we were storing something we shouldn't have been, be honest about it. It'll come out later and it'll be much worse.
* Don't name and shame any external parties that might have caused the compromise. It's bad form. (Unless they've already publicly disclosed, in which case we can link to their disclosure).
* Release the external communication as soon as possible, preferably within a few days of the compromise. The longer you wait, the worse it will be.
* If possible, get in touch with customers' internal security teams before the general public notice is sent.

---

## Communicating During an Incident

* Prefer voice call and Slack over any other methods.
* Avoid email, but if you absolutely need to for some reason,
    * Subject of emails should be "Attorney Work Project" and nothing else.
    * If the email chain has **ANY** contacts **not with the @pagerduty.com domain**, make sure your emails are encrypted.
* Do not use SMS to communicate about the incident.
    * The only exception is to tell someone to move to a more secure channel. e.g. "Please join Slack ASAP."
* Do not disseminate anything about the incident to those outside the response team until you have approval to do so.

---

## Additional Reading

* [Computer Security Incident Handling Guide - NIST SP800-61](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf) (NIST)
* [Incident Handler's Handbook - SANS ](https://www.sans.org/reading-room/whitepapers/incident/incident-handlers-handbook-33901) (SANS): Prepare > Identify > Contain > Remediate > Recover > Aftermath
* [Responding to IT Security Incidents - Microsoft](https://technet.microsoft.com/en-us/library/cc700825.aspx) (Microsoft)
* [Defining Incident Management Processes for CSIRTs: A Work in Progress - CMU CERT/CC](http://resources.sei.cmu.edu/library/asset-view.cfm?assetid=7153) (CMU)
* [Creating and Managing Computer Security Incident Handling Teams (CSIRTS) - First](https://www.first.org/conference/2008/papers/killcrece-georgia-slides.pdf) (CERT)
* [ENISA CSIRT Setting up](https://www.enisa.europa.eu/publications/csirt-setting-up-guide)
* Cheatsheets: [SANS](https://digital-forensics.sans.org/community/cheat-sheets), [Lenny Zeltser](https://zeltser.com/cheat-sheets/), [CERT Société Générale](https://cert.societegenerale.com/en/publications.html)...
* [Incident Response: Taking CSIRT modeling to the next level, Frode Hommedal](http://frodehommedal.no/presentations/first-tc-oslo-2015/#/slide-start)
* [The Remediation Ballet, Matt Linton, SANS Threat Hunting & Incident Response Summit 2016](files.sans.org/summit/Threat_Hunting_Incident_Response_Summit_2016/PDFs/The-Remediation-Ballet-Performing-the-Delicate-Dance-of-Clean-Up-Matt-Linton-Google.pdf)
* [Demisto public playbooks](https://github.com/demisto/content)
* [IncidentResponse.com playbooks](https://www.incidentresponse.com/playbooks/)
* [Cuckoo's Egg](https://en.wikipedia.org/wiki/The_Cuckoo%27s_Egg)
* [Analysis of Competing Hypotheses, CIA](https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/psychology-of-intelligence-analysis/art11.html) and [Psychology of Intelligence Analysis](https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/psychology-of-intelligence-analysis/PsychofIntelNew.pdf)
* [IR A-Z By: Mary Ellen Kennel](http://aboutdfir.com/incident-response-a-to-z/)
* [Incident Response Fundamentals Communication, Sep 2017](https://blogs.cisco.com/security/incident-response-fundamentals-communication)
* [Incident Response: Writing a Playbook, Apr 2018](https://medium.com/@magoo/incident-response-writing-a-playbook-773e7920f171)
