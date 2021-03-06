# 18-Automatic Notification and Alerting
ServiceNow fully supports notification and alerting of SLA violations. 
In [use case 17]() we saw how you can configure a SLA for a task using the SLA definitions form. In this use case, you will see that any SLA
breach results in sending out warnings and final breach notifications

SLA breaches can trigger workflows to do the notification. That configuration is desribed [here](https://docs.servicenow.com/bundle/kingston-servicenow-platform/page/administer/workflow-administration/task/t_CreateAWorkflowFromSLADefinition.html)

### SLA Breach Warning emails
Below are some examples of SLA breach warning emails. 
#### Warning at 75% of SLA duration
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLAWarn1.png)

#### Final Breach email
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLAWarn2.png)


### Dashboards
SLA tracking is visible through dashboards on ServiceNow as another method of tracking and notification. Below are some examples of the out of the box dashboards provided for SLA tracking

#### Overview Dashboard Tab
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLAd1.png)

#### Detail Tab
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLAd2.png)
