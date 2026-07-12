# Identity/Credentials compromised

## Definition

Identity/Credentials compromised is common for home user but for enterprise, it is becoming more prevalent with Saas tools like Google Apps for Business, Microsoft Office 365, Amazon, Github to name a few.

## Prepare

* Ensure environment has a credentials/secrets rotation process that is regularly tested/used

## Course of Action - Human Identities

* Review compromission state
  * Main access, alternate (application password, oauth...)
  * Forwarding message rules
  * Privileged account? (Cloud roles & permissions)
  * Activities
  * Confirm if malicious
  * Check impact and blast radius
  * If Azure SSO: check SigninLogs, AuditLogs, EDR timeline, UnifiedAuditLog, mailbox MailItemsAccessed
  * If Side activities: Mail, Chat, File sharing, Consent O365 apps, other platforms (CRM, HR, Finance)...
* Do backup of evidence, especially if legal actions are planned
* Reset all access
  * Password, certificates, ssh key
  * Tokens/api keys
  * Mail rules
  * App consent
  * Other automations in available Cloud services
* Eventually, report to provider. Might be required if large impact like billing.
* Notify affected users (owner or person impacted by abuse)
  * Ensure preventative actions are done (2FA, Awareness, Audit&alerts, watch for leaked secret keys...)

## Course of Action - Non-Human Identities

* Review compromission state
  * Owner and usage
  * Privileged account? (Cloud roles & permissions)
  * Use of Active Directory gMSA (group Managed Service Accounts)?
  * Secrets, Certificates
  * Activities
  * Confirm if malicious
  * Check impact and blast radius
* Preserve Evidence
* Reset access
* Tighten access typically with managed identities and equivalent, network restrictions.

## References

Tools

* [Recover a hijacked or stolen Google Account](https://support.google.com/accounts/answer/6294825?hl=en)
* [How to fix a compromised (hacked) Microsoft Office 365 account, Dec 2015](https://blogs.technet.microsoft.com/office365security/how-to-fix-a-compromised-hacked-microsoft-office-365-account/), [O365-InvestigationTooling, Github](https://github.com/OfficeDev/O365-InvestigationTooling/)
* [My AWS account may be compromised](https://aws.amazon.com/premiumsupport/knowledge-center/potential-account-compromise/)
* [Incident Response Playbook Template](https://github.com/aws-samples/aws-incident-response-playbooks/blob/master/playbooks/IRP-CredCompromise.md)
* [Security Playbook for Compromised AWS Account Credentials](https://github.com/aws-samples/aws-customer-playbook-framework/blob/main/docs/Compromised_IAM_Credentials.md)
* [AWS IAM Credential Compromise - Analysis](https://github.com/aws-samples/jupyter-notebook-for-incident-response/blob/main/Playbooks/IAM Credential Compromise/credential-compromise-analysis.ipynb)
* [Keeping your account and data secure, GitHub](https://help.github.com/articles/keeping-your-account-and-data-secure/)
* [Recovering from systemic identity compromise](https://docs.microsoft.com/en-us/azure/security/fundamentals/recover-from-identity-compromise)
* [Compromised Credentials Response Playbook](https://frsecure.com/compromised-credentials-response-playbook/)
* [Removing sensitive data from a repository](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository): `git filter-repo`, [BFG Repo-Cleaner](https://rtyley.github.io/bfg-repo-cleaner/)
* [Revoke user access in Microsoft Entra ID](https://docs.azure.cn/en-us/entra/identity/users/users-revoke-access)
* [Use MailItemsAccessed to investigate compromised accounts](https://learn.microsoft.com/en-us/purview/audit-log-investigate-accounts)
* [Protect against consent phishing](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/protect-against-consent-phishing)
* [Token theft playbook](https://learn.microsoft.com/en-us/security/operations/token-theft-playbook)
* [Account Compromised Playbook](https://gitlab.com/syntax-ir/playbooks/-/tree/main/IRP-AccountCompromised) (workflows)
* [Compromised and malicious applications investigation](https://github.com/MicrosoftDocs/security/blob/main/security-docs/operations/incident-response-playbook-compromised-malicious-app.md) (workflows)
* [Octo Tempest: Hybrid identity compromise recovery, Jun 2024](https://techcommunity.microsoft.com/blog/microsoftsecurityexperts/octo-tempest-hybrid-identity-compromise-recovery/4166783) (Cloud eviction workflow) "We begin with the cloud eviction process. If any actor takes control of the identity plane in Microsoft Entra ID, a set of steps should be followed to hit reset and take back administrative control of the environment. Here are some tactical measures employed by the Microsoft Incident Response team to ensure the security of the cloud identity plane: [...] On-premises eviction"
* [Detecting and mitigating Active Directory compromises - ASD AU, Sep 2024](https://www.cyber.gov.au/business-government/detecting-responding-to-threats/detecting-and-mitigating-active-directory-compromises)
* [Remediation of active directory tier 0 - ANSSI, Apr 2025](https://messervices.cyber.gouv.fr/guides/en-cyber-attacks-and-remediation-remediation-active-directory-tier-0)
* [Common security incident investigation areas - Github](https://docs.github.com/en/code-security/reference/security-incident-response/investigation-areas): Exposed or compromised credentials, Unauthorized access and account compromise, Data exfiltration, Malicious code and workflow changes

* Reset passwords and sessions/cookies
  * https://www.newswire.com/news/new-report-from-flare-highlights-significant-costs-and-industry-impact-22553863
  * https://learn.microsoft.com/en-us/entra/identity/users/users-revoke-access
  * https://learn.microsoft.com/en-us/answers/questions/834400/process-to-remove-login-access-and-close-all-login
  * https://www.egroup-us.com/news/revoke-all-user-sessions-for-azure-ad-and-office-365/
  * https://support.google.com/a/answer/178854?hl=en
  * https://developers.google.com/identity/gsi/web/guides/revoke
  * [Windows RDP lets you log in using revoked passwords. Microsoft is OK with that. Apr 2025](https://arstechnica.com/security/2025/04/windows-rdp-lets-you-log-in-using-revoked-passwords-microsoft-is-ok-with-that/)

News

* [Advice for incident responders on recovery from systemic identity compromises, Dec 2020](https://www.microsoft.com/en-us/security/blog/2020/12/21/advice-for-incident-responders-on-recovery-from-systemic-identity-compromises/)
> Response objectives in approximate order:
>    1. Establish secure communications for personnel key to the investigation and response effort.
>    2. Investigate the environment for persistence and initial access point, while establishing continuous monitoring operations during recovery efforts.
>    3. Regain and retain administrative control of your environment and remediate or block possible persistence techniques and initial access exploits.
>    4. Improve posture by enabling security features and capabilities following best practice recommendations.
* [Monitoring OAuth Applications with Azure Sentinel, Jul 2021](https://learnsentinel.blog/2021/07/20/monitoring-oauth-applications-with-azure-sentinel-2/)
* [Microsoft Incident Response lessons on preventing cloud identity compromise, Dec 2023](https://www.microsoft.com/en-us/security/blog/2023/12/05/microsoft-incident-response-lessons-on-preventing-cloud-identity-compromise/)
* [The First 24 Hours After a Credential Compromise: An IR Playbook, Sep 2025](https://terrazone.io/credential-compromise-24h-ir-playbook/)
* [Defending ‘Data Exfiltration via Microsoft Graph’ : Living Off the API, Mar 2026](https://medium.com/@DFIRanjith/defending-data-exfiltration-via-microsoft-graph-living-off-the-api-7e4aaea976ca)

Non-Human identities
* [What are non-human identities?](https://www.microsoft.com/en-us/security/business/security-101/what-are-non-human-identities)
* [OWASP Top 10 Non-Human Identities Risks - 2025](https://owasp.org/www-project-non-human-identities-top-10/2025/top-10-2025/)
* [Expanding the Identity perimeter: the rise of non-human identities, Jun 2025](https://techcommunity.microsoft.com/blog/microsoftthreatprotectionblog/expanding-the-identity-perimeter-the-rise-of-non-human-identities/4418953)
  * Defender XDR: Rules > Service accountds classification
  * Attack Paths
* [When we announced Agent ID at Ignite, it as not just a marketing fad, it is a fundamental shift in how we do access for AI actors. If you register an agent with Entra and it authenticates with Entra then every token, every sign in log will indicate this is an agent (whether it's acting autonomously or on behalf of user). Mar 2026](https://www.linkedin.com/posts/tarekdawoud_token-claims-reference-for-agent-ids-microsoft-activity-7442430544245661696-9Zmy), [Token claims reference for agents](https://learn.microsoft.com/en-us/entra/agent-id/identity-platform/agent-token-claims)
* <https://github.com/davidalonsod/Dalonso-Security-Repo/tree/main/Use%20Cases%20Threat%20Hunting/Non-Human_Identities_Detections>
* [How Storm-2949 turned a compromised identity into a cloud-wide breach, May 2016](https://www.microsoft.com/en-us/security/blog/2026/05/18/storm-2949-turned-compromised-identity-into-cloud-wide-breach/)
