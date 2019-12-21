
Security systems contains large information data that can be requested by user as part of

* GDPR Subject Access Request, Europe
* PIPEDA, Canada
* CCPA, California, United-States

## Scope

Review with user:

* scope if possible. That will limit search and allow to answer faster.
* identity. Ensure user is correctly identified depending on how it was initially (if only nickname and email, if identity documents...)

Depending on security context, search by identifier, name, login and hostname if applicable.

* Processed data
    * Ticketing (multiple if applicable)
    * HR tools
    * Business tools
    * Other

* Raw data
    * Network: IDS/IPS, DNS, Proxy
    * Host: AV, EDR
    * Smartphones
    * Directory: Active Directory, LDAP
    * Mail: antispam/mail gateway (all, only with management, with customers...)
    * Cloud: O365, Azure, AWS...
    * CCTV
    * Other

## Target

Export must be in a readable format, text (csv, json...) or common (OpenOffice, MsOffice...)
Files should be compressed and have a hash generated.
Transfer should be done in a secure manner (not email unless encryption)

Export must be validated by approved party to ensure it does not contain confidential information like PII of other users or company's Intellectual property. Else, it should be redacted.

## References

* [Black Hat: GDPR privacy law exploited to reveal personal data, BBC, Aug 2019](https://www.bbc.co.uk/news/technology-49252501)
* [Five tips for managing data subject access requests under GDPR, Jul 2019](https://bhconsulting.ie/five-tips-data-subject-access-requests-gdpr/)
* [What I Learned About Security from Calling 35 Contact Centers, Twilio, Feb 2019](https://www.twilio.com/blog/learned-about-security-from-calling-35-contact-centers)
* [Responding to subject access requests, Dec 2017](https://iapp.org/news/a/responding-to-subject-access-requests/)
* [The Nightmare Letter: A Subject Access Request under GDPR, Mar 2017](https://www.linkedin.com/pulse/nightmare-letter-subject-access-request-under-gdpr-karbaliotis)

* [Responding to access to information requests under PIPEDA, Feb 2014](https://www.priv.gc.ca/en/privacy-topics/accessing-personal-information/obligations-for-organizations/02_05_d_54_ati_02/)
* [Right of access, UK ICO](https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/individual-rights/right-of-access/)

* [Art. 15 GDPR Right of access by the data subject](https://gdpr-info.eu/art-15-gdpr/)

* [Office 365 Data Subject Requests for the GDPR](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-office365)
* [How To Perform a Data Subject Access Request in Office 365](https://www.slashadmin.co.uk/how-to-perform-a-data-subject-access-request-in-office-365/)
* [Azure Data Subject Requests for the GDPR](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-azure)

