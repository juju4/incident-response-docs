# Jupyter notebooks

## Structure per artefact type

* Trends
  * per day, week, month
  * Time series analysis
  * Web authenticated traffic or not, http status
* Top/Flop per fields
* System
  * Authentication
  * Remote access
  * Privilege escalation
  * Service activities
  * System boot, on/off
  * Process activities
  * Network activities
  * File integrity monitoring
  * Security components (auditd, selinux, apparmor, AV, EDR...)
* Points of interest
  * Win files: Public, ProgramData, Temp/tmp, AppData\Local\Temp, RecycleBin/Trash
  * Web: common path wp-admin, admin, cgi-bin, /.well-known, /robots.txt, rss/feeds...
  * File extension
  * Large/small files
  * Filename/path entropy
  * Group by folder path, 2-5 level
```python
clean_paths = df['filepath'].str.lstrip('/')
df['first_three_folders'] = clean_paths.str.split('/').str[:3].str.join
```
  * Web, MFT... list of existing users, first+last seen
  * Public/Private traffic
  * Tor/VPN traffic
  * Request processing, bytes sent/received
  * Web requests with empty/programming/unusual user-agent, empty referer or not current website
  * Web or file matching sensitive content: password, secret, credential, confidential, secret, identity, creditcard...
  * Applicable IOC per threat actor/incident
* Visualization
  * Timeseries
  * Clustering
  * Geolocation map, ASN
  * Process tree/network, 1-3 levels
  * Sankey, parallel coordinates?
* Zoom period of interest
* Pivot on findings

## References

* https://infosecjupyterthon.com/introduction.html, https://github.com/OTRF/infosec-jupyterthon/tree/master/, https://github.com/OTRF/ThreatHunter-Playbook/tree/master/docs/hunts/windows
* https://github.com/target/huntlib
* https://github.com/microsoft/msticpy/, https://github.com/microsoft/msticnb, https://medium.com/@msticmed
  * <https://msticpy.readthedocs.io/en/latest/data_analysis/EventClustering.html>
  * <https://msticpy.readthedocs.io/en/latest/data_analysis/AnomalousSequence.html>
  * <https://msticpy.readthedocs.io/en/latest/visualization/EventTimeline.html>
  * <https://msticpy.readthedocs.io/en/latest/visualization/ProcessTree.html>
  * <https://msticpy.readthedocs.io/en/latest/visualization/FoliumMap.html>
  * <https://msticpy.readthedocs.io/en/latest/visualization/TimeSeriesAnomalies.html>
  * <https://msticpy.readthedocs.io/en/latest/visualization/MatrixPlot.html>
  * <https://msticpy.readthedocs.io/en/latest/visualization/EntityGraph.html>
  * <https://msticpy.readthedocs.io/en/latest/visualization/NetworkGraph.html>
* https://github.com/Azure/Azure-Sentinel-Notebooks
* https://notebooks.azure.com/Microsoft/projects/samples
* https://github.com/maartengoet/notebooks
* https://github.com/MISP/misp-playbooks/tree/main/misp-playbooks
* https://github.com/jupyter/docker-stacks/tree/master/base-notebook
* [Repository with Sample threat hunting notebooks on Security Event Log Data Sources ](https://github.com/ashwin-patil/threat-hunting-with-notebooks)
* [papermill - tool for parameterizing, executing, and analyzing Jupyter Notebooks](https://github.com/nteract/papermill)
* [Feature Request: Enhanced Markdown Support For Graphs #2300](https://github.com/jupyter/notebook/issues/2300)
* https://github.com/DebugPrivilege/Jupyter-Notebooks/blob/master/DCShadow.ipynb
* BlueTeamVillage Project Obsidian: [DC30 > OODA loop KC3](https://github.com/blueteamvillage/obsidian-ir/tree/main/DC30/ooda_loop), [DC31 > IR > Know your logs](https://github.com/blueteamvillage/Project-Obsidian-DC31/tree/master/IR/Presentations/obsidian-btv-know_yourself_logs) - iaas template linux/web/win, [DC31 > IR > msticpy velociraptor offline collection analysis](https://github.com/blueteamvillage/Project-Obsidian-DC31/tree/master/IR/Presentations/obsidian-btv-velociraptor-offline-collector-notebook)
* [My Jupyter Collection, Dec 2022](https://blog.securitybreak.io/my-jupyter-collection-18e936af410a), [Notebooks, CheatSheets & More](https://jupyter.securitybreak.io/) by @fr0gger_
* [Collection of Jupyter Lab notebooks to help learn Generative AI](https://github.com/besimorhino/ai-workshop)
* [Jupyter Tools for AI Agents](https://github.com/Cyb3rWard0g/agent-jupyter-toolkit), [Executable Code Actions Elicit Better LLM Agents, Feb 2024](https://arxiv.org/abs/2402.01030), [AI Agents and Jupyter Notebooks for Security Data Analysis - Roberto Rodriguez, May 2026](https://www.youtube.com/watch?v=VJPWZGhQe4A)
* <https://github.com/davidalonsod/Dalonso-Security-Repo/blob/main/Notebook/Sentinel-Security-Analysis-6Month.ipynb>

* [Automating Security Operations Using Windows Defender ATP APIs with Python and Jupyter Notebooks, Dec 2018](https://techcommunity.microsoft.com/blog/microsoftdefenderatpblog/automating-security-operations-using-windows-defender-atp-apis-with-python-and-j/294434)
* [Why Use Jupyter for Security Investigations? Apr 2019](https://techcommunity.microsoft.com/blog/microsoftsentinelblog/why-use-jupyter-for-security-investigations/475729)
* [Threat Hunting with Jupyter Notebooks— Part 1: Your First Notebook, May 2019](https://posts.specterops.io/threat-hunting-with-jupyter-notebooks-part-1-your-first-notebook-9a99a781fde7) (disappeared, <https://archive.md/3gr7N#selection-285.0-285.66>)
* <https://learn.microsoft.com/en-us/azure/sentinel/datalake/notebook-examples>
* <https://learn.microsoft.com/en-us/azure/sentinel/notebooks-hunt?tabs=public-endpoint>
* <https://learn.microsoft.com/en-us/shows/github-copilot-series/using-copilot-with-jupyter-notebooks>
* [The Basics of Forensics/IR in a Gsuite Environment, Jupyterthon, May 2020](https://github.com/jeffbryner/jupyterthon-May2020)
* [Hunting for anomalous sessions in your data with Azure Sentinel  - O365, Jun 2020](https://techcommunity.microsoft.com/t5/azure-sentinel/hunting-for-anomalous-sessions-in-your-data-with-azure-sentinel/ba-p/1492490)
* [How to create and maintain Jupyter threat hunting notebooks, Jun 2020](https://expel.com/blog/how-to-create-maintain-jupyter-threat-hunting-notebooks/)
* [If you use #Jupyter for infosec, what do you use it for? And screenshot a snippet from your notebook🙏, Sep 2020](https://x.com/JohnLaTwC/status/1301902295743909888): [Analyzing Windows RPC Methods & Other Functions Via GraphFrames](https://infosecjupyterbook.com/use-cases/data-analysis/03_analyzing_rpc_methods_relationships_graphframes.html), [Insider Threat Hunting](https://findingbad.blogspot.com/2020/07/insider-threat-hunting.html), [Using Graph Powered Security Analytics to Find Attackers Quickly](https://blogs.oracle.com/cloudsecurity/post/using-graph-powered-security-analytics-to-find-attackers-quickly)
* <https://github.com/davidalonsod/Dalonso-Security-Repo/blob/main/Notebook/Sentinel-Security-Analysis-6Month.ipynb>

* [White Paper - CyCAT - The Cybersecurity Resource Catalogue](https://www.cycat.org/services/whitepaper/)

* [How to improve your security incident response processes with Jupyter notebooks, Nov 2023](https://aws.amazon.com/fr/blogs/security/how-to-improve-your-security-incident-response-processes-with-jupyter-notebooks/)
* [Using Jupyter Notebook for CTI using PyMISP, Mar 2024](https://socradar.io/blog/using-jupyter-notebook-for-cti-using-pymisp/)

Sentinel Workbooks/Notebooks
* [Process Investigation workbooks is a collection of Microsoft Sentinel workbooks that act as a **log-based process explorer**. ](https://github.com/lazaridischristos/Sentinel-Workbook-Process-Investigation) (Sysmon or MDE based)
* <https://github.com/microsoft/Sentinel/tree/main/data%20lake/notebooks/PasswordSpray>

Velociraptor
* <https://github.com/Velocidex/pyvelociraptor/blob/master/pyvelociraptor/velo_pandas.py>

Alternatives
* [The future of Python notebooks is here  Transform data, train models, and run SQL queries with marimo — feels like an AI-native reactive notebook, stored as Git-friendly reproducible Python. Seamlessly run as scripts and apps. All open source.](https://marimo.io/)

* [HTTP Status Codes Explained, Jun 2026](https://www.linkedin.com/posts/athulya-b-bb1bb9231_cybersecurity-websecurity-statuscodes-activity-7471118073069101056-tK1X)
