
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
    * tokens
* Eventually, report to provider. Might be required if large impact like billing.
* Notify affected users (owner or person impacted by abuse)
    * Ensure preventative actions are done (2FA, Awareness, Audit&alerts, watch for leaked secret keys...)

## References

Tools

* [Recover a hijacked or stolen Google Account](https://support.google.com/accounts/answer/6294825?hl=en)
* [How to fix a compromised (hacked) Microsoft Office 365 account, Dec 2015](https://blogs.technet.microsoft.com/office365security/how-to-fix-a-compromised-hacked-microsoft-office-365-account/), [O365-InvestigationTooling, Github](https://github.com/OfficeDev/O365-InvestigationTooling/)
* [My AWS account may be compromised](https://aws.amazon.com/premiumsupport/knowledge-center/potential-account-compromise/)
* [Keeping your account and data secure, GitHub](https://help.github.com/articles/keeping-your-account-and-data-secure/)
