# Security analyst mindset

Goal: push better responsibility, curiosity and communication, make a difference

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
* [I Was There When Digital Forensics Lost Its Soul. Oct 2025](https://www.linkedin.com/pulse/i-when-digital-forensics-lost-its-soul-brett-shavers-otkec)
* [Your DF/IR skills won’t be tested by technology; it’ll be tested by testimony. Nov 2025](https://www.linkedin.com/pulse/your-dfir-skills-wont-tested-technology-itll-brett-shavers-apjtc), [Fight City Hall: If You Missed the Webinar, You’re Making Mistakes You Don’t Know About, Nov 2025](https://brettshavers.com/brett-s-blog/entry/fight-city-hall-if-you-missed-the-webinar-youre-making-mistakes-you-dont-know-about)
  1. You Assume Evidence Will Still Exist When You Request It
  2. Your Report Structure Will Collapse Under Adversarial Pressure
  3. Chain-of-Custody Weak Points Are Not “Minor Issues.” They Are Attack Surfaces.
  4. Your Terminology Probably Isn’t Defensible
  5. You Are Preparing for Friendly Questions, Not Hostile Ones
  6. Your Workflow Has Failure Points You Can’t See Yet

* [Why you should hire curious people, Dec 2019](https://www.conferencesthatwork.com/index.php/leadership/2019/12/why-you-should-hire-curious-people/)
* [Security Incident Response - a Process, Apr 2020](blog.jeffbryner.com/2020/04/14/security-incident-response-a-process.html)
* Triage template: Summary/Understanding, Actions (What has been done, ongoing, next), Timeline, IOC, Theories, Lessons learned
* Executive summary: Summary, Actions (short)
* [HISAC - High Impact Security Analysis and Communication. How to be a well rounded SOC/MDR/Cyber/Information Security Analyst. Jan 2025](https://www.jaiminton.com/internal-blog/high-impact-security-analysis)
* [*A brief note to new cybersecurity grads trying to land that first job.*, Nov 2025](https://www.linkedin.com/posts/jen-easterly_a-brief-note-to-new-cybersecurity-grads-activity-7392076035799883776-OhKo): (apply largely)
  1) Don’t compete with AI — learn to lead it.
  2) Strengthen your technical foundation
  3) Go where the growth is. Some areas are saturated. Others are exploding
  4) Find opportunities to build experience
* [Learning to ADAPT | Framework for analyzing any evidence in IR, Nov 2025](https://chocolatecoat4n6.com/2025/11/30/learning-to-adapt-framework-for-analyzing-any-evidence-in-ir/): Approach, Discovery, Association, Profile, Timeline
* [Thoughts on Analysis, Nov 2025](https://windowsir.blogspot.com/2025/11/thoughts-on-analysis.html): **"The key to all of this is to document your analysis process; if you don't know what you did, you can't make modifications or adjustments to the process."**
* [The FACT Attribution Framework v1.0, Dec 2025](https://zenodo.org/records/17745959): "The FACT Attribution Framework v1.0 is a legally grounded investigative model designed to bridge the gap between technical digital evidence and human attribution."
* [The late Tom Stoppard, in his play Hapgood, had some good advice for writers of scientific papers.](https://federate.social/@mattblaze/115693121409354888), <https://en.wikipedia.org/wiki/Hapgood_(play)>
* [The Art of Pivoting - Techniques for Intelligence Analysts to Discover New Relationships in a Complex World](https://github.com/adulau/the-art-of-pivoting) (pdf, html, epub)
* [THE RED TEAM HANDBOOK, A product of the TRADOC G–2 Operational Environment Enterprise](https://home.army.mil/wood/application/files/6115/8222/0759/RedTeamHB.pdf)
* [Why do so many new analysts drown in logs?They're great at using tools, but they haven't mastered the foundational skills of investigation. Jan 2026](https://www.linkedin.com/posts/adamgoss1_cyberinvestigation-threathunting-soc-activity-7413550033024753664-q4ve): "4 core evidentiary skills: Interpretation, Manipulation, Capability Comprehension, Collection", <https://kravensecurity.com/hack-the-box-brutus-sherlock-walkthrough/>
* [CTI Notetaking: How to Make Effective Notes and Documentation, Jul 2025](https://kravensecurity.com/cti-notetaking-guide/)
* [Quiet, Loud, and in the Logfiles: The Detection Duo You Didn’t Know You Needed, May 2025](https://dispatch.thorcollective.com/p/quiet-loud-and-in-the-logfiles) "The Introverts and the Extroverts."
* [A collection of inspiring lists, manuals, cheatsheets, blogs, hacks, one-liners, cli/web tools and more. ](https://github.com/trimstray/the-book-of-secret-knowledge)
* [Why You Should Build The most powerful thing you can do in security is create something that did not exist before. Jan 2026](https://dispatch.thorcollective.com/p/why-you-should-build)
* [Presenting the ADAPT framework: Investigation and Analysis without Paralysis, Jan 2026](https://chocolatecoat4n6.com/2026/01/23/presenting-the-adapt-framework-investigation-and-analysis-without-paralysis/) "Approach Discovery Association Profile Timeline"
* [Skill Atrophy in Cybersecurity: Part 3- The Mid-Level Danger Zone — Experience Without Adaptation! Feb 2026](https://nothingcyber.medium.com/skill-atrophy-in-cybersecurity-part-2-the-mid-level-danger-zone-experience-without-adaptation-a7394b9546d2)
* [Skill Atrophy in Cybersecurity: Part 6- The Accelerators — AI! Feb 2026](https://nothingcyber.medium.com/skill-atrophy-in-cybersecurity-part-6-the-accelerators-ai-952192448acb)
* [Top Lessons from Operation Deepfake & What They Teach Us About Insider Risks, Jan 2026](https://vertex.link/blogs/insider-threat-lms/)
* [Staying ahead of the constant flow of intelligence data isn’t about collecting more, it’s about connecting the right signals faster.
Ryann Hallback (reign) shows how analysts cut through noise, link critical data, and move investigations forward with confidence. https://www.youtube.com/watch?v=84oGqEL7ITQ](https://bsky.app/profile/vertexproject.bsky.social/post/3mfrtqc3brk2j)
* [Does AI have a role in security? Perhaps. Is it going to replace DF analysts? ...](https://www.linkedin.com/posts/harlan-carvey-86a8694b_does-ai-have-a-role-in-security-perhaps-activity-7433152986064785409-xTbw)
> Consider how you, as a DF analyst, currently conduct your analysis.
> Is it goal-based?
> Do you have your goals documented at the top of your case notes? (I do)
> Is your tool usage intentional, and derived from your goals, and based on deep knowledge and understanding of the data, as well as the tool itself?
> Do you recognize & document potential gaps in data, pivot based on findings, and apply lessons learned from previous analysis by operationalizing those lessons?
> If you said "yes" to each of those questions, AI will not replace you.
* [Too many people simply don't understand that you actually want some slack in your organization. You want people to not be grinding 24/7, because sometimes, you will have a crisis that requires all hands on deck, and if all hands are *always* on deck, things fall apart.](https://bsky.app/profile/jkfecke.bsky.social/post/3mhrivvcbsk2u), <https://www.jalopnik.com/2129924/laguardia-lone-air-traffic-controller-ground-air-space/>
* [Nouveau design, Fev 2026](https://richard-dern.fr/interets/divers/2026/02/24/nouveautes-du-blog/) "Comme presque chaque année depuis 2021, j’ai créé un nouveau design pour le blog. Il est toujours totalement dépourvu de javascript, le CSS fait toujours moins de 15ko, et la page d’accueil pèse un peu moins de 1.5Mo. [...] Il est loin le temps où le client savait ce qu’il voulait, où il était capable d’aligner sa vision dans un document complet, conjointement avec les développeurs grâce à un lien social, et où le livrable était considéré comme définitif. [...] Je n’ai rien fait de spécial : j’ai mis à jour mon blog, comme des milliers de blogueurs à travers le monde à chaque instant. J’ai pourtant l’impression d’avoir relié mon passé et mon avenir. Je ne sais pas si l’IA causera notre perte ou sera notre salut, et le fait-même de se poser la question est troublant. Je n’aurais pas cru être amené à tant de métaphysique, simplement en mettant mon site à jour.  Je suis juste content de ne pas m’être laissé dépasser par l’IA."
* [From Operations to Leadership: What 19 Years in Cybersecurity Actually Taught Me. Mar 2026](https://www.hurrikane.net/from-operations-to-leadership-what-19-years-in-cybersecurity-actually-taught-me)
* [The Slow Death of the Power User, Feb 2026](https://fireborn.mataroa.blog/blog/the-slow-death-of-the-power-user/)
* [If you want someone to believe something, you have to provide convincing evidence. You're the one trying to convince ME. You don't get to say "I dunno, you're the expert, you tell me how they did it." I don't KNOW how they did it, or if they did it. I've seen no evidence of any fraud, in fact.](https://bsky.app/profile/mattblaze.org/post/3mleybnsnxs2t)
