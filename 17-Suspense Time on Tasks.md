# 17-Suspense Time on Tasks

Time on tasks can be managed through Service Levels in ServiceNow. Each task in ServiceNow is tracked from the moment it is created until it is completed.

Tasks exist on their own as a record. However, associated to a task can be a service level tracker if so configured to allow the tracking of time by which the task must be complete. This is how Suspense time on tasks is tracked and managed. 

Service Levels in ServiceNow can also be tied to a work schedule so that they only account for 'work hours', avoid counting holidays and weekends and any other conditions that make sense for the business. 

### Example 1: Case - Priority 1 resolution (8 hour)
The screen below shows the configuration of a Priority 1 SLA that can be tied to a task to give it the desired feature for this use case.
Features to notice:
- You can control the duration you wish to suspend on the task. 
- You can control the schedule that you want to attach to the SLA tracker (eg. Do not count weekends as work time, or holidays)
- You can configure BOTH start and retroactive start conditions
- You can configure a pause condition
- You can also configure a stop condition
- You can configure a reset condition
- You can set a cancel condition

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLA1.png)

Below are each of the tabs for setting the suspense time conditions 
#### Start Conditions
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLA2.png)
#### Pause Conditions
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLA3.png)
#### Stop Conditions
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLA4.png)
#### Reset Conditions
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/SLA5.png)

