# Task Creation
Task creation can be triggered by creating a business rule on table for insert. 
Below is a example of a business rule on a table to assign a role or task

Step 1 : Configure a business rule and set triggering criteria. 
Things to note:
 - You can filter out which results the rule applies to
 - Choose which database event to respond to
 - when Advanced is checked - then you can create a script to handle the rule details - just as done in this one. 
![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/BR1.png)


Step 2 : For simple field settings you can use this assign action box. Otherwise use the next tab to enter your script
![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/BR2.png)

Step 3 : In this script window you have the full power of ServiceNow scripting APIs
![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/BR3.png)
