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
