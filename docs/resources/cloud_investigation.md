# Cloud Investigation

## References

* [Suzaku (朱雀) is a sigma-based threat hunting and fast forensics timeline generator for cloud logs. ](https://github.com/Yamato-Security/suzaku)
* https://nathanmcnulty.com/blog/2025/04/comprehensive-guide-to-configuring-advanced-auditing/
* https://github.com/nccgroup/ScoutSuite (AWS, Azure, GCP...)
* https://docs.prowler.com/projects/prowler-open-source/en/latest/# (AWS, Azure, GCP...)

* https://andreafortuna.org/2023/01/16/my-own-list-of-tools-to-perform-incident-response-against-azure-ad-and-microsoft-365
* https://github.com/AzureAD/Azure-AD-Incident-Response-PowerShell-Module
* https://github.com/invictus-ir/Microsoft-Extractor-Suite
* [An Azure SPN access minimizer](https://github.com/labyrinthinesecurity/silhouette/)
* https://github.com/WillOram/AzureAD-incident-response
* [Untitled Goose Tool Aids Hunt and Incident Response in Azure, Azure Active Directory, and Microsoft 365 Environments, Mar 2023](https://www.cisa.gov/news-events/alerts/2023/03/23/untitled-goose-tool-aids-hunt-and-incident-response-azure-azure-active-directory-and-microsoft-365), https://github.com/cisagov/untitledgoosetool
* https://github.com/mandiant/Mandiant-Azure-AD-Investigator
* https://github.com/T0pCyber/hawk
* https://github.com/CrowdStrike/CRT
* https://github.com/PwC-IR/Office-365-Extractor
* https://github.com/SpecterOps/AzureHound
* https://medium.com/@rajendraprasanth/cloud-incident-forensic-response-part3-azure-and-m365-fabe6dcbcef2
* [Microsoft 365, Azure subscriptions and Microsoft Entra ID security configuration reviews](https://github.com/silverhack/monkey365)
* [Microsoft Teams New Audit Log Feature Allows Admins to Track Users Actions, Jun 2025](https://cybersecuritynews.com/microsoft-teams-audit-log/)
* [Belshazaar is a command-line tool for analyzing Azure Role-Based Access Control (RBAC) actions to detect overly broad wildcard permissions.](https://github.com/labyrinthinesecurity/silhouette/tree/2.1/formal)
* [MAES: M365 Analyzer & Extractor Suite](https://github.com/ionsec/maes-platform)
* [Insights from the trenches: building audit capacity for Microsoft Sentinel & Defender XDR](https://www.michalos.net/2025/06/20/insights-from-the-trenches-building-audit-capacity-for-microsoft-sentinel-defender-xdr/)
* [How to check if audit logging is enabled:](https://www.linkedin.com/posts/chaim-black_imagine-buying-a-home-with-a-full-camera-activity-7348796040176685056-Fpj6/), <https://security.microsoft.com/auditlogsearch>
* [Maester, Your Microsoft Security test automation framework!](https://maester.dev/)
* [ScubaGear, Automation to assess the state of your M365 tenant against CISA's baselines](https://github.com/cisagov/ScubaGear)
* [lightweight security testing tool that checks if Microsoft Entra ID (Azure AD) APIs and login portals allow password-only authentication ](https://github.com/NotSoSecure/NoPrompt), <https://www.claranet.com/us/blog/noprompt-%E2%80%94-detect-mfa-conditional-access-gaps-entra-id>
* [Microsoft-Analyzer-Suite (Community Edition) A collection of PowerShell scripts for analyzing data from Microsoft 365 and Microsoft Entra ID.](https://github.com/LETHAL-FORENSICS/Microsoft-Analyzer-Suite)

* [I’m an Incident Responder on the AWS Customer Incident Response Team (CIRT). And I get asked a lot of questions, like:“Where do I even start with incident response in the cloud?”Here’s a beginner-friendly thread on AWS IR tips — with a few lessons I learned 🧵👇 /THREAD, Apr 2025](https://x.com/4n6lady/status/1917627609741156368): CloudTrail all regions, monitor root account, enable guardduty, tag resources, snapshot first, baseline, start small, save logs...
* [Tales from the cloud trenches: The Attacker doth persist too much, methinks, May 2025](https://securitylabs.datadoghq.com/articles/tales-from-the-cloud-trenches-the-attacker-doth-persist-too-much/) AWS
* Awesome work by the folks at AWS that implemented this! AWS now prevents OIDC misconfigurations with many popular third-parties. https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_oidc_secure-by-default.html
This is an issue I described here: https://www.wiz.io/blog/avoiding-mistakes-with-aws-oidc-integration-conditions
https://bsky.app/profile/scottpiper.bsky.social/post/3lr72k25qt227
https://github.com/aws-samples/resource-control-policy-examples
* [Get visibility into the IAM permissions in your AWS organizations and accounts](https://github.com/cloud-copilot/iam-lens)
* [Go library, server, and CLI providing foundational capabilities to simulate access for AWS IAM policies.](https://nsiow.github.io/yams/)

* https://cloud.google.com/architecture/framework/security
* [How to Actually Security Benchmark Your Microsoft 365 Tenant, Sep 2025](https://ourcloudnetwork.com/how-to-actually-security-benchmark-your-microsoft-365-tenant/):  Maester, Scubgear (free), Avepoint, Inforcer, Coreview (paid)
* [How Google Does It: Collecting and analyzing cloud forensics, Dec 2025](https://cloud.google.com/transform/how-google-does-it-collecting-and-analyzing-cloud-forensics): grr, plaso, timesketch, dftimewolf...

* [Granular, Actionable Adversary Emulation for the Cloud](https://github.com/DataDog/stratus-red-team)
* [Cloud Offensive Breach and Risk Assessment (COBRA) Tool](https://github.com/PaloAltoNetworks/cobra-tool)
* [EasyPIM let you manage PIM Azure Resource, Entra Role and Groups settings and assignments with simplicity](https://github.com/kayasax/EasyPIM)
* [Audit administrator events in Microsoft Entra Connect Sync](https://learn.microsoft.com/en-us/entra/identity/hybrid/connect/admin-audit-logging)

Cloud disk encryption (managed or customer)
* [Overview of managed disk encryption options (VM) - Azure](https://learn.microsoft.com/en-us/azure/virtual-machines/disk-encryption-overview): ADE (Scheduled for retirement on Sep 2028), SSE (PMK or CMK), Encryption at Host, Confidential disk encryption
* [Computer forensics chain of custody in Azure](https://learn.microsoft.com/en-us/azure/architecture/example-scenario/forensics/), <https://github.com/Azure/forensics>
* [Forensicating Azure VMs, Feb 2021](https://isc.sans.edu/diary/27136)
* [Can a managed disk with server-side encryption using platform managed keys be exported and imported to a VM on a different tenant. Or, are PMKs tenant specific? Dec 2022](https://learn.microsoft.com/en-us/answers/questions/1113949/can-a-managed-disk-with-server-side-encryption-usi), <https://stackoverflow.com/questions/70354057/azure-blobstorage-sas-token-urls-that-decrypt-data#comment124367652_70354057> "Something is missing. Are you using SSE (server side encryption) or client-provided key encryption? With SSE the encryption should be transparent and you should get decrypted content independent of the way you access the content (DownloadTextAsync or SAS url).", [Export Azure Platform Managed Key Encrypted VM, Feb 2024](https://www.reddit.com/r/AZURE/comments/1ak63au/export_azure_platform_managed_key_encrypted_vm/)
