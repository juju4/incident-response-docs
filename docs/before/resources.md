It's critical as incident preparation to identify appropriate resources, be it persons, documentation and toolset
A contact page and card can be useful to summarize main company contacts for incident support, security or crisis.

## People

Most notably

* who is the owner (business) and the corresponding technical team of a system
* where do we find the resources to solve the incident
    * internal: if the operations team and owner team don't manage to fix issue in a defined time, who we escalate? expert separate team, SRE...
    * external: do we plan for 3rd party involvment? to support legacy system where we have less internal resources, to reduce overload on them
        * for a security incident, it's uncommon for a company to have a security team mastering everything. While a certain level of incident response is necessary, smaller team should plan for external support when they are overloaded or for some advanced skills like reverse engineering or mobile forensics. Higher management can also support a 3rd party either as an extra audit, either as public relationship.
        * external involvment should be anticipated as Non-Disclosure-Agreement(NDA) and other engagement conditions need to be reviewed
* how to escalate

## Process

You also should ensure that you have appropriate documentation and procedure to handle most incidents. It's a requirement to ensure consistency and avoid forgetting critical steps. Remember, procedures should be a guideline not a MUST-do every-step. Each incident has its peculiarities and adaptation is key.
Whatever you call them, procedure, cheatsheet, Standard Operating Procedures, Playbook, create them, maintain them, make new-hired staff review and amend them.
From a security incident perspective, examples procedure set:

* disk forensics
    * Acquisition and chain of evidence
    * Prefetch
    * Shimcache/Amcache
    * Timeline
* memory forensics
* suspicious url/document/files
    * sandbox
* malware analysis
* social media search
* online search

## Toolset

Having the right tool available with appropriate documentation and training can help a lot to solve an incident.
Examples

* Forensic station
* Jumpbag


## References

* Toyota Andon Cord: on production line, worker can pull the cord to ask team leader for support. if they can't solve issue in a short time, production line is stopped and whole team is involved to fix it.

* [SOPs in DFIR - Standard Operating Procedures](http://www.hecfblog.com/2017/02/sops-in-dfir.html)
