
## Definition

Cloud credentials compromised is common for home user but for enterprise, it is becoming more prevalent with Google Apps for Business, Microsoft Office 365 and others.
Amazon, Github are also concerned

## Course of Action

* Review compromission state
    * main access, alternate (application password, oauth...)
    * Forwarding message rules
    * confirm if malicious
    * check impact
* Do backup of evidence, especially if legal actions are planned
* Reset all access
    * password
    * tokens/api keys
* Eventually, report to provider. Might be required if large impact like billing.
* Notify affected users (owner or person impacted by abuse)
    * Ensure preventative actions are done (2FA, Awareness, Audit&alerts, watch for leaked secret keys...)

## References

Tools

* [Recover a hijacked or stolen Google Account](https://support.google.com/accounts/answer/6294825?hl=en)
* [How to fix a compromised (hacked) Microsoft Office 365 account, Dec 2015](https://blogs.technet.microsoft.com/office365security/how-to-fix-a-compromised-hacked-microsoft-office-365-account/), [O365-InvestigationTooling, Github](https://github.com/OfficeDev/O365-InvestigationTooling/)
* [My AWS account may be compromised](https://aws.amazon.com/premiumsupport/knowledge-center/potential-account-compromise/)
* [Keeping your account and data secure, GitHub](https://help.github.com/articles/keeping-your-account-and-data-secure/)
* [Recovering from systemic identity compromise](https://docs.microsoft.com/en-us/azure/security/fundamentals/recover-from-identity-compromise)
* [Removing sensitive data from a repository](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository): `git filter-repo`, [BFG Repo-Cleaner](https://rtyley.github.io/bfg-repo-cleaner/)

* Reset passwords and sessions/cookies
  * https://www.newswire.com/news/new-report-from-flare-highlights-significant-costs-and-industry-impact-22553863
  * https://learn.microsoft.com/en-us/entra/identity/users/users-revoke-access
  * https://learn.microsoft.com/en-us/answers/questions/834400/process-to-remove-login-access-and-close-all-login
  * https://www.egroup-us.com/news/revoke-all-user-sessions-for-azure-ad-and-office-365/
  * https://support.google.com/a/answer/178854?hl=en
  * https://developers.google.com/identity/gsi/web/guides/revoke
  * [Windows RDP lets you log in using revoked passwords. Microsoft is OK with that. Apr 2025](https://arstechnica.com/security/2025/04/windows-rdp-lets-you-log-in-using-revoked-passwords-microsoft-is-ok-with-that/)
