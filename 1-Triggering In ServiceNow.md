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
ServiceNow requires the jar file for your message queue driver. 

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
  
  
 


