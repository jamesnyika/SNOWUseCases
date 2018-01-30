# 8-Human Task Assignment

Human Task assignment is at the heart of all the activity performed by ServiceNow, being a platform for making work easy in the enterprise. 

Human task assignment can be done :

## Manually 
Open any form based on the task type (in this instance we use the Incident form) and scroll to the bottom. 
If not visible, you will need to configure the form's related lists to show the Incident Task tab. 
You can create a new Incident task and assign it to any user in the system

### Step 1 - Click New to Create a Task

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/HumanTask1.png)

### Step 2 - Fill out the task details manually
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/HumanTask2.png)


## Automatically
This is managed and triggered using business rules. Here we show an example of a business rules that does human task assignment for incidents automatically to a named individual on creation (on insert)

### Step 1 - Define a new business rule
Set the conditions to be only for on insert, of records on the incident table. 
Do not click advanced unless you want to use scripting mode

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/HumanTask3.png)

### Step 1 - Define the action for the business rule 
Set a field on the record (assigned to) to a specific person.
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/HumanTask4.png)

