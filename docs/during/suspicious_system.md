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
* Collect live artifacts
    * snapshot if virtualized
    * memory
    * extra captures like tcpdump, sysdig...
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

* [If you aren’t performing memory analysis then you are doing your clients & org a disservice, @attrc, jun 2016](https://twitter.com/attrc/status/742399097206771712)
* [Reqs for effective #DFIR, Why Threat Hunting, Why Memory Forensics, @attrc, nov 2016](https://twitter.com/attrc/status/793875121022832640)
* [Volatility](http://www.volatilityfoundation.org/)
* [Rekall](https://github.com/google/rekall/)
* [Loki](https://github.com/Neo23x0/Loki)
* [FastIR](https://github.com/SekoiaLab/FastIR_Collector)
* [OSX Collector](https://github.com/Yelp/osxcollector)
* [Adware the series, the final: Tools section, Jul 2017](https://blog.malwarebytes.com/puppum/2017/07/adware-the-series-the-final-tools-section/)

Virtual Machines

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

Docker

* [CSI: Container Edition - forensics in the age of containers, Aug 2017](https://www.stackrox.com/post/2017/08/csi-container-edition---forensics-in-the-age-of-containers/)
    * ```docker commit $CONTAINER_ID imagename```
    * memory: ```gcore $PID```, objdump, dd...
* [Forensicating Docker, Part 1, Mar 2016](https://isc.sans.org/forums/diary/Forensicating+Docker+Part+1/20835)
* [Docker explorer](https://github.com/google/docker-explorer)
