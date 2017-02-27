
## Definition
BGP Hijacking involve redirecting traffic of someone else network to your, either as termination, either as man-in-the-middle.
It is usually a mistake but could be malicious.

## Course of Action

It depends mostly what size the prefix is hijacked.
In BGP, the route which is elected depends on two factors

* the shortest path
* the smaller prefix

but on the Internet, it's uncommon to advertise anything smaller than /24, especially if you consider global routing table is over 512k which can lead to resource exhaustion on some equipments. Most large networks will not accept those advertising. Some will require a manual process.

First step is to contact operator at the source of the issue.
Without timely response and depending on impact, mitigation actions can be engaged.

If prefix is larger than /24

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
* [NANOG 63: BGP Route Hijacks, Andree Toonk, Feb 2015](https://blog.apnic.net/2015/02/11/nanog-63-bgp-route-hijacks/)
* [An Overview of BGP Hijacking By Zach Julian, Aug 2015](https://www.bishopfox.com/blog/2015/08/an-overview-of-bgp-hijacking/)
* [BGP Hijacking tag, Krebs on security](https://krebsonsecurity.com/tag/bgp-hijacking/)
* [BGP Hijack Detection, Tabi](https://github.com/ANSSI-FR/tabi)

* [Secure Cisco IOS BGP Template, Team Cymru](https://www.team-cymru.org/secure-bgp-template.html)
* [BGP Operations and Security, RFC7454](https://www.rfc-editor.org/rfc/rfc7454.txt)
* [Abuse Contact DB](https://www.abusix.com/contactdb)

* [RIPEStat](https://stat.ripe.net/)
* [Hurricane Electric BGP Toolkit](http://bgp.he.net/)
* [BGP Looking Glasses for IPv4/IPv6, Traceroute & BGP Route Servers](http://www.bgp4.as/looking-glasses)
* [BGP Looking Glass Database](http://www.bgplookingglass.com/)
