

## Recommendations

First ensure that your organization and team is mature enough before extending time coverage.
"strong day team is better than weak 24x7."

Implementing 24x7 on-call should be first step and possibly enough vs going 24x7 on-site/on-shift too soon.

If your organization is world-wide, try to implement follow-the-sun model and avoid non-standard hours that will potentially create fatigue, health issues, turnover and so on.

## Typical 24x7

* 6 groups of 8-9h shifts, 5 days
* 4 days on, 3 days off
* 4 days on, 4 days off

## Shifts handover

Medium can be whatever fitting team and company: Email, Web status, Chat status...
It's recommended to have them archived.

* Executive Summary, including incidents in progress
* Actions/Recommendations
* Important notes: tools health-check, escalation, blockers if any.
* Ongoing operational issues and workarounds, special events (quarter end, coming pentest...)
* High priority Threat Intelligence
* Handover signoff: previous, new shifts
* Tickets ongoing
* Tickets closed
* (Email pending processing)
* Tools health-check details
  * logs flowing (top source like security tools, ActiveDirectory, AzureAD...)
  * security tools/console state, healthy, patched
  * Weekly/Monthly backup (wiki, ticketing...)
  * Revalidate users access and permissions

## References

* https://en.wikipedia.org/wiki/Shift_plan
* https://www.bmscentral.com/learn-employee-scheduling/category/shift-patterns/
* [Intro SOC training, 2020 Educause Security, Chris Crowley](https://www.youtube.com/watch?v=caPYj9v8E-M) ~Daily Shift Change ~57:00
* [Configure Shift Handover Templates - ServiceNow](https://www.servicenow.com/docs/bundle/zurich-security-management/page/product/secops-analyst-workspace/task/configure-shift-handover-templates.html)
* [Time Zone Math That Actually Works, Dec 2025](https://hirefullscale.com/timezone-math-that-works) "A tight daily overlap between your US core hours and an offshore mid-shift does more for velocity than most teams realize. Two or three hours of live collaboration can collapse feedback loops, kill decision lag, and move work from “stalled” to “shipped.”"
