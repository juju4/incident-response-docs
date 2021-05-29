
Base analysis of file (not reverse-engineering)

!!! warning "Operations Security aka Opsec ?"
    Please be careful on **Opsec** and dont upload confidential files on Internet.

## Generic File

* Review public and private reports by hash search
    * Generate hash on Windows: `Get-FileHash`
    * Generate hash on Macos: `shasum`
    * Generate Import hash for PE files: [ImpHash-Generator](https://github.com/Neo23x0/ImpHash-Generator) (Python)

* Use command-line tools, mostly on Linux and Macos
    * `file`, `strings`, `grep`...
    * Windows [Sysinternals strings](https://docs.microsoft.com/en-us/sysinternals/downloads/strings)
    * Python [python-magic](https://pypi.org/project/python-magic/)
    * exiftool and similar for Images

See references for few tools relevant to MsOffice, PDF or Image files

## Executable File

* Review meta-data
* Review signature if available
    * Windows > Properties
    * Windows file on Linux, Macos: use [Didier Steven's disitool](https://blog.didierstevens.com/2008/01/11/the-case-of-the-missing-digital-signatures-tab/) and openssl
    * Macos file: use codesign cli tool

## Sandbox

Whatever the tool, ensure that sandboxing is isolated from your network and from Internet.

### Internal sandbox

Whatever is relevant in your context

* [Open source automated malware analysis system](https://cuckoosandbox.org)
* [IRMA is an asynchronous & customizable analysis system for suspicious files.](https://github.com/quarkslab/irma)
* [Noriben - Portable, Simple, Malware Analysis Sandbox ](https://github.com/Rurik/Noriben)

### External sandbox

* [Free Automated Malware Analysis Sandboxes and Services](https://zeltser.com/automated-malware-analysis/)
* [VirusTotal](https://www.virustotal.com/)
* [Hybrid Analysis](https://www.hybrid-analysis.com)
* [Joe Sandbox Cloud](https://www.joesandbox.com)

## References

* [TotalHash, Team Cymru](https://totalhash.cymru.com/)

* Collection of [Didier Steven's PDF tools](https://blog.didierstevens.com/programs/pdf-tools/)
* MsOffice tools: [oletools](https://github.com/decalage2/oletools), [oletools' mraptor](https://github.com/decalage2/oletools/wiki/mraptor)

* [Malware Analysis Fundamentals - Files | Tools, Jun 2020](https://www.winitor.com/pdf/Malware-Analysis-Fundamentals-Files-Tools.pdf)

* [Photo Tampering throughout History](http://pth.izitru.com)
* [Photo Forensics](https://29a.ch/photo-forensics/)
* [GIMP-ELA, A JPEG Error Level Analysis forensic plugin for the GNU Image Manipulation Program (GIMP)](https://github.com/sentenza/GIMP-ELA)
* [detect stegano-hidden data in PNG & BMP](https://github.com/zed-0xff/zsteg)

* [Malware Delivered via Windows Installer Files, Feb 2018](https://isc.sans.edu/diary/Malware+Delivered+via+Windows+Installer+Files/23349)
