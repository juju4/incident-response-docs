# Ransomware

## Preparation

* Offline/Immutable or segmented backups
* Identity segmentation including Active Directory administrative tier model and enforcing MFA wherever is possible
* Network segmentation
* Supply chain management
* Restrict Windows network shares, RDP, WinRM and other management services to allow-only list
* Priority list of key internal staff, systems to validate healthy or restore, customers to take care
* External support: IR retainer, General counsel, cyber insurance, Law Enforcement...
* Process to collect IR data for system online and offline (network or system disconnected)

## Playbooks

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

## Pay ransomware or not
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

## Post-Incident

* Ensure restored full capacity and lessons learned
* Preserve evidence for insurance and legal actions
* Preserve most valuable encrypted data that was not recovered from elsewhere in case encryption key is made available or vulnerability found later

## References

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
* [Map tracking ransomware, by OCD World Watch team](https://github.com/cert-orangecyberdefense/ransomware_map)
* [CERT SG IRM-17-Ransomware](https://github.com/certsocietegenerale/IRM/blob/main/EN/IRM-17-Ransomware.pdf)
* [Ransom Playbook](https://gitlab.com/syntax-ir/playbooks/-/tree/main/IRP-Ransom)
* <https://www.ransomlook.io/analyses>

* [Lessons from TV5Monde 2015 Hack, Jun 2017](https://www.comae.com/posts/lessons-from-tv5monde-2015-hack/), [Conférence de clôture: Retour technique de l'incident de TV5Monde  ANSSI - SSTIC - French, Jun 2017](https://www.sstic.org/2017/presentation/2017_cloture/)
* [A Conversation with a Hacker - CWT - operator negotiation, Sep 2020](https://www.triella.com/a-conversation-with-a-hacker/)
* [Ransomware Victims That Pay Up Could Incur Steep Fines from Uncle Sam, Oct 2020](https://krebsonsecurity.com/2020/10/ransomware-victims-that-pay-up-could-incur-steep-fines-from-uncle-sam/), [Advisory on Potential Sanctions Risks for Facilitating Ransomware Payments - OFAC, Oct 2020](https://home.treasury.gov/system/files/126/ofac_ransomware_advisory_10012020_1.pdf)
* [Hospitals take action to avoid ransomware attacks, including preemptive email shut down, Nov 2020](https://www.beckershospitalreview.com/cybersecurity/hospitals-take-action-to-avoid-ransomware-attacks-including-pre-emptive-email-shut-down.html)
* [Ransomware: Remove Response Paralysis with a Comprehensive Incident Response Plan](https://www.marsh.com/sg/insights/research/ransomware-removing-response-paralysis.html)
* [Human operated ransomware, Feb 2021](https://docs.microsoft.com/en-us/security/compass/human-operated-ransomware)
* [I've worked a lot of #ransomware incidents and I've found that most companies don't realize what the true cost of a ransomware incident is.But isn't it just paying the ransom or restoring and you're done? Nope. Here are the (potential) costs (based on my experience): (1/X), May 2021](https://twitter.com/SecShoggoth/status/1389645581325320204)
* [BloodHound versus Ransomware: A Defender’s Guide, Jun 2021](https://posts.specterops.io/bloodhound-versus-ransomware-a-defenders-guide-28147dedb73b)
* [Ransomware prevention: How organizations can fight back , Feb 2022](https://www.mckinsey.com/business-functions/risk-and-resilience/our-insights/ransomware-prevention-how-organizations-can-fight-back)
* [Legitimate exfiltration tools : summary and detection for incident response and threat hunting, Sep 2023](https://www.synacktiv.com/publications/legitimate-exfiltration-tools-summary-and-detection-for-incident-response-and-threat.html)
* [The State of Cloud Ransomware in 2024, Nov 2024](https://www.sentinelone.com/blog/the-state-of-cloud-ransomware-in-2024/)
* [Ransomware-driven data exfiltration: techniques and implications, Nov 2024](https://blog.sekoia.io/ransomware-driven-data-exfiltration-techniques-and-implications/)
* [Rebuild or Restore Active Directory from Backups? ... not a "rebuild" guy, May 2025](https://www.linkedin.com/posts/emannon_rebuild-or-restore-active-directory-from-activity-7330407013648138241-k_Kf)
* [Ransomware Response Playbook](https://frsecure.com/ransomware-response-playbook/)

* [Australia's new ransomware payment disclosure rules, if total sales within a year over AUS$3 million ($1.93 million) report within 72 hours. Jun 2025](https://www.darkreading.com/threat-intelligence/australia-ransomware-payment-disclosure-rules)
* [Always maintain copies of encrypted data as long as decryption would still be valuable for the business. Jul 2025](https://bsky.app/profile/malwarejake.bsky.social/post/3lt2mvtwwrs2f), Hunters International ransomware shuts down operation and releases free decryption keys Via 3xp0rt: https://x.com/3xp0rtblog/status/1940690461624357144
* [Ransomware Rising, Sep 2025. Confronting the fastest-growing cybercrime through international cooperation.](https://digitalfrontlines.io/2025/09/03/ransomware-rising/)
* [5 lessons we learned from our ransomware attack](https://dxc.com/ca/en/insights/perspectives/article/5-lessons-we-learned-from-our-ransomware-attack), <https://dxc.com/content/dam/dxc/projects/dxc-com/us/pdfs/services/security/DXC-5%20Lessons%20we%20learned%20for%20our%20ransomware%20attack.pdf>, <https://bsky.app/profile/andyjabbour.bsky.social/post/3m7y4vni2is2y>
> 1. Know your infrastructure.
> 2. Involve senior leadership from the start.
> 3. Engage authorities and experts early.
> 4. Gain as much leverage as you can — and don’t pay.
> 5. Be transparent.
* [Arctic Wolf Threat Report Highlights 11x Growth in Data Extortion Incidents and Continued Dominance of Ransomware, Feb 2026](https://arcticwolf.com/resources/press-releases/arctic-wolf-threat-report-highlights-11x-growth-in-data-extortion-incidents-and-continued-dominance-of-ransomware/)
* [This doesn't surprise me. Orgs have greatly matured their recovery operations to the point that they'll wipe and restore rather than pay for a decryption key. The attackers are going where the money is.](https://bsky.app/profile/elforesto.coolestfamilyever.com/post/3mfrknlfgj22o), "Data theft-only attacks accounted for 57% of all extortion insurance claims last year, according to numbers released by cyber insurance provider Resilience" <https://www.prnewswire.com/news-releases/resilience-cyber-claims-data-reveals-the-new-economics-of-professionalized-cybercrime-302696505.html>
* [The number of ransomware victims paying threat actors has dropped to 28% last year, an all-time low, despite a significant increase in the number of claimed attacks.](https://bsky.app/profile/bleepingcomputer.com/post/3mfreawovnu2i), <https://www.bleepingcomputer.com/news/security/ransomware-payment-rate-drops-to-record-low-as-attacks-surge/>
* [[New Report with @rusi.bsky.social] Assessing the Impact of Ransomware Interventions and Countermeasures: A Framework. This Pharos report presents a practical framework to evaluate counter-ransomware actions across severity, scope, longevity & reversibility, and signalling value.](https://bsky.app/profile/virtualroutes.bsky.social/post/3mg5j7xfymk2k), <https://virtual-routes.org/pharos-report-no-4-assessing-the-impact-of-ransomware-interventions-and-countermeasures-a-framework/>, <https://bsky.app/profile/bindinghook.bsky.social/post/3mgcowyb3vs22>, <https://bindinghook.com/assessing-the-impact-of-counter-ransomware-interventions/>
* [Beyond Availability – Forensic Backup Scanning with Veeam and THOR, Oct 2025](https://www.nextron-systems.com/2025/10/22/beyond-availability-forensic-backup-scanning-with-veeam-and-thor/), <https://community.veeam.com/yara-and-script-library-67/using-veeam-data-integration-api-with-nextron-s-thor-11846>, <https://github.com/NextronSystems/veeam-integration>
* [The who, what, and why of the attack that has shut down Stryker’s Windows network  Company says it doesn’t know how long it will take to restore its Microsoft environment. Mar 2026](https://arstechnica.com/security/2026/03/whats-known-about-wiper-attack-on-stryker-a-major-supplier-of-lifesaving-devices/)
* [Everyday tools, extraordinary crimes: the ransomware exfiltration playbook, Mar 2026](https://blog.talosintelligence.com/everyday-tools-extraordinary-crimes-the-ransomware-exfiltration-playbook/), <https://github.com/Cisco-Talos/Xfiletrator>
* [EDR killers explained: Beyond the drivers, Mar 2026](https://www.welivesecurity.com/en/eset-research/edr-killers-explained-beyond-the-drivers/), <https://github.com/eset/malware-ioc/tree/master/edr_killers>
* [Canadian security firm Bedrock Safeguard has released a decryption utility that can recover files encrypted by The Gentlemen ransomware.
The decrypter can be used if companies can recover at least one memory dump taken while the ransomware encryption process was active
https://github.com/Bedrock-Safeguard/gentlemen-decryptor](https://bsky.app/profile/campuscodi.risky.biz/post/3mkq45d55g223)
* [Conduent are facing legal cases from multiple US states over their attempt to cover up a ransomware incident.
As uncovered on this very fediverse thread, they were attempting to hide a SafePay ransomware incident from the US government as a "service interruption" - the second time they pulled this stunt.
https://www.databreachtoday.com/missouri-alleges-conduent-stonewalling-state-on-hack-a-31645](https://cyberplace.social/@GossiTheDog/116556501827414216)
* [The criminals have offered “assurance”. Ffs
Also they’ve offered assurance that no one will be extorted. They haven’t mentioned not selling on the data for scams](https://bsky.app/profile/ciaranm.bsky.social/post/3mln6g47igs2h), <https://bsky.app/profile/racheltobac.bsky.social/post/3mlmtfnbsek2d>, <https://www.insidehighered.com/news/tech-innovation/administrative-tech/2026/05/11/instructure-pays-ransom-canvas-hackers>, <https://www.instructure.com/incident_update>
* [It is official that half of CISOs pay in ransomware attacks, May 2026](https://www.cybersecurity-insiders.com/it-is-official-that-half-of-cisos-pay-in-ransomware-attacks/), [Majority of Chief Information Security Officers (CISOs) Consider Paying Cybercriminals to End Ransomware Attacks, According to New Absolute Security Research](https://www.absolute.com/press-releases/new-research-cisos-ransomware-trends), [To pay, or not to pay: 58% of CISOs say they would pay the ransom for their data, May 2026](https://www.csoonline.com/article/4176472/to-pay-or-not-to-pay-58-of-cisos-say-they-would-pay-the-ransom-for-their-data.html)
* [The CEO has a 44% pay cut after the LAPSUS$ incident https://www.cityam.com/ms-pay-slashed-after-cyberattack-turmoil/](https://cyberplace.social/@GossiTheDog/116685605695435086), [M&S chief’s pay slashed by £3m after cyberattack turmoil, Jun 2026](https://www.cityam.com/ms-pay-slashed-after-cyberattack-turmoil/) "The bulk of Machin’s pay cut came as a result of the board’s decision to axe the wider executive bonus scheme.", [M&S scraps staff bonuses after cyberattack cuts profits by a third The high street retailer said no employees would receive a bonus this year after the attack left annual pre-tax profits down 28.8 per cent at £364.6m](https://www.thetimes.com/business/companies-markets/article/m-and-s-cyberattack-wipes-131m-off-annual-profits-xrlldf7lb)
* [Bajaj Auto reports ransomware attack on systems, says impact contained, Jun 2026](https://legal.economictimes.indiatimes.com/news/corporate-business/bajaj-auto-faces-ransomware-attack-impact-contained-and-systems-secure/131954305)
* [If you have ever handled a ransomware incident, you have probably seen a room like this. Notebooks staged for wipe, rebuild, hardening, and controlled return to service. Jun 2026](https://www.linkedin.com/posts/mauricefielenbach_threatintel-dfir-cybersecurity-activity-7473818536768004097-1GQn) "The practical takeaway is boring, but it decides the quality of the response. VPN needs MFA. Privileged accounts should not be usable for remote access. Firewall and VPN logs need central forwarding. Retention must be long enough to cover the time between compromise, detection, containment, and investigation."
* [Fundamentally it wasn't a domain wide Windows ransomware incident which stopped production.. it was one Unix system.   It's not the kind of thing which is *already happening at scale for the past decade* with ransomware groups.  CISOs should focus on cyber operational resiliency.  If you're just doing this now, you should have done this ten years ago.  If you're chasing marketing blogs for AI agents, you're doing it wrong.](https://cyberplace.social/@GossiTheDog/116852288612626208), [JADEPUFFER: Agentic ransomware for automated database extortion, Jul 2026](https://www.sysdig.com/blog/jadepuffer-agentic-ransomware-for-automated-database-extortion)
