# 15-Wait for an event/Asynchronous  processing
In ServiceNow business processes workflows two items are provided to allow event handling from both other activities in workflows or from records 
in tables on the platforms

### Wait for Condition Workflow Activity
The Wait for condition activity causes the workflow to wait at this activity until the current record matches the specified condition.
The workflow evaluates the Wait for condition activity each time the current record is updated. Use this activity to pause a workflow indefinitely until a particular criteria is met by a record update. To pause a workflow for a timed duration see Timer workflow activities.
[ServiceNow Documentation](https://docs.servicenow.com/bundle/kingston-servicenow-platform/page/administer/workflow-activities/reference/r_WaitForCondition.html)

### Wait for WF Event Workflow Activity
The Wait for WF Event activity causes the workflow to wait at this activity until the specified event is fired.
Use this activity to wait for another activity to fire an event. Events from other activities are fired in a script using the workflow.fireEvent('eventName') API call.
[ServiceNow Documentation](https://docs.servicenow.com/bundle/kingston-servicenow-platform/page/administer/workflow-activities/reference/r_WaitForWFEvent.html)

There is also a [timer]() activity for holding and delaying workflow activities to comply with business requirements



