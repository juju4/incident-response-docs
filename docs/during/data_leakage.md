
Data leakage is easily transform into data theft or data breach but it is not always millions of users information. Intellectual property, company results before public or technical details of the network are also sensitive data that can leak. Lost laptop is also a data leak especially if not using full-disk encryption.
Depending on country, regulation will enforce data breach notification.
If internal staff is suspected of leakage, extra carefulness should occur with Legal and HR involvement to ensure respect of both parties rights.

## Process

* Identify impact of the leak
    * on business
    * on operations
    * on any other parties
* Identify other locations of leaked data through search engines, pastebin, forums, Torrents...
* Identify internal locations through internal search engine, Data Leak Prevention (DLP) system
* If you can identify possible owners, try to represent how data has circulated
    * what's possible: email, web, removable media, printing, photo...
    * what's confirmed through logs
    * what is not visible in any way
    * Forensics investigation of owner systems is most probably needed but require Legal and HR approval in many case. Remember that in some countries (ex: Europe), you can't search private/personal folders without user consent or a reasonable suspicion (usually through automated scanner)
* If you can't identify internal owners
    * Third parties involved? Partners, visitors...
* Whose data is impacted?
    * Customers, current, old ones
    * Employees, current, old ones
    * Sales prospect
    * Partners
    * Others
* How can I tell if my environment has been compromised?
* Communicate appropriately depending on the data leak.
    * internally
    * externally: customers, partners, investors, regulators, law enforcement
    * Identify priority groups which should be worked early on
* Regularly evaluate impact of the incident and if it should be treated as a crisis

* If part of data extortion scheme and if known communication channel that can be watched in advance, monitor both communication channel (like onion page) and backend if possible. It may give you a headstart.

## References

* CERT Societe Generale, IRM-11-Information-Leakage
* EU GDPR, Data breach notification in 72h
* US SEC notification, after 4h that incident is assessed material
* [Five data leak nightmares, NetworkWorld, Jan 2008](http://www.networkworld.com/article/2289232/lan-wan/five-data-leak-nightmares.html)
* [Aligning with the GDPR: Data Breach Prevention and Notification, Apr 2018](https://www.trendmicro.com/vinfo/us/security/news/online-privacy/aligning-with-the-gdpr-data-breach-prevention-and-notification)

* Data identification
  * Credentials: https://github.com/trufflesecurity/trufflehog, https://github.com/gitleaks/gitleaks, https://github.com/Yelp/detect-secrets
  * [Presidio: Data Protection and De-identification SDK](https://microsoft.github.io/presidio/)

* [Report Regarding the November 16, 2020 Email Incident, Coil](https://coil.com/p/coil/Report-Regarding-the-November-16-2020-Email-Incident-/6udAFYucT)
* [Clothes retailer Fatface: Someone's broken in and accessed your personal data, including partial card payment details... Don't tell anyone'Strictly private and confidential'? SERIOUSLY? Mar 2021](https://www.theregister.com/2021/03/24/fatface/)
* [The "we suffered a security incident & your data is at risk" letters are pretty standard. New (to me, at least) is the "[redacted] confirmed from the intruder that any data that was accessed and copied has been destroyed." But, don't worry, "[redacted2] reports that it is actively monitoring via 3rd party experts and has found no trace of the data being available." The letter goes on to note how the "intruder was detected & expelled from the system." So: anonymous 3rd party has it totally under control, and we're taking the intruder at their word.](https://twitter.com/jckichen/status/1297307412299358208)
* [Every security vulnerability advisory should contain such a chapter:"How can I tell if my environment has been compromised?" good job @solarwinds https://solarwinds.com/trust-center/security-advisories/cve-2021-35211#FAQImage](https://twitter.com/cyb3rops/status/1414594673868480515)
* [We Can Do Better Than Free Credit Monitoring After a Breach, Nov 2024](https://www.darkreading.com/cyberattacks-data-breaches/we-can-do-better-than-free-credit-monitoring-after-breach)
