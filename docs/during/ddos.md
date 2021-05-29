
## Definition
Distributed Denial of Service targets avaibility of your system. It's usually triggered in two ways:

* Volumetric attack: saturate system and network resources.
* Application attack: exploit a configuration issue or software bug to make application unavailable.

DDoS can have many intents: revenge, blackmail (dd4bc, armada collective...), diversion and so on.

## Course of Action

Preparation is key and should be handle at all levels: public application and system, your network and the upstream provider.
Today's volumetric attack can saturated almost any company Internet link.

* Assess situation
    * which system is impacted 
    * is it an attack? no special press release, events? any application, system, network change?
    * what kind of attack
    * what automated countermeasures did
* Enable or Refine countermeasures
    * If on-site system are not enough, trigger upstream protection. Commercial services have emergency protection which can be onboarded fast but they usually come with a very high price when you are not a customer.
    * Did attacker change pattern. Depending on tool used, manual adaptation might be needed.
    * Any impact on legitimate traffic

Upstream protection usually involves a cleaning or scrubbing center either through DNS, either through BGP.
Protection should encompass all your points of presence. There is little interest to protect the front door if back one is open.

BGP options

* Blackhole: make target unavailable but the rest of your network will not be impacted anymore
    * usually easy
    * upstream provider can usually do without much preparation
* Cleaning center: cloud system will remove bad trafic and send back to you only the valid one
    * on advanced attacks, making distinction between good and bad trafic can be tricky. Be sure to be able to validate than (most of) legitimate trafic flows correctly.
    * use of world-wide cleaning center providers can be tricky from a privacy perspective. From a pure bandwidth capacity, it's hard to avoid. General recommendation is to use encryption and plan for applicative attacks on encryption channel at your own datacenter or site.
* Flowspec: "newcomer" in the field and depending on upstream network, you can send flowspec commands to create acl on edge router
    * flowspec is kind of a firewall on steroids but it will not help against advanced attacks.

Usual attacks channel are mostly amplification vectors: dns, ntp, snmp, ssdp, netbios, chargen, qotd, ripv1, portmap.
Outside of DNS and NTP, others have little reason to be used directly over Internet and should be filter. If an application requires one of them, it should be through a VPN.
For DNS and NTP, security conscious companies can limit corresponding traffic to a specific set of systems and filter out for others.


## References

* [THE HISTORY OF DDoS, 20 years of DDoS attacks](https://www.arbornetworks.com/the-history-of-ddos)
* [‘Booter Shells’ Turn Web Sites into Weapons, Aug 2012](https://krebsonsecurity.com/2012/08/booter-shells-turn-web-sites-into-weapons/)
* [Can You Afford $500 per Minute of Internet Downtime? $1000? More?](https://www.arbornetworks.com/blog/insight/can-you-afford-500-per-minute-of-internet-downtime-1000-more/)
* [Akamai quaterly State of the Internet](https://www.akamai.com/us/en/our-thinking/state-of-the-internet-report/global-state-of-the-internet-security-ddos-attack-reports.jsp)
* [Alert (TA14-017A) UDP-Based Amplification Attacks, US-CERT](https://www.us-cert.gov/ncas/alerts/TA14-017A)
* [TR-19 - UDP Protocols Security - Recommendations To Avoid or Limit DDoS reflection / amplification](https://www.circl.lu/pub/tr-19/)
* [Checklist To Prepare Yourself In Advance of a DDoS Attack, Mar 2013](https://www.whitehatsec.com/blog/checklist-to-prepare-yourself-in-advance-of-a-ddos-attack/)
* [BCP38](http://www.bcp38.info/index.php/Main_Page)
* [Not all attacks are equal: understanding and preventing DoS in web applications, Sep 2020](https://r2c.dev/blog/2020/understanding-and-preventing-dos-in-web-apps/)

* [Maximizing Firewall Availability, Team Cymru](http://www.cymru.com/gillsr/documents/maximizing-firewall-availability.htm)
* [Unwanted Traffic RemovalService (UTRS), Team Cymru](https://team-cymru.com/community-services/utrs/)
* [DDoS Mitigation Using BGP Flowspec, Justin Ryburn, Nanog63](https://nanog.org/sites/default/files/tuesday_general_ddos_ryburn_63.16.pdf)(https://forums.juniper.net/t5/Security-Now/DDoS-Mitigation-using-BGP-Flowspec/ba-p/268609)
* [FastNetmon detection tool](https://fastnetmon.com/)

CDN are not enough

* [CDN Networks as a Weapon for DDoS, Jan 2012](https://blog.radware.com/security/2012/01/cdn-networks-as-a-weapon-for-ddos/)
* [The Pentester’s Guide to Akamai, NCC Group, Mar 2013](https://dl.packetstormsecurity.net/papers/attack/the_pentesters_guide_to_akamai.pdf)
* [Can a CDN Stop Cyber-Attacks?, Feb 2015](https://blog.radware.com/security/2015/02/can-a-cdn-stop-cyber-attacks/)
* [CloudPiercer](https://cloudpiercer.org/)

Past DDoS

* [We’re standing up against a DDoS attack, Meetup, Mar 2014](http://blog.meetup.com/were-standing-up-against-a-ddos-attack/)
* [Linode: Back at last after ten days of hell, Jan 2016](http://www.theregister.co.uk/2016/01/04/linode_back_at_last_after_ten_days_of_hell/)
* [400Gbps: Winter of Whopping Weekend DDoS Attacks, Mar 2016](https://blog.cloudflare.com/a-winter-of-400gbps-weekend-ddos-attacks/)
* [the simultaneous DDoS are close to 1Tbps !, @olesovhcom](https://twitter.com/olesovhcom/status/778830571677978624)
* [The DDoS that didn't break the camel's VAC*](https://www.ovh.com/us/news/articles/a2367.the-ddos-that-didnt-break-the-camels-vac)
* [DDoS on Dyn Impacts Twitter, Spotify, Reddit, Oct 2016](https://krebsonsecurity.com/2016/10/ddos-on-dyn-impacts-twitter-spotify-reddit/)
* [Internet of Things, DDoS. How can we react as a community?](https://securityblob.blogspot.ca/2016/10/internet-of-things-ddos-how-can-we.html)
