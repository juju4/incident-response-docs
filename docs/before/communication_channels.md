An essential point of any incident response is communication as most incident require collaboration of multiples persons and teams.

!!! note "Backup communication channel too!"
    Missing or losing your communication channel means you are back at shouting in the office which is a sure way to fail your incident response. There is usually too many people to inform and/or involve to work alone or in small group.


## Channels

At minimum, should be available

* paging/text message system
* an audiobridge
* an instant messaging system. to obtain quick status and transfer technical messages.

Ensure it's unique to each incident or with a protected access unless you want to risk an old employee or partner listening to current incidents.

Additionaly, you could have for incident internal communication:

* Document sharing system: for logs or any evidence of the case
    * It should support encryption for confidential incidents most notably the one impacting Personal Identifiable Informations
    * Have large capacity: logs...
* **Out of band channel**: in case, your normal system are suspected of being compromised or a major disaster (natural or not), a backup system should be available with differentiate access and if possible without risks of interception by an attacker
    * Phone: Signal, Whatsapp...
    * Instant Messaging: separate dormant system in the cloud

and for external communications:

* **Status web page**: internal and external, it can provide appropriate information to the targeted audience without disturbing work on incidents
    * External status should be available outside of your own network or ASN. For example, if you are unaccessible because of DDoS, an alternate information page is a good option. Examples:
        * Tumblr - [Meetup Service Outage](http://meetup.tumblr.com/post/78113362079/meetups-service-outage)
        * GitHub gist - [Basecamp was under network attack](https://gist.github.com/dhh/9741477)
* Twitter account(s): most notably support and security to push quick and regular update. Note that during an emergency people are less prone to check links [1] so do it sometimes but not in all tweets.
* Call-center: less applicable in technology sector but more traditional services like finance or retail. Incident information should be available to call center staff and/or through Interactive Voice Response systems.

## References

Example of status pages

* [GitHub Status Page](https://status.github.com/)
* [Google App Status](https://www.google.com/appsstatus#hl=fr&v=status)

Opensource tool

* [Cachet, open source status page system](https://cachethq.io/)

Recommendations

* [1] [Skip The URL When You Post In A Crisis, Readwrite, Aug 2012](http://readwrite.com/2012/08/29/skip-the-url-when-you-post-in-a-crisis/), [Determinants of information retweeting in microblogging, Internet Research](http://www.emeraldinsight.com/doi/abs/10.1108/10662241211250980)
