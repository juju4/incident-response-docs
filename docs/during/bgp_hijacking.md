
## Definition

BGP Hijacking involve redirecting traffic of someone else network to your, either as termination, either as man-in-the-middle.
It is usually a mistake but could be malicious.

## Course of Action

It depends mostly what size the prefix is hijacked.
In BGP, the route which is elected depends on two factors

* the shortest path
* the smaller prefix

but on the Internet, it's uncommon to advertise anything smaller than /24, especially if you consider global routing table is over 512k which can lead to resource exhaustion on some equipment. Most large networks will not accept those advertising. Some will require a manual process.

First step is to contact operator at the source of the issue.
Without timely response and depending on impact, mitigation actions can be engaged.
You can contact upstream providers (attacker's and yours) to ask them to stop route advertising. You should provide enough information to show that you are the legitimate owner.

Else, if prefix is larger than /24

* announce next smaller prefix to re-gain traffic
* monitor route propagation through your router, your upstream provider and other services like looking glass
* review if necessary

If prefix is smaller or equal than /24

* you can announce the same prefix or smaller but
    * shortest path wins
    * it will probably not be advertised very far except if your upstream provider is engaged.
* monitor route propagation through your router, your upstream provider and other services like looking glass
* review if necessary

Please note that you must know where to announce the route (which router) and to which system. Depending on your network space, inventory can be more or less complicate.

## References

* [YouTube Hijacking: A RIPE NCC RIS case study](https://www.ripe.net/publications/news/industry-developments/youtube-hijacking-a-ripe-ncc-ris-case-study)
* [Pakistan hijacks YouTube, Renesys/Din, Feb 2008](https://dyn.com/blog/pakistan-hijacks-youtube-1/)
* [Global Internet Routing Table Reaches 512k Milestone](https://blogs.cisco.com/sp/global-internet-routing-table-reaches-512k-milestone)
* [Using BGP data to find Spammers, Sep 2014](https://bgpmon.net/using-bgp-data-to-find-spammers/)
* [NANOG 63: BGP Route Hijacks, Andree Toonk, Feb 2015](https://blog.apnic.net/2015/02/11/nanog-63-bgp-route-hijacks/)
* [An Overview of BGP Hijacking By Zach Julian, Aug 2015](https://www.bishopfox.com/blog/2015/08/an-overview-of-bgp-hijacking/)
* [Best Practices to Combat Route Leaks and Hijacks, Jan 2017](https://blog.thousandeyes.com/best-practices-combat-route-leaks-hijacks/)
* [BGP / DNS Hijacks Target Payment Systems, Aug 2018](https://blogs.oracle.com/internetintelligence/bgp-dns-hijacks-target-payment-systems)
* [BGP Hijacking tag, Krebs on security](https://krebsonsecurity.com/tag/bgp-hijacking/)
* [August 30th 2020: Analysis of CenturyLink/Level(3) Outage](https://blog.cloudflare.com/analysis-of-todays-centurylink-level-3-outage/)
* [CenturyLink / Level 3 Outage Analysis, Aug 2020](https://blog.thousandeyes.com/centurylink-level-3-outage-analysis/)
* [At 2025-11-10 17:40:57 UTC Cloudflare for some unknown reason withdrew 2400:cb00:2049::/48, A prefix that contains a lot of DNS name servers for many customers (including bgp.tools) (see https://bgp.tools/prefix/2400:cb00:2049::/48#dns#dns )
Everything was back by 2025-11-10 18:00:30, but it's kinda wild that a prefix that contains .gov and loads of other name servers on it would just disappear like that.
This graph shows a selection of bgp.tools's session visibility second-by-second during the incident. Nov 2025](https://benjojo.co.uk/u/benjojo/h/7XtQ6k2vjx31G1w4n1)
* [Enforcing the First AS in BGP AS_PATHs, Jun 2026](https://blog.cloudflare.com/enforce-first-as-bgp/), <https://xcancel.com/spamhaus/status/2043708364941627683>
* [Is BGP boring? Well...it depends. But a few quick observations we've made recently:
1. We identified several /24 IP blocks with consistent RPKI/IRR flips between a Romanian ASN that's the largest VPN exit node in Europe, half a dozen Iranian ASNs, and another handful of shell ASNs in Europe and North America in order to launder transit from sanctioned IP space.
2. A new-ish ASN that's very much a problem child, including a recent favorite of Iranian threat actors, is nothing more than a well-known AS bucketing all its known problematic customers together, but still taking their money and providing them service. All original prefixes for the Problem Child originated at its parent ASN and migrated in the course of 3 hours.
3. In looking at other IP blocks showing up in recent-ish advisories, you can see clear IP prefix handoffs from an Iranian ASN to an Italian one while traffic clearly still originates from Iran. The BGP updates occur in the middle of the night for Italy - but a healthy morning period for Tehran.
4. This one, we published on - a Seychelles-based ASN under complete transit capture by one Russian organization and a second Slovakian one whose administration offices just happened to be in Moscow.
And these aren't even the coolest things we've seen lately. These are just the ones I'm okay vaguebooking about.
So no - BGP ain't boring. Much like DNS, it leads you to exactly where threat actors hang their hat.
Look deeper, look wider, punch bad guys where it hurts and make sure the bruises last.](https://masto.deoan.org/@neurovagrant/116704466257184677)
* [Telegram BGP hijack due to weird blackholing config, Jun 2026](https://anuragbhatia.com/post/2026/06/telegram-bgp-hijack-and-blackholing/)

Operations

* [Secure Cisco IOS BGP Template, Team Cymru](https://www.team-cymru.org/secure-bgp-template.html)
* [BGP Operations and Security, RFC7454](https://www.rfc-editor.org/rfc/rfc7454.txt)
* [Abuse Contact DB](https://www.abusix.com/contactdb)
* [BGP Hijack Detection, Tabi](https://github.com/ANSSI-FR/tabi)

Investigate

* [NANOG Mailing-list archive](https://mailman.nanog.org/pipermail/nanog/)
* [RIPEStat](https://stat.ripe.net/)
* [Hurricane Electric BGP Toolkit](http://bgp.he.net/)
* [BGP Looking Glasses for IPv4/IPv6, Traceroute & BGP Route Servers](http://www.bgp4.as/looking-glasses)
* [BGP Looking Glass Database](http://www.bgplookingglass.com/)
* [BGP Routing Table Analysis Reports](https://bgp.potaroo.net/)
* [BGP.tools](https://bgp.tools/)
* Twitter: https://twitter.com/thousandeyes, https://twitter.com/bgpmon
* [IHR BGP Monitor](https://www.ihr.live/en/bgp-monitor)
* [See through all BGP data with a monocle.](https://github.com/bgpkit/monocle)

