Suspicious system can lead to a server compromiser or follow a phishing.
You are at the point where you question the integrity of a system and if it should be trusted.

## Definition
Suspicious system is a wide case representing abnormal reactions of the system or possible compromise.
It includes

* Malware
* Ransomware
* Server compromise
* Data Breach

## Course of Action

* Check system information
    * owner? criticity? backup? time to rebuild?
    * network activity
    * performance activity
    * logs activity from central logging
    * Cloud console information.
      Ex: Azure Security Center, Policy, Networking...
* Collect live artifacts
    * live snapshot if virtualized (vmware disk+memory, azure disk...)
    * memory if not previously
    * extra captures like tcpdump, procmon, sysdig...
    * other live artifacts: MFT, Prefetch, ...
* Collect user feedback
    * abnormal activity
    * abnormal event (call, found usb key/DVD...)
* Eventually, collect disk(offline) artifacts
* Use sandbox to investigate binaries and urls
* Cross-check indicators of compromise and behaviors with your local and shared threat intelligence
    * other systems infected? repeat.
    * attacker communication channels
    * what, when, how. how it enters, how it persists.
* Quarantine or disconnect systems
* Review if possible countermeasures to prevent infection or detect it faster
    * validate if applicable during incident or if should be in post-mortem action (signature update, firewall block, registry change...)

## References

* [TR-22 - Recommendations for Readiness to Handle Computer Security Incidents, CIRCL.LU](https://circl.lu/pub/tr-22/)
* [If you aren’t performing memory analysis then you are doing your clients & org a disservice, @attrc, jun 2016](https://twitter.com/attrc/status/742399097206771712)
* [Reqs for effective #DFIR, Why Threat Hunting, Why Memory Forensics, @attrc, nov 2016](https://twitter.com/attrc/status/793875121022832640)
* [I’m very concerned by the number of people in your mentions who think memory dumps aren’t necessary. My hope is they are mistaking IR for meaning “malware cleanup”. Feb 2021](https://twitter.com/MalwareTechBlog/status/1365358152133185537), [If you're not getting a memory dump, you're leaving evidence on the table. While I understand you can't always get memory because of constraints (e.g. system was powered off before you were involved), you shouldn't be planning to leave evidence behind either. Feb 2021](https://twitter.com/MalwareJake/status/1365362315365912578)
* [Important #DFIR tip!!!
Recovering MFT entries from memory does *NOT* just duplicate what is on disk! You also get:
- Entries of deleted files that are overwritten in $MFT
- Entries from *previously* attached NTFS-formatted removable media
- Entries from encrypted stores, Mar 2021](https://twitter.com/attrc/status/1208031451859619840)
* [Adversaries are looking at how to persist post-exploitation. One of the easiest ways is credential harvesting. There’s plenty of enduring intrusion operations where the focus of the effort is gaining and maintaining access. Patching isn’t enough. Investigate intrusions.👈🏼, Mar 2021](https://twitter.com/anthomsec/status/1368277575655714817)
* [Volatility](http://www.volatilityfoundation.org/)
* [Rekall](https://github.com/google/rekall/)
* [DumpIt - Your favorite Memory Toolkit is back… FOR FREE! Jun 2016](https://blog.comae.io/your-favorite-memory-toolkit-is-back-f97072d33d5c)
* [Loki](https://github.com/Neo23x0/Loki)
* [FastIR](https://github.com/SekoiaLab/FastIR_Collector)
* [OSX Collector](https://github.com/Yelp/osxcollector)
* [AutoMacTC: Automated Mac Forensic Triage Collector](https://github.com/CrowdStrike/automactc)
* [CSIRT-Collect, Windows Powershell](https://github.com/dwmetz/CSIRT-Collect)
* [Microsoft Safety Scanner](https://docs.microsoft.com/en-us/windows/security/threat-protection/intelligence/safety-scanner-download)
* [Alert (AA21-077A) Detecting Post-Compromise Threat Activity Using the CHIRP IOC Detection Tool, Mar 2021](https://us-cert.cisa.gov/ncas/alerts/aa21-077a)
* [Forensic Artifact Collection Tool Matrix](https://github.com/swisscom/ArtifactCollectionMatrix)
* [Forensic helper scripts for KAPE and RegRipper](https://github.com/swisscom/Invoke-Forensics)
* [Scan for HAFNIUM Exploitation Evidence with THOR Lite, Mar 2020](https://www.nextron-systems.com/2021/03/06/scan-for-hafnium-exploitation-evidence-with-thor-lite/)
* [Adware the series, the final: Tools section, Jul 2017](https://blog.malwarebytes.com/puppum/2017/07/adware-the-series-the-final-tools-section/)
* [Linux Compromise Assessment Command Cheat Sheet, Nov 2018](https://www.sandflysecurity.com/wp-content/uploads/2018/11/Linux.Compromise.Detection.Command.Cheatsheet.pdf)
* https://github.com/austinsonger/Incident-Playbook
* [Triage with Velociraptor  Pt 3, Oct 2019](https://docs.velociraptor.app/blog/2019/2019-10-08_triage-with-velociraptor-pt-3-d6f63215f579/)
* [Thor Lite, Nextron systems](https://www.nextron-systems.com/thor-lite/), [`-a ProcessCheck` Process Memory only](https://twitter.com/cyb3rops/status/1501821636621873156)
* [YaraMemoryScanner - Windows Powershell](https://github.com/BinaryDefense/YaraMemoryScanner)
* [triage.zip provides an out-of-the-box Velociraptor triage collector for Windows, pre-configured for rapid and effective incident response. The project is intended for responders who need a reliable offline collector without the hassle of building from scratch.](https://github.com/Digital-Defense-Institute/triage.zip)
* [WTFBin (n): a benign application that exhibits malicious behavior. These applications tend to confuse and alarm security analysts during incident response. This project exists to identify, catalog, and lightly poke fun at these applications, in the hopes that we can make analysts' lives just a little bit better.](https://wtfbins.wtf/)
* [Velociraptor Deployment Automation System](https://github.com/N1ghtFury74/Scripts/tree/main/VDA)

### Data collection

* [KAPE by Eric Zimmerman](https://www.kroll.com/en/insights/publications/cyber/kroll-artifact-parser-extractor-kape), [repository for community created Targets and Modules for use with KAPE](https://github.com/EricZimmerman/KapeFiles), [Using KAPE with CrowdStrike Falcon (Real Time Response)](https://ericzimmerman.github.io/KapeDocs/#!Pages\60-Tips-and-tricks.md)
Recommendation: run from share, results locally and after sent to server (SMB, [SFTP](http://www.mashthatkey.com/2019/10/use-kape-to-collect-data-remotely-and.html)...)
```
> .\kape.exe --tsource \\RemoteEndpoint\C$ --tdest E:\kape --target WebBrowsers --gui --tvars user:JohnDoe
> PsExec64.exe -s E:\kape\Kape.exe --msource G: --module MSFTallScan --mdest E:\kape\parsed
```
* [Forensic Artifact Collection Tool Matrix - Win, Linux, Swisscom, Dec 2020](https://github.com/swisscom/ArtifactCollectionMatrix)
* [When you should perform a Live Acquisition + the risks; these factors should always be considered prior to performing one during an investigation.Not so mini thread, Jul 2021](https://twitter.com/4n6lady/status/1411017778593677317)

### Virtual Machines

* [Vmware](https://github.com/volatilityfoundation/volatility/wiki/VMware-Snapshot-File), Eventually convert to [core memory dump](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2003941).
```
esxi$ vim-cmd vmsvc/snapshot.create <VM_ID> <SNAPSHOT_NAME>
esxi$ vim-cmd vmsvc/snapshot.get <VM_ID>
workstation$ vmrun snapshot <PATH TO VMX FILE> <SNAPSHOT_NAME>
workstation$ vmrun listSnapshots <PATH TO VMX FILE>
```
Alternatives: [Cmdlet New-Snapshot](https://pubs.vmware.com/vsphere-6-0/index.jsp#com.vmware.powercli.cmdletref.doc/New-Snapshot.html), [vmsnapshot.pl](https://pubs.vmware.com/vsphere-6-0/index.jsp#com.vmware.perlsdk.uaref.doc/vmsnapshot.html)
* [Virtualbox](https://github.com/volatilityfoundation/volatility/wiki/Virtual-Box-Core-Dump): [debugvm](https://www.virtualbox.org/manual/ch08.html#vboxmanage-debugvm)
```
live$ VBoxManage debugvm <uuid|vmname> dumpvmcore [--filename=name]
atstart$ VirtualBox --dbg --startvm <VM name>
atstart dbg> .pgmphystofile
```
* [Parallel](http://kb.parallels.com/en/121323)
```
prlctl list -a
prlctl start {<VM_UID>}
prlctl internal {<VM_UID>} dbgdump --path /path/to/target/dir/
```

### Containers

* [CSI: Container Edition - forensics in the age of containers, Aug 2017](https://www.stackrox.com/post/2017/08/csi-container-edition---forensics-in-the-age-of-containers/)
    * ```docker commit $CONTAINER_ID imagename```
    * memory: ```gcore $PID```, objdump, dd...
* [Forensicating Docker, Part 1, Mar 2016](https://isc.sans.org/forums/diary/Forensicating+Docker+Part+1/20835)
* [Docker explorer](https://github.com/google/docker-explorer)
* [Windows Container Forensics, Jul 2021](https://osdfir.blogspot.com/2021/07/windows-container-forensics.html)

### Cloud

* [Introducing Libcloudforensics, May 2020](https://osdfir.blogspot.com/2020/05/introducing-libcloudforensics.html)
```
# Create a copy of the volume 'vol1' from one account to another
cloudforensics aws 'us-east-2b' copydisk --volume_id='vol1' --src_profile='src_profile' --dst_profile='dst_profile'
# Scenario 3. Assumes credentials are configured through profiles in ~/.azure/credentials.json
cloudforensics az 'resource_group_name' copydisk --disk_name='disk1' --src_profile='src_profile' --dst_profile='dst_profile'
```
* [Forensicating Azure VMs, Feb 2021](https://isc.sans.edu/forums/diary/Forensicating+Azure+VMs/27136/)
```
powershell> $vm=az vm show --name whacked --resource-group whacked | ConvertFrom-JSON
powershell> $vm.storageProfile.osDisk.managedDisk.id
powershell> $disk=az disk show --ids $vm.storageProfile.osDisk.managedDisk.id
powershell> $snap = az snapshot create --resource-group whacked --name whacked-snapshot-2021FEB20 --source "/subscriptions/366[...]42/resourceGroups/whacked/providers/Microsoft.Compute/disks/whacked_disk1_66a[...]7" --location centralus | ConvertFrom-JSON
powershell> $snap.id

powershell> $sas=(az snapshot grant-access --duration-in-seconds 7200 --resource-group whacked --name whacked-snapshot-2021FEB20 --access-level read --query [accessSas] -o tsv)
powershell> az storage blob copy start --destination-blob whacked-snapshot-2021FEB20 --destination-container images --account-name [removed] --auth-mode login --source-uri "`"$sas`""
powershell> (az storage blob show -c images --account-name forensicimage -n whacked-snapshot-2021FEB20 --auth-mode login | ConvertFrom-JSON).properties.copy.progress
943718400/136367309312
powershell> (az storage blob show -c images --account-name forensicimage -n whacked-snapshot-2021FEB20 --auth-mode login | ConvertFrom-JSON).properties.copy.progress
136367309312/136367309312

powershell> az disk create --resource-group forensicdemo --name whacked-image --sku 'Standard_LRS' --location 'centralus' --size-gb 150 --source "`"https://[removed].blob.core.windows.net/images/whacked-snapshot-2021FEB20`""
powershell> $diskid=$(az disk show -g forensicdemo -n whacked-image --query 'id' -o tsv)
powershell> az vm disk attach -g forensicdemo --vm-name sift --name $diskid
```

* [Exploring container security: Performing forensics on your GKE environment, Dec 2019](https://cloud.google.com/blog/products/containers-kubernetes/best-practices-for-performing-forensics-on-containers)
* [Mitigating security incidents, GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/security-mitigations)
* [Making Sense of Kubernetes Initial Access Vectors Part 2 - Data Plane, Nov 2024](https://www.wiz.io/blog/kubernetes-data-plane), [Making Sense of Kubernetes Initial Access Vectors Part 1 – Control Plane, Nov 2024](https://www.wiz.io/blog/making-sense-of-kubernetes-initial-access-vectors-part-1-control-plane)
* `kubectl cluster-info dump`
