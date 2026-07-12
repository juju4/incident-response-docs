# DNS Poisoning

## Definition

DNS Cache poisoning allow to alter the DNS response and as such hijack traffic of a domain.
DNSSec use can prevent this attack but it is still not fully deployed. DNSCrypt can help too.

## Course of Action

While uncommon currently (few known recent cases), impact is high be it on web, email or other services.
Detection requires monitoring of DNS servers used by customers, most probably not your own.

In case of incident

* contact impacted DNS provider to notify of the issue and support them in investigating and fixing it.
* alert customers of possible threat
  * use of https or other encrypted channel can help depending on how security-conscious users are and if HTTP Strict Transport Security (HSTS) is enforced. See Karma reference.

## References

* [March 2005 DNS Poisoning Summary compiled by Kyle Haugsnessi - incident](https://isc.sans.edu/presentations/dnspoisoning.html)
* [An Illustrated Guide to the Kaminsky DNS Vulnerability](http://unixwiz.net/techtips/iguide-kaminsky-dns-vuln.html)
* [DNS Cache Poisoning - The Next Generation, Mar 2011](https://www.secureworks.com/blog/dns-cache-poisoning)
* [Monitoring cache poisoning attacks, 2008 OARC Workshop](https://www.dns-oarc.net/files/workshop-2008/toyono.pdf)
* [VU#800113 Multiple DNS implementations vulnerable to cache poisoning, US-CERT](https://www.kb.cert.org/vuls/id/800113)
* [DNS Cache-Poisoning: New Vulnerabilities and Implications, or: DNSSEC, the time has come!, IETF, 2013](https://www.ietf.org/proceedings/87/slides/slides-87-saag-3.pdf)
* [Probable Cache Poisoning of Mail Handling Domains, CERT-CC, sep 2014](https://insights.sei.cmu.edu/cert/2014/09/-probable-cache-poisoning-of-mail-handling-domains.html)
* [DNSSEC Statistics, Internet Society](http://www.internetsociety.org/deploy360/dnssec/statistics/)
* [How to remove DNS Poisoning, PandaPow](https://pandapow.co/how-to/dns-poisoning/)
* [Introducing DNSCrypt](https://www.opendns.com/about/innovations/dnscrypt/)
* [Recursive DNS Server Fingerprint & DNS Hijacking, Apr 2017](https://recdnsfp.github.io/)

* [The WiFi Pineapple - Using Karma and SSLstrip to MiTM secure connections, sep 2013](https://scotthelme.co.uk/wifi-pineapple-karma-sslstrip/)

* [APT28 exploit routers to enable DNS hijacking operations, Apr 2026](https://www.ncsc.gov.uk/news/apt28-exploit-routers-to-enable-dns-hijacking-operations)
* [DNSSEC Failure in the .de Zone: Why bahn.de, spiegel.de and blackfort-tec.de Returned SERVFAIL, May 2026](https://blackfort-tec.de/en/insights/dnssec-denic-servfail-nsec3-de-zone), [DE ccTLD Issue Identified, May 2026](https://uptime.quad9.net/incident/888522), [Technical issue with .de domains resolved](https://blog.denic.de/en/technical-issue-with-de-domains-resolved/), [Analysis of the DNS outage on 5 May 2026, May 2026](https://blog.denic.de/en/analysis-of-the-dns-outage-on-5-may-2026/)
* [RIPE 92 - How many DNS queries?- Ondřej Surý, Jun 2026](https://www.isc.org/blogs/2026-how-many-queries/)
  > Prefer in-domain delegations where you can
  > If you must use a managed DNS provider, pick one or two, not four each across different four TLDs
  > Audit CNAME depth — every hop is a fresh chain
  > Keep PTR delegations boring: in-domain/in-bailiwick, glued
