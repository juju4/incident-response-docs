
## Definition
Phishing is the attempt to obtain sensitive information such as usernames, passwords, and credit card details, often for malicious reasons, by disguising as a trustworthy entity in an electronic communication. [Wikipedia](https://en.wikipedia.org/wiki/Phishing)
This document will mostly go through phishing email but it can also be through other channel like text message, social media...

## Course of Action

* Review messsage
    * recover full email with headers. Some reporting service will require msg file.
    * confirm if malicious: sender, headers, content, urls... use sandbox to investigate any attachments or url.
    * check impact: how many people impacted based on subject, from, attachment...
* For internal email, issue a mass recall
* Report to 3rd party for blocking (mail systems, browsers, proxies... see references)
* Notify users of a phishing campaign
* Notify Email provider of service abuse
* Eventually, review suspicious system case
* Takedown of the fraudulent website
    * review legal template

## References

Report

* [Google Safebrowsing](https://safebrowsing.google.com/safebrowsing/report_phish/)
* [Report Suspected Phishing Sites, Symantec](https://submit.symantec.com/antifraud/phish.cgi)
* [Phishtank](https://www.phishtank.com/)
* [Report a Phishing URL, Netcraft](http://toolbar.netcraft.com/report_url)
* [Bluecoat Webpulse](https://sitereview.bluecoat.com/sitereview.jsp)
* [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/en-us/library/jj200769(v=exchg.150).aspx)
* [Report Phishing Sites, US-CERT](https://www.us-cert.gov/report-phishing)
* [Report Phishing, APWG](https://apwg.org/report-phishing/)
* [SIGNALER UN SITE..., PhishingInitiative](https://phishing-initiative.fr/contrib/)

Tools

* [Gone Phishing - Malware Triage For Everyone, Mary Ellen Kennel, 2014](https://drive.google.com/file/d/0B0CinYp-Pe4-dmgzMW1VRmtTSVU/view)
* [PhishReporter: PowerShell Module](https://msadministrator.com/2015/11/05/phishreporter-powershell-module/)
* [ENGINEERING SECURITY THROUGH UBER’S CUSTOM EMAIL IDS, Dec 2016](https://eng.uber.com/custom-email-ids/)

How to do email

* [How to Not Send Corporate Emails?, Feb 2016](https://blog.rootshell.be/2016/02/29/phishing-or-not-phishing/)
* [97% of FTSE 250 Companies are Exposing Customers to Risks of Phishing Attacks, Mar 2016 - No DMARC](http://www.informationsecuritybuzz.com/study-research/97-of-ftse-250-companies-are-exposing-customers-to-risks-of-phishing-attacks/)
* [About Spam Filters, Mailchimp](http://kb.mailchimp.com/delivery/spam-filters/about-spam-filters)
* [Best practices for sending person-to-person email, Rackspace](https://support.rackspace.com/how-to/best-practices-for-sending-person-to-person-email/)
* [Marketing FAQs, SpamHaus](https://www.spamhaus.org/faq/section/Marketing%20FAQs)
