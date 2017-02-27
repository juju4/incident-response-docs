
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

* [The WiFi Pineapple - Using Karma and SSLstrip to MiTM secure connections, sep 2013](https://scotthelme.co.uk/wifi-pineapple-karma-sslstrip/)
