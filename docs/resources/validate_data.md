

# References

* [Handbook for Safeguarding Sensitive PII, Dec 2017](https://www.dhs.gov/sites/default/files/publications/dhs policy directive 047-01-007 handbook for safeguarding sensitive PII 12-4-2017.pdf)

## Detection

It can apply to secrets, credentials, PII, PHI, Contracts & legal documents, Invoice & billing documents...

* bulk_extractor
* Detect-Secrets
* TruffleHog
* https://github.com/adobe/stringlifier

Eventually if prepared, sensitive files can have specific marking:
* Confidentiality level
* Watermarking
* Source code banner
* Other signature mechanism

## Validation

* Credentials:
  Match existing requirements
  Match hash
  offline database, haveibeenpwned...

FIXME! overlap with data_validation.md

## Products

Opensource
* [scanner for PII and PHI information. It finds PII data in your databases](https://pypi.org/project/piicatcher/), Commercial support https://tokern.io/piicatcher/
* [EarlyBird is a sensitive data detection tool capable of scanning source code repositories for clear text password violations, PII, outdated cryptography methods, key files and more. ](https://github.com/americanexpress/earlybird)
* [R code to scan for obvious ](https://github.com/J-PAL/PII-Scan)
* [piihunter is a sensitive unencrypted data detection tool built to scan source code repositories for plaintext passwords, tokens, weak cryptography usage, private keys, emails, phone numbers, addresses, zip codes etc](https://github.com/offensivedev/piihunter) - Last commit May 2021
* [Scan your data stores for unencrypted personal data (PII)](https://github.com/ankane/pdscan) - Last commit Dec 2020
* [detector makes detecting data containing Personally Identifiable Information (PII) quick, easy, and scalable. - R](https://github.com/paulhendricks/detector), Warning: last commit 2017
* [CUSpider - PII Scanning Application. Win only](https://cuit.columbia.edu/content/cuspider-pii-scanning-application)
* [Discover PII sensitive data. Golang](https://github.com/oxytis/oxidize) - Warning: No code???
* [A package to build an end-to-end ML pipeline to detect personally identifiable information (PII) from text. alpha](https://pypi.org/project/piidetect/)
* [Fluentd filter output plugin to anonymize records with MD5/SHA1/SHA256/SHA384/SHA512 algorithms. This data masking plugin protects privacy data such as ID, email, phone number, IPv4/IPv6 address and so on. ](https://github.com/y-ken/fluent-plugin-anonymizer)
* [PII and Your Logs: Managing Log Data with Loggly and Fluentd, Jan 2015](https://www.loggly.com/blog/pii-logs-managing-log-data-loggly-fluentd/)
* [Why IP address truncation fails at anonymization, Oct 2025](https://00f.net/2025/10/27/ip-anonymization/), [Methods for IP Address Encryption and Obfuscation](https://github.com/ipcrypt-std/draft-denis-ipcrypt)


Commercial
* [How to detect and redact Personally Identifying Information (PII)](https://docs.microsoft.com/en-us/azure/cognitive-services/language-service/personally-identifiable-information/how-to-call)
* [Quickstart: Detect Personally Identifiable Information (PII)](https://docs.microsoft.com/en-us/azure/cognitive-services/language-service/personally-identifiable-information/quickstart?pivots=programming-language-csharp)
* [PII Detection Action](https://github.com/marketplace/actions/pii-detection) with Azure Cognitive service
* [Control PII and Sensitive Data Risk for Self-Service BI using Power BI DataFlows and Azure Data Lake, Nov 2019](https://techcommunity.microsoft.com/t5/healthcare-and-life-sciences/control-pii-and-sensitive-data-risk-for-self-service-bi-using/ba-p/1018486)
* [Azure Purview is a unified data governance solution that helps you manage and govern your on-premises, multicloud, and software-as-a-service (SaaS) data. Easily create a holistic, up-to-date map of your data landscape with automated data discovery, sensitive data classification, and end-to-end data lineage. Enable data consumers to find valuable, trustworthy data.](https://azure.microsoft.com/en-us/services/purview/#overview)
* [Detecting and redacting PII using Amazon Comprehend, Sep 2020](https://aws.amazon.com/blogs/machine-learning/detecting-and-redacting-pii-using-amazon-comprehend/)
* [Slack Security: How to Detect PII & Prevent Data Exfiltration in Slack, Feb 2020](https://nightfall.ai/slack-security-detect-pii-prevent-data-exfiltration)
* [How to Detect PII Data Flows, Nov 2021](https://www.bionic.ai/blog/identify-pii-data-flows/)
* [PII Tools](https://pii-tools.com)
* [Moderate and filter user texts in real-time with our API. ](https://sightengine.com/text-moderation-api)

* [Top PII Data Discovery Tools, May 2021](https://blog.rsisecurity.com/top-pii-data-discovery-tools/): OneTrust, Nightfall, Egnyte, Windows Server File Classification Infrastructure (FCI), Azure Information Protection (AIP), Netwrix Auditor
* [Best practices to avoid sending Personally Identifiable Information (PII), Google Analytics](https://support.google.com/analytics/answer/6366371?hl=en)
* [Remove hidden data and personal information by inspecting documents, presentations, or workbooks](https://support.microsoft.com/en-us/topic/remove-hidden-data-and-personal-information-by-inspecting-documents-presentations-or-workbooks-356b7b5d-77af-44fe-a07f-9aa4d085966f)

* Data Classification & Forensics: ideally ownership, confidentiality level, compliance, information type, countries and customers are tagged and easily available for review. Ideally, those metadata can have policies attach affecting retention, encryption requirement, IP+identification allow/deny...
  * https://learn.microsoft.com/en-us/microsoft-365/compliance/data-classification-overview?view=o365-worldwide
    * https://learn.microsoft.com/en-us/microsoft-365/compliance/data-classification-activity-explorer-available-events?view=o365-worldwide
    * https://www.netwrix.com/how_to_audit_data_access_in_teams_and_sharepoint_online.html
    * https://learn.microsoft.com/fr-fr/previous-versions/windows/powershell-scripting/jj900651(v=wps.630)?redirectedfrom=MSDN
  * https://help.libreoffice.org/latest/en-US/text/shared/guide/classification.html
    * `exiftool -a ~/QubesIncoming/libreoffice-test-classification-bails.ods  |grep -aiE '(internal|bails|tscp)'`
    * `unzip -aa -c libreoffice-test-classification-bails.ods  | grep -aiE '(internal|bails|tscp)'`
  * https://owncloud.com/features/document-classification/
  * https://doc.owncloud.com/server/next/admin_manual/enterprise/document_classification/classification_and_policy_enforcement.html
  * Data Protection overview https://support.apple.com/en-ca/guide/security/secf6276da8a/1/web/1; Data Protection classes https://support.apple.com/en-ca/guide/security/secb010e978a/web;
    * https://developer.apple.com/documentation/foundation/nsfileprotectioncomplete
    * https://stackoverflow.com/questions/36577647/why-does-nsfileprotectioncomplete-not-work
    * `xattr -l itempath` - https://eclecticlight.co/2020/10/24/theres-more-to-files-than-data-extended-attributes/

* Find SSNs - VirginiaTeach, Mar 2009 https://security.vt.edu/software/Find_SSNs.html
* Find Restricted Information: SENF https://community.pepperdine.edu/it/security/ric/findsenf.htm), Find Restricted Information: SENF https://community.pepperdine.edu/it/security/ric/findsenf.htm
* CUSpider - PII Scanning Application https://www.cuit.columbia.edu/content/cuspider-pii-scanning-application
* https://github.com/swarleysez/Find-SensitiveData, Dec 2020
* Search for sensitive content in SharePoint and OneDrive documents, Aug 2014 https://www.microsoft.com/en-us/microsoft-365/blog/2014/08/27/search-sensitive-content-sharepoint-onedrive-documents/
