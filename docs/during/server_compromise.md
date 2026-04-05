# Server compromise

## Definition

Server is identified as compromised possibly relating to

* Malware
* Ransomware
* Data Breach
* Identity compromise, including Managed identity
* Application compromise, including webservers exploitation (ex: webshell), file transfer tool (ex: MoveIt)
* Website defacement

## Course of Action

* Check system information
  * Owner? criticity? backup? time to rebuild?
  * Data hosted on server? sensitivity?
  * Identities involved (human and non-human)
  * Network activity: What systems can server reached? Internet, DMZ, Internal network, partners/customers...
  * Performance activity
  * Security tools coverage
  * Logs activity from central logging
  * Cloud console information. Ex: Azure Security Center, Policy, Networking...
  * Possible blast radius of incident
* Collect live artifacts
  * Live snapshot if virtualized (vmware disk+memory, azure disk...)
  * Memory if not previously
  * Extra captures like tcpdump, procmon, sysdig...
  * Other live artifacts: MFT, Prefetch, ...
* Collect server owner feedback
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
* [CERT SG IRM-3-UnixLinuxIntrusionDetection](https://github.com/certsocietegenerale/IRM/blob/main/EN/IRM-3-UnixLinuxIntrusionDetection.pdf)
* [CERT SG IRM-6-Website-Defacement](https://github.com/certsocietegenerale/IRM/blob/main/EN/IRM-6-Website-Defacement.pdf)
* [Malware Playbook](https://gitlab.com/syntax-ir/playbooks/-/tree/main/IRP-Malware)
* [Malware triage with MISP](https://github.com/MISP/misp-playbooks/blob/main/misp-playbooks/pb_malware_triage.ipynb)
* [Linux Compromise Assessment Command Cheat Sheet, Nov 2018](https://www.sandflysecurity.com/wp-content/uploads/2018/11/Linux.Compromise.Detection.Command.Cheatsheet.pdf)
* [Web Application Attack Response Playbook](https://frsecure.com/web-application-attack-response-playbook/)
* [Malicious IIS extensions quietly open persistent backdoors into servers, Jul 2022](https://www.microsoft.com/en-us/security/blog/2022/07/26/malicious-iis-extensions-quietly-open-persistent-backdoors-into-servers/)

### Data collection

* [Forensic Artifact Collection Tool Matrix - Win, Linux, Swisscom, Dec 2020](https://github.com/swisscom/ArtifactCollectionMatrix)
* [When you should perform a Live Acquisition + the risks; these factors should always be considered prior to performing one during an investigation.Not so mini thread, Jul 2021](https://twitter.com/4n6lady/status/1411017778593677317)

  > Factor 1: Is there a valid reason to believe that volatile data contains information critical to the investigation that cannot be attained elsewhere? If you can get it some other system logs, you don't need to put this device at risk.
  > Factor 2: Can the live acquisition tool/method be conducted in an ideal manner? This tool/method should limit changes to the target system. If not, be aware of the changes, and document each action.
  > Factor 3: Will a full disk image (full acquisition) take an excessive amount of time or has the potential to fail? Is there an FDE (Full Disk Encryption) that will hinder your capability to do a full disk image? If so, a live acquisition of a logical image is ideal.
  > Factor 4: Is the number of affected systems overwhelming? Is is feasible to perform a full disk acquisition on all these machines? A live acquisition is ideal for grabbing key files: Event logs, registry hives, user profiles, processes, network connections, and MFT.
  > Factor 5: Is there a legal consideration that make it a good idea to grab as much data as possible?
  > Risk 1: The process of a live acquisition can hinder the system's performance, and could cause the system to crash should the system have any particular sensitivity to performance issues. Crashes can wipe the volatile evidence you're trying to preserve.
  > Risk 2: Similar to Risk 1, if the system does crash, data could be lost. Its important to evaluate how losing this data could impact the investigation.
  > Risk 3: Has your tool/method been tested on a similar system? Can you clearly explain what changes to the system are to be expected? Do you have a solid process when conducting live acquisitions?
  > Risk 4: Do you have approval? It's not a good idea to go all willy nilly on a system that you think may/may not contain evidence. You need a valid reason to believe, and its best to have approval before performing a live acquisition. If something goes wrong, you'll be covered.

### Virtual Machines

* [Vmware](https://github.com/volatilityfoundation/volatility/wiki/VMware-Snapshot-File), Eventually convert to [core memory dump](https://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2003941).

```shell
esxi$ vim-cmd vmsvc/snapshot.create <VM_ID> <SNAPSHOT_NAME>
esxi$ vim-cmd vmsvc/snapshot.get <VM_ID>
workstation$ vmrun snapshot <PATH TO VMX FILE> <SNAPSHOT_NAME>
workstation$ vmrun listSnapshots <PATH TO VMX FILE>
```

Alternatives: [Cmdlet New-Snapshot](https://pubs.vmware.com/vsphere-6-0/index.jsp#com.vmware.powercli.cmdletref.doc/New-Snapshot.html), [vmsnapshot.pl](https://pubs.vmware.com/vsphere-6-0/index.jsp#com.vmware.perlsdk.uaref.doc/vmsnapshot.html)
* [Virtualbox](https://github.com/volatilityfoundation/volatility/wiki/Virtual-Box-Core-Dump): [debugvm](https://www.virtualbox.org/manual/ch08.html#vboxmanage-debugvm)

```shell
live$ VBoxManage debugvm <uuid|vmname> dumpvmcore [--filename=name]
atstart$ VirtualBox --dbg --startvm <VM name>
atstart dbg> .pgmphystofile
```

* [Parallel](http://kb.parallels.com/en/121323)

```shell
prlctl list -a
prlctl start {<VM_UID>}
prlctl internal {<VM_UID>} dbgdump --path /path/to/target/dir/
```

### Containers

* [CSI: Container Edition - forensics in the age of containers, Aug 2017](https://www.stackrox.com/post/2017/08/csi-container-edition---forensics-in-the-age-of-containers/)
  * `docker commit $CONTAINER_ID imagename`
  * memory: `gcore $PID`, objdump, dd...
* [Forensicating Docker, Part 1, Mar 2016](https://isc.sans.org/forums/diary/Forensicating+Docker+Part+1/20835)
* [Docker explorer](https://github.com/google/docker-explorer)
* [Windows Container Forensics, Jul 2021](https://osdfir.blogspot.com/2021/07/windows-container-forensics.html)

### Cloud

* [Introducing Libcloudforensics, May 2020](https://osdfir.blogspot.com/2020/05/introducing-libcloudforensics.html)

```shell
# Create a copy of the volume 'vol1' from one account to another
cloudforensics aws 'us-east-2b' copydisk --volume_id='vol1' --src_profile='src_profile' --dst_profile='dst_profile'
# Scenario 3. Assumes credentials are configured through profiles in ~/.azure/credentials.json
cloudforensics az 'resource_group_name' copydisk --disk_name='disk1' --src_profile='src_profile' --dst_profile='dst_profile'
```

* [Forensicating Azure VMs, Feb 2021](https://isc.sans.edu/forums/diary/Forensicating+Azure+VMs/27136/)

```shell
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
