

# Preparation

* Offline/Immutable or segmented backups
* Identity segmentation including Active Directory administrative tier model and enforcing MFA wherever is possible
* Network segmentation
* Supply chain management
* Restrict Windows network shares, RDP, WinRM and other management services to allow-only list
* Priority list of key internal staff, systems to validate healthy or restore, customers to take care
* External support: IR retainer, General counsel, cyber insurance, Law Enforcement...
* Process to collect IR data for system online and offline (network or system disconnected)

# Playbooks

For your company or for customer, partner

* Network split or shutdown
* Account access reset (user, service, API...)
* System containment, snapshot
* Domain controller restoration, Backup server, Image/Software distribution
* Reconnection risk assessment
* Preserve evidence
  * For legal reason, you may need or have to keep affected systems "as is". Review with your legal department, general counsel and insurance, what are your options and their impacts.
* Data restoration and validation - "dirty" backup
  * format check
  * AV scan
  * services functional tests
  * manual check
  * per business decision compared to other options (start from fresh, known good backup)

As large ransomware incident recovery is usually a long process, it is recommended to establish objectives and priorities per timeperiod (first few days, every week or month...).
* Scope
* Ensure recovery in good conditions
* Complaint (Law Enforcement): facts, timeline
* Customer and partners: communication, prevention, IOC

# Pay ransomware or not
This should be obviously your last resort option but there may be case when it has to be evaluated.
Ultimately, this is a decision by executive management.

Negotiation does not mean pay.
Negotiation can
  * give time to assess situation and evaluate compromise
  * confirm attacker statements
  * confirm if decryption is really possible, especially for most critical data.
  * delay information disclosure

If willing to pay, this should never be directly by company staff but with
  * Cyber-insurance nominated negotiator
  * Law Enforcement
Some countries require to notify government bodies
  * US OFAC and CISA. [Updated Advisory on Potential Sanctions Risks for Facilitating Ransomware Payments, Sep 2021](https://home.treasury.gov/system/files/126/ofac_ransomware_advisory.pdf)
  * FR fill a complaint. [Loi LOPMI : pour payer la rançon, il faudra déposer plainte, Mar 2022](https://www.zdnet.fr/actualites/loi-lopmi-pour-payer-la-rancon-il-faudra-deposer-plainte-39939113.htm)

# Post-Incident

* Ensure restored full capacity and lessons learned
* Preserve evidence for insurance and legal actions
* Preserve most valuable encrypted data that was not recovered from elsewhere in case encryption key is made available or vulnerability found later

# References

* [Ransomware Guide, CISA, Sep 2020](https://www.cisa.gov/publication/ransomware-guide)
* [CISA’s CSET Tool Sets Sights on Ransomware Threat, Jun 2021](https://us-cert.cisa.gov/ncas/current-activity/2021/06/30/cisas-cset-tool-sets-sights-ransomware-threat)
* [Stop Ransomware, CISA, Jul 2021](https://www.cisa.gov/stopransomware)
* [ENISA Threat Landscape 2020 - Ransomware, Oct 2020](https://www.enisa.europa.eu/publications/ransomware)
* [RANSOMWARE GUIDE, MS-ISAC, SEPTEMBER 2020](https://www.cisa.gov/sites/default/files/publications/CISA_MS-ISAC_Ransomware Guide_S508C_.pdf)
* [Attaques par rançongiciels, tous concernés - Comment les anticiper et réagir en cas d’incident ? ANSSI, Sep 2020](https://www.ssi.gouv.fr/guide/attaques-par-rancongiciels-tous-concernes-comment-les-anticiper-et-reagir-en-cas-dincident/)
* [Ransomware Protection and Containment Strategies, FireEye](https://www.fireeye.com/content/dam/fireeye-www/current-threats/pdfs/wp-ransomware-protection-and-containment-strategies.pdf)
* [Microsoft Enterprise access model, Jun 2021](https://docs.microsoft.com/en-us/security/compass/privileged-access-access-model), previously [Active Directory administrative tier model, Feb 2019](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material)
* [Ransomware: How to Prevent and Recover (ITSAP.00.099)](https://cyber.gc.ca/en/guidance/ransomware-how-prevent-and-recover-itsap00099), [Ransomware](https://cyber.gc.ca/en/ransomware)
* [NIST Ransomware Risk Management: A Cybersecurity Framework Profile - 8374](https://www.nist.gov/publications/ransomware-risk-management-cybersecurity-framework-profile)
* [Microsoft DART ransomware approach and best practices](https://docs.microsoft.com/en-us/security/compass/incident-response-playbook-dart-ransomware-approach)

* [Lessons from TV5Monde 2015 Hack, Jun 2017](https://www.comae.com/posts/lessons-from-tv5monde-2015-hack/), [Conférence de clôture: Retour technique de l'incident de TV5Monde  ANSSI - SSTIC - French, Jun 2017](https://www.sstic.org/2017/presentation/2017_cloture/)
* [A Conversation with a Hacker - CWT - operator negotiation, Sep 2020](https://www.triella.com/a-conversation-with-a-hacker/)
* [Ransomware Victims That Pay Up Could Incur Steep Fines from Uncle Sam, Oct 2020](https://krebsonsecurity.com/2020/10/ransomware-victims-that-pay-up-could-incur-steep-fines-from-uncle-sam/), [Advisory on Potential Sanctions Risks for Facilitating Ransomware Payments - OFAC, Oct 2020](https://home.treasury.gov/system/files/126/ofac_ransomware_advisory_10012020_1.pdf)
* [Hospitals take action to avoid ransomware attacks, including pre-emptive email shut down, Nov 2020](https://www.beckershospitalreview.com/cybersecurity/hospitals-take-action-to-avoid-ransomware-attacks-including-pre-emptive-email-shut-down.html)
* [Ransomware: Remove Response Paralysis with a Comprehensive Incident Response Plan](https://www.marsh.com/sg/insights/research/ransomware-removing-response-paralysis.html)
* [Human operated ransomware, Feb 2021](https://docs.microsoft.com/en-us/security/compass/human-operated-ransomware)
* [I've worked a lot of #ransomware incidents and I've found that most companies don't realize what the true cost of a ransomware incident is.But isn't it just paying the ransom or restoring and you're done? Nope. Here are the (potential) costs (based on my experience): (1/X), May 2021](https://twitter.com/SecShoggoth/status/1389645581325320204)
* [BloodHound versus Ransomware: A Defender’s Guide, Jun 2021](https://posts.specterops.io/bloodhound-versus-ransomware-a-defenders-guide-28147dedb73b)
* [Ransomware prevention: How organizations can fight back , Feb 2022](https://www.mckinsey.com/business-functions/risk-and-resilience/our-insights/ransomware-prevention-how-organizations-can-fight-back)
* [The State of Cloud Ransomware in 2024, Nov 2024](https://www.sentinelone.com/blog/the-state-of-cloud-ransomware-in-2024/)
* [Rebuild or Restore Active Directory from Backups? ... not a "rebuild" guy, May 2025](https://www.linkedin.com/posts/emannon_rebuild-or-restore-active-directory-from-activity-7330407013648138241-k_Kf)

* [Australia's new ransomware payment disclosure rules, if total sales within a year over AUS$3 million ($1.93 million) report within 72 hours. Jun 2025](https://www.darkreading.com/threat-intelligence/australia-ransomware-payment-disclosure-rules)
* [Always maintain copies of encrypted data as long as decryption would still be valuable for the business. Jul 2025](https://bsky.app/profile/malwarejake.bsky.social/post/3lt2mvtwwrs2f), Hunters International ransomware shuts down operation and releases free decryption keys Via 3xp0rt: https://x.com/3xp0rtblog/status/1940690461624357144
