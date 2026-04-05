
## Definition
Phishing is the attempt to obtain sensitive information such as usernames, passwords, and credit card details, often for malicious reasons, by disguising as a trustworthy entity in an electronic communication. [Wikipedia](https://en.wikipedia.org/wiki/Phishing)
This document will mostly go through phishing email but it can also be through other channel like text message, social media...

## Course of Action

* Review messsage
    * recover full email with headers. Some reporting service will require msg file. Note some phishing awareness campaign use X-PHISH header to be identified.
    * confirm if malicious: sender, headers, content, urls... use sandbox to investigate any attachments or url.
    * check impact: how many people impacted based on subject, from, attachment...
* For internal email, issue a mass recall
* Report to 3rd party for blocking (mail systems, browsers, proxies... see references)
* Notify users of a phishing campaign
* Notify Email provider of service abuse
* Eventually, review suspicious system case
* Takedown of the fraudulent website or incriminated email.
    * review legal template
* Validate security coverage of targeted users and in general and possibly attacked targets (O365, Cloud, Password reset...)
* Push repeated victims to use phish-resistant MFA (FIDO2 - yubikey, passkey...) and disable less secure MFA like phone/sms

## References

* [Security Tip (ST04-014) Avoiding Social Engineering and Phishing Attacks](https://us-cert.cisa.gov/ncas/tips/ST04-014)
* [CERT Societe Generale, IRM-13-Phishing](https://github.com/certsocietegenerale/IRM/blob/master/EN/IRM-13-Phishing.pdf)
* [Online Brand Protection, Mar 2020](https://www.digitalshadows.com/blog-and-research/the-complete-guide-to-online-brand-protection/)
* [Keep Office 365 safe from BEC when you are an SME](https://www.comae.com/posts/2020-04-12_keep-office-365-safe-from-bec-when-you-are-an-sme/)
* [BEC Taxonomy: A Proofpoint Framework, Apr 2021](https://www.proofpoint.com/us/blog/threat-insight/bec-taxonomy-proofpoint-framework)
* [BEC Taxonomy: Invoice Fraud, May 2021](https://www.proofpoint.com/us/blog/threat-insight/bec-taxonomy-invoice-fraud)
* [BEC Taxonomy: Payroll Redirects, May 2021](https://www.proofpoint.com/us/blog/threat-insight/bec-taxonomy-payroll-redirects)
* [Simple Email Reputation](https://emailrep.io)
* [Business-Email-Compromise-Guide, PwC, Feb 2021](https://github.com/PwC-IR/Business-Email-Compromise-Guide)
* [Phishing investigation, Microsoft IR playbook](https://docs.microsoft.com/en-us/security/compass/incident-response-playbook-phishing)
* [Playbook - Phishing, Incidentresponse.com](https://www.incidentresponse.com/playbooks/phishing)
* [Playbook phishing, Counteractive](https://github.com/counteractive/incident-response-plan-template/blob/master/playbooks/playbook-phishing.md)
* [Phishing Playbook, Syntax IR](https://gitlab.com/syntax-ir/playbooks/-/tree/main/IRP-Phishing)
* <https://github.com/MISP/misp-playbooks/blob/main/misp-playbooks/pb_investigating_phishing_websites.ipynb>, <https://misp.github.io/misp-playbooks/misp-playbooks/pb_investigating_phishing_websites-with_output.html>

Report

* [Google Safebrowsing](https://safebrowsing.google.com/safebrowsing/report_phish/)
* [I would like to report a Gmail user who has sent messages that violate the Gmail Program Policies and/or Terms of Use.](https://support.google.com/mail/contact/abuse?hl=en)
* [Report Suspected Phishing Sites, Symantec](https://submit.symantec.com/antifraud/phish.cgi)
* [Phishtank](https://www.phishtank.com/)
* [Report a Phishing URL, Netcraft](http://toolbar.netcraft.com/report_url)
* [Bluecoat Webpulse](https://sitereview.bluecoat.com/sitereview.jsp)
* [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/en-us/library/jj200769(v=exchg.150).aspx)
* [Report Phishing Sites, US-CERT](https://www.us-cert.gov/report-phishing)
* [Report Phishing, APWG](https://apwg.org/report-phishing/)
* [SIGNALER UN SITE..., PhishingInitiative](https://phishing-initiative.fr/contrib/)
* [Report unsafe site, Microsoft](https://www.microsoft.com/en-us/wdsi/support/report-unsafe-site)
* [Easily Report Phishing and Malware, Decent Security](https://decentsecurity.com/malware-web-and-phishing-investigation/)
* [Filing a Complaint with the IC3](https://www.ic3.gov)
* [ICANN Contractual Compliance Complaint Forms](https://icannportal.force.com/compliance/s/abuse-domain)

Takedown

* [InfoSec Guide: Taking Down Fraudulent Domains (Part 2), Mar 2018](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/infosec-guide-taking-down-fraudulent-domains)

Tools

* [Gone Phishing - Malware Triage For Everyone, Mary Ellen Kennel, 2014](https://drive.google.com/file/d/0B0CinYp-Pe4-dmgzMW1VRmtTSVU/view)
* [PhishReporter: PowerShell Module](https://msadministrator.com/2015/11/05/phishreporter-powershell-module/)
* [ENGINEERING SECURITY THROUGH UBER’S CUSTOM EMAIL IDS, Dec 2016](https://eng.uber.com/custom-email-ids/)
* [How to review and mitigate the impact of phishing attacks in Office 365, Mar 2016](https://blogs.technet.microsoft.com/office365security/how-to-review-and-mitigate-the-impact-of-phishing-attacks-in-office-365/)
* [How to fix a compromised (hacked) Microsoft Office 365 account, Dec 2015](https://blogs.technet.microsoft.com/office365security/how-to-fix-a-compromised-hacked-microsoft-office-365-account/), [O365-InvestigationTooling, Github](https://github.com/OfficeDev/O365-InvestigationTooling/)
* [Search for and delete email messages in your Office 365 organization - Admin Help](https://support.office.com/en-gb/article/Search-for-and-delete-email-messages-in-your-Office-365-organization-Admin-Help-3526fd06-b45f-445b-aed4-5ebd37b3762a)
* [urlquery](https://urlquery.net/)
* [urlscan.io](https://urlscan.io/)
* [Mxtoolbox Email Headers analysis](https://mxtoolbox.com/EmailHeaders.aspx)

How to do email

* [How to Not Send Corporate Emails?, Feb 2016](https://blog.rootshell.be/2016/02/29/phishing-or-not-phishing/)
* [97% of FTSE 250 Companies are Exposing Customers to Risks of Phishing Attacks, Mar 2016 - No DMARC](http://www.informationsecuritybuzz.com/study-research/97-of-ftse-250-companies-are-exposing-customers-to-risks-of-phishing-attacks/)
* [How to Send Customer Emails That Don’t Look Like Phishing, Dec 2020](https://zeltser.com/customer-emails-like-phishing/)
* [About Spam Filters, Mailchimp](http://kb.mailchimp.com/delivery/spam-filters/about-spam-filters)
* [Best practices for sending person-to-person email, Rackspace](https://support.rackspace.com/how-to/best-practices-for-sending-person-to-person-email/)
* [Marketing FAQs, SpamHaus](https://www.spamhaus.org/faq/section/Marketing%20FAQs)

Email server recall/removal (test before!!!)

* [Removing specific messages from your Exchange Server, Oct 2010](https://blogs.technet.microsoft.com/exchange/2010/10/27/removing-specific-messages-from-your-exchange-server/)
* [Office 365 Search and Delete mail using Powershell, Oct 2012](https://www.resdevops.com/2012/10/26/office-365-search-and-delete-mail-using-powershell/)
* [How To Delete Mails From Or To A Specific Email Address From Your Mail Queue (Postfix)](https://www.howtoforge.com/delete-mails-to-or-from-a-specific-email-address-from-postfix-mail-queue)

Misc

* [Keep Office 365 safe from BEC when you are an SME, Apr 2020](https://www.comae.com/posts/keep-office-365-safe-from-bec-when-you-are-an-sme/)
* [BEC Response Guide Tips for Responding to Business Email Compromise Incidents, Dec 2020](https://iheartmalware.medium.com/bec-response-guide-tips-for-responding-to-business-email-compromise-incidents-fbb6744e056a)
* [Improving the phishing triage process: Keeping our analysts (and our customers) sane, Jan 2021](https://expel.io/blog/improving-the-phishing-triage-process/). Is this email benign or malicious? Impersonation, Intent, Action
* [3 OAuth TTPs Seen This Month — and How to Detect Them with Entra ID Logs, Nov 2025](https://www.wiz.io/blog/recent-oauth-attacks-detection-strategies)
* [DNS Uncovers Infrastructure Used in SSO Attacks, Dec 2025](https://blogs.infoblox.com/threat-intelligence/dns-uncovers-infrastructure-used-in-sso-attacks/)
* [SpyCloud Data Shows Corporate Users 3x More Likely to Be Targeted by Phishing Than by Malware, Dec 2025](https://latesthackingnews-com.cdn.ampproject.org/c/s/latesthackingnews.com/2025/12/04/spycloud-data-shows-corporate-users-3x-more-likely-to-be-targeted-by-phishing-than-by-malware/amp/): "The company tracked a 400% year-over-year increase in successfully phished identities, with nearly 40% of the 28+ million recaptured phished records containing a business email address – compared to just 11.5% in recaptured malware data. The result is a warning to enterprises that their workforce is three times more likely to be targeted with phishing attacks than infostealer malware."
* [App Governance in Defender for Cloud Apps: Your OAuth App Security Command Centre, Nov 2025](https://www.itprofessor.cloud/defender-for-cloud-apps-app-governance-oauth-security/)
* [Conditional Access bypasses, Nov 2025](https://cloudbrothers.info/en/conditional-access-bypasses/)
* [When Your Calendar Becomes the Compromise, Nov 2025](https://www.rapid7.com/blog/post/ve-when-your-calendar-becomes-the-compromise-phishing/)
* [How #ConsentFix attack looks in the logs: Different methods, same behaviour. Dec 2025](https://www.linkedin.com/posts/mehmetergene_consentfix-threathunting-detectionengineering-activity-7407452633495425025-RCON): `SigninLogs | project IPAddress,SessionId,AppDisplayName,UserAgent,UniqueTokenIdentifier,ResourceDisplayName`
* [ConsentFix: Analysing a browser-native ClickFix-style attack that hijacks OAuth consent grants, Dec 2025](https://pushsecurity.com/blog/consentfix)
* [TokenFlare: Serverless AiTM Phishing in Under 60 Seconds, Dec 2025](https://labs.jumpsec.com/tokenflare-serverless-AiTM-phishing-in-under-60-seconds/)
* [ClickFix attacks are increasingly devious, dangerous, and can hack you in an instant, Jan 2026](https://this.weekinsecurity.com/clickfix-attacks-are-increasingly-devious-dangerous-and-can-get-you-hacked-in-an-instant/)
* [How the latest deepfake scam can cheat companies out of millions  Hackers are targeting businesses with video deepfakes of top executives that can trick people into sending money, sharing passwords, or revealing sensitive information - all in seconds. CNN’s Clare Duffy met with ethical hacker and security expert Rachel Tobac to see just how easy it is for bad actors to impersonate someone using AI. Jan 2026](https://edition.cnn.com/2025/10/07/business/video/deepfake-scam-ai-zoom-call-digvid)
* [Scaling the Fraud Economy: Pig Butchering as a Service, Jan 2026](https://www.infoblox.com/blog/threat-intelligence/scaling-the-fraud-economy-pig-butchering-as-a-service/)
* [ConsentFix (a.k.a. AuthCodeFix): Detecting OAuth2 Authorization Code Phishing, Jan 2026](https://blog.nviso.eu/2026/01/29/consentfix-a-k-a-authcodefix-detecting-oauth2-authorization-code-phishing/)
* [AiTM/ MFA phishing attacks in combination with “new” Microsoft protections (2026 edition), Sep 2025](https://jeffreyappel.nl/aitm-mfa-phishing-attacks-in-combination-with-new-microsoft-protections-2023-edt/)
* [Starkiller: New ‘Commercial-Grade’ Phishing Kit Bypasses MFA, Feb 2026](https://www.infosecurity-magazine.com/news/starkiller-phishing-kit-bypasses/)
* [Would You Click ‘Accept’? Automatically detecting malicious Azure OAuth applications using LLMs, Feb 2026](https://www.wiz.io/blog/detecting-malicious-oauth-applications)
* [Abusing Entra ID App Registrations for Long-Term Persistence, Jun 2025](https://guardz.com/blog/abusing-entra-id-app-registrations-for-long-term-persistence/)
* [OAuth redirection abuse enables phishing and malware delivery, Mar 2026](https://www.microsoft.com/en-us/security/blog/2026/03/02/oauth-redirection-abuse-enables-phishing-malware-delivery/)
* [1 in 4 phishing emails now contain no malicious link. No attachment. No exploit.  Just a phone number.  It's called TOAD — Telephone Oriented Attack Delivery. It surged 127% last year. Mar 2026](https://www.linkedin.com/posts/mfaas_1-in-4-phishing-emails-now-contain-no-malicious-activity-7437120474561757184-xOxT)
* [There is no longer any such thing as Computer Security, Sep 2018](https://blog.codinghorror.com/there-is-no-longer-any-such-thing-as-computer-security/) (about phishing), [Basic security precautions for non-profits and journalists in the United States, early 2019. ](https://techsolidarity.org/resources/basic_security.html)
* [Inside p1bot: A Vishing Platform Weaponizing ElevenLabs, Mar 2026](https://www.miragesecurity.ai/blog/inside-p1bot-vishing-platform-weaponizing-elevenlabs), [Researchers uncover AI-powered vishing platform](https://www.helpnetsecurity.com/2026/03/11/researchers-uncover-ai-powered-vishing-platform/)
* [New widespread EvilTokens kit: device code phishing as-a-service – Part 1, Mar 2026](https://blog.sekoia.io/new-widespread-eviltokens-kit-device-code-phishing-as-a-service-part-1/)
