# Client compromise (End-user system)

## Definition

User system compromise, including

* Phishing
* Malware
* Ransomware
* Data Breach

## Course of Action

* Check system information
  * Owner? VIP? criticity? backup? time to rebuild?
  * Department? Finance, HR, IT, Security...
  * Data hosted on system or related systems (Onedrive, Sharepoint...)
  * User activity, UEBA, possible multiple identities...
  * Network activity
  * Performance activity
  * Security tools coverage
  * Logs activity from central logging if applicable
  * Possible blast radius of incident
* Collect live artifacts
  * EDR (Crowdstrike RTR, MDE LiveResponse...)
  * Memory if not previously
  * Extra captures like tcpdump, procmon, sysdig...
  * Other live artifacts: MFT, Prefetch, ...
* Collect end-user feedback
  * Abnormal activity
  * Abnormal event (call, found usb key/DVD...)
* Decide whether early management notification or escalation is needed or not, if not done earlier
* Eventually, collect disk(offline) artifacts
* Use sandbox to investigate binaries and urls
* Cross-check indicators of compromise and behaviors with your local and shared threat intelligence
  * Other systems infected? repeat.
  * Attacker communication channels
  * What, when, how. how it enters, how it persists.
* Quarantine or disconnect systems
  * With approval or not depending on applicable process
* Rotate credentials for affected identities, confirmed or potential
* Decide if surgical eradication is possible or system should be reimaged
* Review if possible countermeasures to prevent infection or detect it faster
  * Validate if applicable during incident or if should be in post-mortem action (signature update, firewall block, registry change...)

## References

* [CERT SG IRM-2-WindowsIntrusion](https://github.com/certsocietegenerale/IRM/blob/main/EN/IRM-2-WindowsIntrusion.pdf)
* [CERT SG IRM-7-WindowsMalwareDetection](https://github.com/certsocietegenerale/IRM/blob/main/EN/IRM-7-WindowsMalwareDetection.pdf)
* [Malware Playbook](https://gitlab.com/syntax-ir/playbooks/-/tree/main/IRP-Malware)
* [Malware triage with MISP](https://github.com/MISP/misp-playbooks/blob/main/misp-playbooks/pb_malware_triage.ipynb)

* [The Nevada's Ransomware Mystery From 2025: What Really Happened? Nov 2025](https://rohittamma.substack.com/p/the-nevadas-ransomware-mystery-from): "Quarantine removed the original file but not these persistent mechanisms"

### Data collection

* [KAPE by Eric Zimmerman](https://www.kroll.com/en/insights/publications/cyber/kroll-artifact-parser-extractor-kape), [repository for community created Targets and Modules for use with KAPE](https://github.com/EricZimmerman/KapeFiles), [Using KAPE with CrowdStrike Falcon (Real Time Response)](https://ericzimmerman.github.io/KapeDocs/#!Pages\60-Tips-and-tricks.md)
Recommendation: run from share, results locally and after sent to server (SMB, [SFTP](http://www.mashthatkey.com/2019/10/use-kape-to-collect-data-remotely-and.html)...)

```shell
> .\kape.exe --tsource \\RemoteEndpoint\C$ --tdest E:\kape --target WebBrowsers --gui --tvars user:JohnDoe
> PsExec64.exe -s E:\kape\Kape.exe --msource G: --module MSFTallScan --mdest E:\kape\parsed
```

* [Forensic Artifact Collection Tool Matrix - Win, Linux, Swisscom, Dec 2020](https://github.com/swisscom/ArtifactCollectionMatrix)
