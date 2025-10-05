# Security analyst mindset

Goal: push better responsibility, curiosity and communication

> "Never assume, verify"
> "Trust but verify"
> "Zero-Trust"
> "Perfection is the enemy of the good when it comes to emergency management. Speed trumps perfection... The greatest error is not to move. The greatest error is to be paralyzed by the fear of failure. If you need to be right before you move, you will never win."

## Responsibility

Your investigation can decide to fire someone, to send someone to jail, hopefully never to kill.
It can and should be reviewed by your internal peers, management and internal auditors.
Depending on context, it may be reviewed by external auditors, lawyers and journalists (1).
Not all investigations are equals. "Choose your battle" but ensure to document and communicate limitations and tradeoffs to your team and management.

## Mindset

* Call it questioning mindset, detective, investigative or just scientific or feedback loop.
* Don't panic
* Don't wait / act fast - WHO crisis director: [“Perfection is the enemy of the good when it comes to emergency management. Speed trumps perfection … The greatest error is not to move. The greatest error is to be paralyzed by the fear of failure. If you need to be right before you move, you will never win.", Michael Ryan (WHO Health Emergencies Programme) at daily press briefing on COVID 19 March 13th 2020](https://www.youtube.com/watch?v=AqRHH6e-y6I), [We are in a race to save lives right now and as my colleague Dr. Mike Ryan said back in March last year, it’s important in any crisis to act fast and have no regrets, WHO, Jan 2021](https://www.who.int/director-general/speeches/detail/opening-remarks-for-the-media-briefing-on-covid-19-5-january-2021)
* Relentlessly ask questions but prioritize as nearly all investigations are time-bound. No business will invest in years of investigation.
* Establish timeline of the key events of the attack and of the response
* Known Knowns, Known Unknowns - Donald Rumsfeld, https://en.wikipedia.org/wiki/There_are_unknown_unknowns
* Diamond Model - Threat Intelligence, https://www.threatintel.academy/diamond/
* Analysis of Competing Hypotheses - Richards (Dick) J. Heuer, Jr., CIA
  * https://en.wikipedia.org/wiki/Analysis_of_competing_hypotheses
  * https://web.archive.org/web/20070613032237/https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/psychology-of-intelligence-analysis/art11.html, https://www.cia.gov/resources/csi/books-monographs/psychology-of-intelligence-analysis-2/
* Investigative Mindset, Chris Sanders
  * [Investigation Theory Training](https://chrissanders.org/training/investigationtheory/)
  * Deconstructing the analyst mindset, SANS CTI Summit 2023, https://www.sans.org/blog/a-visual-summary-of-sans-cti-summit-2023/
* Be mindful of bias
  * https://en.wikipedia.org/wiki/List_of_cognitive_biases
  * https://mediasonar.com/2019/07/24/cognitive-biases-investigations/
  * https://www.visualcapitalist.com/every-single-cognitive-bias/
  * [Overcoming Cognitive Biases During Threat Hunts and Incident Response, Sep 2019](https://dgunter.com/2019/09/26/overcoming-cognitive-biases-during-threat-hunts-and-incident-response/)
  * [Through Your Mind’s Eye: What Biases Are Impacting Your Security Posture? McAfee, May 2021](https://www.mcafee.com/blogs/other-blogs/executive-perspectives/through-your-minds-eye-what-biases-are-impacting-your-security-posture/)
  * [Correcting Prevention Bias in Your OT Cyber Incident Response, Dragos, Jul 2021](https://www.dragos.com/blog/correcting-prevention-bias-in-your-ot-cyber-incident-response/)
  * [Avoiding Cognitive Bias in Your Investigations, Maltego, Oct 2022](https://www.maltego.com/blog/ensuring-objective-analysis-using-maltegos-data-driven-solution/)
* When your initial triage is done (usually between 15-60min), you should be able to explain the alert/incident, to your peers, your management, an end-user or a business owner.
  * Able to explain and answer at least partially their questions.
  * Communicate with the right context. Don't sent alert "Malicious file detected on your system. Remove immediately": What file (name and path), When, by Who, Where, and Why/How characterized malicious (5 Ws)
  * Know what to say and what not to say. You should give enough context but you should also validate the information you found vs what is said to you, typically if Insider Threat.


Examples
* [SCARLETEEL: Operation leveraging Terraform, Kubernetes, and AWS for data theft, Feb 2023](https://sysdig.com/blog/cloud-breach-terraform-data-theft/) "Launch a cryptominer in order to make money or provide a distraction."
* [Research Reveals Hacker Tactics: Cybercriminals Use DDoS as Smokescreen for Other Attacks on Business, Kasperksy, Nov 2016](https://www.kaspersky.com/about/press-releases/2016_research-reveals-hacker-tactics-cybercriminals-use-ddos-as-smokescreen-for-other-attacks-on-business)
* [A quick thread on observer bias…In 2011, I was fortunate to be a part of @mandiant, when the threat intelligence team was just beginning to coalesce. Back then, threat activity came in 3 flavors: APT, FIN, and everything else, and it was a problem... /THREAD](https://twitter.com/invisig0th/status/1375416158434828293)
* [Symantec: Data-stealing hackers use DDoS to distract from attacks, Oct 2012](https://www.zdnet.com/article/symantec-data-stealing-hackers-use-ddos-to-distract-from-attacks/)
* [Rogue admin jailed after taking down former employer’s network, Dec 2016](https://nakedsecurity.sophos.com/2016/12/06/rogue-admin-jailed-after-taking-down-former-employers-network/)

## References

* [Five Ws](https://en.wikipedia.org/wiki/Five_Ws)
* [Spy the Lie: Three Former CIA Officers Reveal Their Secrets to Uncloaking Deception](https://www.goodreads.com/book/show/13167156-spy-the-lie)
* [On Conveying Doubt, Cisco Talos, Aug 2017](https://blog.talosintelligence.com/on-conveying-doubt/)
* [Defenders think in lists. Attackers think in graphs. As long as this is true, attackers win. John Lambert, Apr 2015](http://web.archive.org/web/20170929011236/https://blogs.technet.microsoft.com/johnla/2015/04/26/defenders-think-in-lists-attackers-think-in-graphs-as-long-as-this-is-true-attackers-win/)
* [New York Times Rule Law and Legal Definition](https://definitions.uslegal.com/n/new-york-times-rule/): "New York Times rule is a commonsense rule of ethical conduct that a person should not do anything arguably newsworthy in public or in private that one would mind having reported on the front page of a major newspaper. The rule ultimately protects defamatory falsehood. New York Times rule is also known as New York Times test or New York Times v. Sullivan rule."

* [Life-long student mentality is key to success as a SOC analyst, that's one of the things I learned from @jhencinskiand the leadership at @expel_io. Great advice here in the blog, and I think experience as a SOC analyst can take you literally anywhere you'd like to go in INFOSEC. Apr 2021](https://twitter.com/stvemillertime/status/1380593714410577920)
* [5 helpful habits for aspiring #SOC analysts 1. Survey the field, #FF folks like @stvemillertime 2. Combine reading & practice 3. Seek learning, not just reading 4. Develop an attacker mindset 5. Be dauntless! Apply, maybe you get a no. Try again! Apr 2021](https://twitter.com/jhencinski/status/1380590078087606272)
* [It’s sometimes hard to remember as a security professional that other people generally don’t see the world in terms of what criminals and pranksters will *for sure* exploit, constantly, and what the result will be. They don’t. It’s not common. Apr 2021](https://twitter.com/hacks4pancakes/status/1384009600966348803)
* [1. Never stop learning.2. See failure as a beginning.3. Teach others what you know.4. Assume nothing, question everything.5. Analyze objectively.6. Practice humility.7. Respect constructive criticism.8. Love what you do.9. Give credit where it's due.10. Take initiative. Feb 2023](https://twitter.com/ProfFeynman/status/1627127271671861249)
* [Struggling to find ‘bad’ in your SIEM? Here are two simple tips.1. Pivot. Ok so X user created an alert for being added to a privileged group. Obviously check the user account itself, but then pivot to the asset , what events occurred on it during the time. Oh it /THREAD, Sep 2020](https://twitter.com/blueteamblog/status/1311409973512089607)

* [Sysadmin tries, fails at being l337 hax0r, gets jail time, Jan 2008](https://arstechnica.com/information-technology/2008/01/sysadmin-tries-fails-at-being-l337-hax0r-gets-jail-time/)
* [Feds: IT admin plotted to erase Fannie Mae, Jan 2009](https://www.theregister.com/2009/01/29/fannie_mae_sabotage_averted/)
* [NSA Warns of Rogue System Administrators 1991 - Two Versions](https://cryptome.org/2014/01/nsa-rogue-sysadmins-compare.htm)
* [How Analysts Approach Investigations with Diagnostic Inquiry, May 2016](https://chrissanders.org/2016/05/how-analysts-approach-investigations/)
* [So, you want to work in security? Jul 2016](https://www.freecodecamp.org/news/so-you-want-to-work-in-security-bc6c10157d23#.8vgj4hxdy)
* [SEC Charges Rogue Trader Who Bankrupted His Firm, Sep 2021](https://www.sec.gov/news/press-release/2021-205)
* [UBS Rogue Trader Incident Stirs Access Management Speculation, Sep 2011](https://www.darkreading.com/authentication/ubs-rogue-trader-incident-stirs-access-management-speculation)
* [IR 101 The analyst mindset, BTV Project Obsidian, Aug 2023](https://github.com/blueteamvillage/Project-Obsidian-DC31/blob/master/IR/Presentations/BTV-Project%20Obsidian-IR101%20Module%204.pptx)
* [The Lost Art of Careful Craftsmanship: Lessons from My Uncle’s Workshop, Mar 2025](https://cyb3rops.medium.com/the-lost-art-of-careful-craftsmanship-lessons-from-my-uncles-workshop-54ae2b7462ac)
* [Know Your Tools, Mar 2025](https://windowsir.blogspot.com/2025/03/know-your-tools.html)
* [Your Mood Is Murdering Your DF/IR Investigation and You Don’t Even Know It, May 2025](https://brettshavers.com/brett-s-blog/entry/your-mood-is-murdering-your-investigation-and-you-dont-even-know-it)

* [Security Incident Response - a Process, Apr 2020](blog.jeffbryner.com/2020/04/14/security-incident-response-a-process.html)
* Triage template: Summary/Understanding, Actions (What has been done, ongoing, next), Timeline, IOC, Theories, Lessons learned
* Executive summary: Summary, Actions (short)
* [HISAC - High Impact Security Analysis and Communication. How to be a well rounded SOC/MDR/Cyber/Information Security Analyst. Jan 2025](https://www.jaiminton.com/internal-blog/high-impact-security-analysis)
