# 1-Triggering In ServiceNow
ServiceNow has an extensive triggering mechanism that can be used to kick off busines processes or send emails, make phone calls etc. 
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

## Step 2 : Configure a credential for logging into your ActiveMQ instance
We will just use the default out of the box admin/admin credentials. From the ServiceNow filter navigation, type credentials and create a new credential under "Connections and Credentials" as shown below. You will reference this later.

![Queue Contents](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Credentials.png)

## Step 4 : Configure a JMS Connection 
Under the same "Connections and Credentials" menu, configure a new Connection as shown below. Important points to configure here relative to your chosen JMS Server are :
- InitialContextFactory (this is the name of the JMS initial context factory. Your JMS Queue provider normally tells you this)
- Provider URL (this is the url to the running queue instance. Your JMS Queue provider normally tells you this)
- Also make sure you check "Use MID Server" to true (tick mark). 
- Your Credential field will be the name of the credential you configured in [Step 2](#step-1--configure-your-mid-server).
 
 ![Connection Configuration](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/Connection.png)


