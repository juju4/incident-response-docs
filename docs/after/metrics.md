Metrics are a requirement to evaluate impact and improvements over incidents
Those should help to identify easily which platform or component is most often at stake and where improvements is more valuable.

From a generic standpoint, your system should give you following statistics

* Number of incidents per severity, per hour of day or day of week, per application/platform or geography
* Mean-Time-To-Repair (MTTR), Cost of repair (hours)
* Mean-Time-Between-Failure (MTBF)
* Avaibility: either as uptime, either as successful requests (if using Error budget)
* Error budget (Google Site Reliability Engineering): one minus the availability target

From a security perspective

* Number of incidents per category per severity
* Dwell time: time between cause of incident/compromission and discovery
* Mean-Time-To-Contain (MTTC)
* Identified loss
* Source of notification: automated system, manual, 3rd party
* Controls involved
* KillChain steps
* Outcome: false-positive, true-positive...


## References
* [Vocabulary for Event Recording and Incident Sharing (VERIS)](http://veriscommunity.net/)
* [Error Budgets and Risks, Marc Alvidrez, Google, SRECon 2015 ](https://www.usenix.org/conference/srecon15/program/presentation/alvidrez)
