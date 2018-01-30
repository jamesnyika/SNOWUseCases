# 16-Correlate message to the correct process instance

## Within Workflows
Within business processes, the Wait for WF Event activity is the mechanism by which a script activity in the same or other workflow can send a signal
to promote continuation of a business flow. This is accomplished by calling this api (from within a run script activity)
 ````
workflow.fireEvent('eventName');
 ````
 
 More information is [here](https://docs.servicenow.com/bundle/kingston-servicenow-platform/page/administer/workflow-activities/reference/r_WaitForWFEvent.html)

## Within Alerts
More information on how correlation is handled in ServiceNow, see [this](https://docs.servicenow.com/bundle/kingston-it-operations-management/page/product/event-management/concept/c_EMEventCorrelationRules.html) documentation article
