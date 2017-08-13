
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
* [How to review and mitigate the impact of phishing attacks in Office 365, Mar 2016](https://blogs.technet.microsoft.com/office365security/how-to-review-and-mitigate-the-impact-of-phishing-attacks-in-office-365/)
* [How to fix a compromised (hacked) Microsoft Office 365 account, Dec 2015](https://blogs.technet.microsoft.com/office365security/how-to-fix-a-compromised-hacked-microsoft-office-365-account/), [O365-InvestigationTooling, Github](https://github.com/OfficeDev/O365-InvestigationTooling/)
* [Search for and delete email messages in your Office 365 organization - Admin Help](https://support.office.com/en-gb/article/Search-for-and-delete-email-messages-in-your-Office-365-organization-Admin-Help-3526fd06-b45f-445b-aed4-5ebd37b3762a)

How to do email

* [How to Not Send Corporate Emails?, Feb 2016](https://blog.rootshell.be/2016/02/29/phishing-or-not-phishing/)
* [97% of FTSE 250 Companies are Exposing Customers to Risks of Phishing Attacks, Mar 2016 - No DMARC](http://www.informationsecuritybuzz.com/study-research/97-of-ftse-250-companies-are-exposing-customers-to-risks-of-phishing-attacks/)
* [About Spam Filters, Mailchimp](http://kb.mailchimp.com/delivery/spam-filters/about-spam-filters)
* [Best practices for sending person-to-person email, Rackspace](https://support.rackspace.com/how-to/best-practices-for-sending-person-to-person-email/)
* [Marketing FAQs, SpamHaus](https://www.spamhaus.org/faq/section/Marketing%20FAQs)

Email server recall/removal (test before!!!)

* [Removing specific messages from your Exchange Server, Oct 2010](https://blogs.technet.microsoft.com/exchange/2010/10/27/removing-specific-messages-from-your-exchange-server/)
* [Office 365 Search and Delete mail using Powershell, Oct 2012](https://www.resdevops.com/2012/10/26/office-365-search-and-delete-mail-using-powershell/)
* [How To Delete Mails From Or To A Specific Email Address From Your Mail Queue (Postfix)](https://www.howtoforge.com/delete-mails-to-or-from-a-specific-email-address-from-postfix-mail-queue)
