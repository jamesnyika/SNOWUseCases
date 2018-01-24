# 1-Triggering In ServiceNow
ServiceNow has an extensive triggering mechanism that can be used to kick off business processes, send emails, make phone calls etc. 
We can also create listeners for different sources as shown below. You access these in the custom tab and click the + icon

----
![Listeners](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/ServiceNowListenerTypes.png)


In this excercise we create a JMS listener and use it to create a polling workflow. This workflow will poll an ActiveMQ JMS queue
Below are the contents of the queue

![Queue Contents](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/1-ActiveMQContents.png)

And here is a sample message

![Queue sample](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/2-ActiveMQMessageExample.png)

## Step 1 : Configure Your MID Server
ServiceNow documentation on MID Server Setup is very complete and thorough. Please follow it [here](https://docs.servicenow.com/bundle/helsinki-servicenow-platform/page/product/mid-server/concept/c_MIDServerInstallation.html) 
Ensure your MidServer is up and running and ALL CAPABILITIES are configured on it. 

## Step 1.5 : Upload your message queue driver jar
ServiceNow requires the jar file for your message queue driver. In the filter navigation type "Jar" and you should see a menu
item for MID Server jar files. Select that menu item and click the New button to configure a new upload. Enter the necessary information as shown below and the use the paperclip icon on the top of the form to attach your jar file to the form and submit. 

![Queue Contents](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/DriverUpload.png)

## Step 2 : Configure a credential for logging into your ActiveMQ instance
We will just use the default out of the box admin/admin credentials. From the ServiceNow filter navigation, type credentials and create a new credential under "Connections and Credentials" as shown below. You will reference this later.

![Queue Contents](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Credentials.png)

## Step 3 : Configure a Connection Alias
Under the same "Connections and Credentials" menu, configure a new Connection Alias as shown below. You may give any name you want but remember it for later steps.
- Type must be JMS
- You can pick Connection and Credential together. 
- You may use any name you like. 

![Queue Contents](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/ConnectionAlias.png)

## Step 4 : Configure a JMS Connection 
Under the same "Connections and Credentials" menu, configure a new Connection as shown below. Important points to configure here relative to your chosen JMS Server are :
- InitialContextFactory (this is the name of the JMS initial context factory. Your JMS Queue provider normally tells you this)
- Provider URL (this is the url to the running queue instance. Your JMS Queue provider normally tells you this)
- Also make sure you check "Use MID Server" to true (tick mark). 
- Your Credential field will be the name of the credential you configured in [Step 2](#step-1--configure-your-mid-server).
- Your Connection Alias comes from [Step 3](#step-3--configure-a-connection-alias)
 
 ![Connection Configuration](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Connection.png)
 
## Step 5 : Test your JMS Connection 
The Connection page has a link at the bottom to "Test Connection" Click on it and you should see go through the following two steps.
Key points
- Select the correct mid server you are using for this tutorial
- Ensure you get a validated connection. A failed validation means one of many things could be happening
  - Your MID server is not running
  - Your credential configuration passed in wrong credentials
  - Your Message Queue Server is not running
  - You have configured an incorrect Provider URL
  - You configured an incorrect InitialContextFactory
  - You did not upload the correct and non-corrupted JMS Driver jar file.
  - You might not be connected to the/a network
  
  ![Testing Connection 1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/TestConnection1.png)
  
  and after validating you should see 
  
  ![Testing Connection 2](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/TestConnection2.png)
  
 ## Step 6 : Create a Custom Activity for Getting Messages off a JMS Queue
The next steps require that you have the ServiceNow Orchestration plugin turned on and you have the appropriate roles to configure workflows. More information is here on:
   - [Activating Orchestration](https://docs.servicenow.com/bundle/helsinki-servicenow-platform/page/product/orchestration/task/t_ActivateOrchestration.html) 
   - [Workflow Editor](https://docs.servicenow.com/bundle/kingston-servicenow-platform/page/administer/workflow/reference/workflow-editor.html) 
   
   To begin, navigate to the workflow editor and create a custom activity by clicking on the Custom tab and then the + sign to the right. This will bring a submenu from which JMS can be picked (last item in the menu). 
   
   This will give you a sequence of screens to configure the activity. The next few screenshots describe those steps
   
----
   
 ### 1. Configure the name and description of your listener
 ![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/3-JMSPoller-Step1.png)
 ### 2. Configure any input variables.
 We do not use any at all in this case  
 ![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/4-JMSPoller-Step2.png)
 ### 3. Configure the execution details
 Important points here are :
 - Pick the connection factory configured above
 - Check for a reasonable timout value
 - Only Text is supported for message type if the Mode is GET
 - We need GET mode if we are going to read from the queue. PUT is used to send a message TO a queue
 - We are accessing a queue not a topic in this example so select Queue for destination type
 - Destination Name is whatever you NAMED your queue on your JMS server where ServiceNow will read from.  
![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/5-JMSPoller-Step3.png)
 ### 4. Configure your output variables
 ServiceNow allows you to define both local variables (local to the Activity) or output variables (that will be passed out to other activities following this one). We only configure output variables in this case. We could also have written to the workflow.scratchpad - an in memory global write area where activities can share data with each other.  
 Key points:
 - when you add a new output variable, you can then 'drag it' to the variable name area and the configure how you want it to be populated. More information is available [here](https://docs.servicenow.com/bundle/istanbul-it-operations-management/page/administer/orchestration-activity-designer/task/t_CreateAnOutputVariable.html) on how to do this. Do not click on post processing as we do not need it. 
![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/6-JMSPoller-Step4.png)
 ### 5. Conditions
 By configuring conditions, we configure what paths we want out of this activity. More information on configuring conditions is [here](https://docs.servicenow.com/bundle/istanbul-servicenow-platform/page/administer/using-workflows/task/t_ManageActivityConditions.html)
 
![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/7-JMSPoller-Step5.png)

At this point you have now created a custom activity that can be used in any workflow to read from the configured message queue. 

## Step 7 : Design the WorkFlow
We need a workflow with a looping construct to be able to repeatedly poll the message queue for messages and then do something with them like 
- Kick off another workflow
- Create a record in a table
- Create a system event
- Create a business event
- Send a notification or email

In this workflow we do two of these. We will create a record in the Event Management Event table. We will also create a business event. 
The workflow we will design will look as follows and is a polling workflow for reading from the queue and doing something with the message. Some resources on creating workflows: 
[Video Tutorial on Workflow](https://youtu.be/Jgj26yUphBw)
[Video Tutorial on Workflow 2 - Advanced](https://youtu.be/7nf0p3xdGKA) 
[Video Tutorial on Workflow - Troubleshooting](https://youtu.be/li7hdfHbK3I)

![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/JMSPoller-Workflow.png)




