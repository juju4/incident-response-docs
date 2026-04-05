
## Quality process

Regular review of ticket
* Can a new hire, upper management, journalist or lawyer look at ticket, understand it and evaluate that a good job was made
* End summary with what happened, what was done well+need improvements
* Appropriate classification and tagging
* Identify process gaps, training or automation needed

Add label quality_check (ongoing), quality_ok, quality_nok (done, latter to be re-evaluated after review)

### Criteria

Manual
* communication/language clear
* proper groups where involved
* proper scoping/identification
* proper course of action
* clear conclusion and closure code
* apply appropriate containment actions
* lessons learned

Auto check/lint (regular frequency, closure)
* time to ack
* time to remediate/closure
* has relevant attachments (email, logs queries+results, jupyter book...)
* has relevant labels/tags (user, host, business unit/product...) at case or observables level
* minimum size for critical field (summary, timeline...)
* closure code check (no conflicting attributes)
* not updated since 1w
* assigned but no comment


## References

* [How do you measure #SOC quality? 
🤔
1. ISO 2859-1 (#AQL) to determine sample size 
2. #Python #Jupyter notebook to perform random selection
3. Check sheet to spot defects 
4. Process runs every 24 hrs
5. (Digestible) #Metrics to improve
How'd we get there? Story in /thread, Apr 2020](https://twitter.com/jhencinski/status/1254465280367083521)
* [If you have a #SOC #QC program be super transparent about the trend. 
We wrote a #Slack bot that sends the #QC trend to the team each day. We talk about it. We plan. We adjust. 
QC legend: 
- 
🔴
 failed   
- 
🟢
 passed
- 
⚫
 missed
Visualize. Review. Plan. Improve. Repeat. Jun 2020](https://twitter.com/jhencinski/status/1277656033901588481)
* [Let's talk process control charts for a hot second. 

We use a control chart to answer "is alert management in a state of control?" 

Steps: 
- Detect last alert daily mean change w/ change point 
- Extract residuals using loess
- Plot residuals in control chart

Here's ours:](https://twitter.com/jhencinski/status/1306616434366218242)

* [Check Sheets: Five Basic Types](https://www.sixsigmadaily.com/check-sheets-five-basic-types/)

* [AQL CalculatorBased on the AQL Tables](https://qualityinspection.org/aql-calculator/)
* [AQL Calculator](https://rsjqa.com/useful-corner/aql-manday-calculator/aql-calculator)
Example:
For 500 tickets with major/minor defect limits at 1.5/4 with
** a General I categorization, you should sample 20 tickets
** a Special II categorization, you should sample 8 tickets.

