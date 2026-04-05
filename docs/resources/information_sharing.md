# Information sharing

## Workflow

* Pre-approved cases
IOC (hash, domain, IP address, url, email, yara rule, sigma rule, snort rule...) - only if external, non-identified to company

* CISO approval

* Legal approval
C-Suite, Employee or customer/partner data

Examples
| Data type | Approval | Communication channel |
| --------- | -------- | --------------------- |
| Sharing of public resources | Pre-approved | Any |
| Url non-targeted phishing report | Pre-approved | Google SafeBrowsing, Netcraft, Phishtank... |
| Non-targeted IOC (external data) | Manager | Authorized TIP and tool (MISP, Signal, file sharing, private security mailing-list & communities like FIRST and ISAC, National CERT ...) |
| Targeted attack IOC | Director | Authorized TIP and higher security level tool |
| Third-party compromise | CISO | Phone |
| Company compromise, IOC Internal data | Legal, External counsel | Per legal review |
| Detection rules (sigma, yara...) | ? | ? |
| Security tools (contribution existing, new...) | ? | ? |
| General security architecture and tools feedback or advices except sensitive ones | Pre-Approved | Any |

Incident data can also be matched based on severity level.

## Store data

## Transfer data

## Destroy data

## Technical data

* TLP
* Type
* If email, subject/sender/phishing url/exfiltration to/email body observed, supporting evidence/sandbox url

## References

* [Information Sharing, US DHS](https://www.dhs.gov/information-sharing)
* [Information Sharing and Awareness, US CISA](https://www.cisa.gov/information-sharing-and-awareness)
* [Information Sharing and Analysis Centers (ISACs), ENISA](https://www.enisa.europa.eu/topics/national-cyber-security-strategies/information-sharing)
* [Cyber incident reporting guidelines: Key information sharing requirements – ITSM.00.140](https://www.cyber.gc.ca/en/guidance/cyber-incident-reporting-guidelines-key-information-sharing-requirements-itsm00140)

* [Good Practice Guide on Information Sharing, ENISA, 2009](https://www.enisa.europa.eu/publications/good-practice-guide)
* [Privacy and Civil Liberties Final Guidelines: Cybersecurity Information Sharing Act of 2015](https://us-cert.cisa.gov/sites/default/files/ais_files/Privacy_and_Civil_Liberties_Guidelines.pdf), [Federal Guidance on the Cybersecurity Information Sharing Act of 2015](https://corpgov.law.harvard.edu/2016/03/03/federal-guidance-on-the-cybersecurity-information-sharing-act-of-2015/)
* [A Framework for Effective Corporate Communication after Cyber Security Incidents, Oct 2020](https://arxiv.org/ftp/arxiv/papers/2009/2009.09210.pdf) - p26, fig6, Refined framework
* [CISA has shared "all of the information we have" about SolarWinds and Exchange "at the unclassified level, save one small piece related to attribution," Wales says, "and frankly, that [piece] is not going to help a single network defender improve their security." Mar 2021](https://twitter.com/ericgeller/status/1374403586554138626)
