# Invoking Web Services and Passing Business Data

ServiceNow has a number of documented examples on invoking web services such as those listed [here](https://docs.servicenow.com/bundle/istanbul-application-development/page/integrate/examples/concept/c_InboundWebServiceExamples.html)
Every invocation of REST / SOAP services in ServiceNow supports passing business data from any table to the service.

The primary methods of invoking web services are :
### From a workflow : configure a custom Rest Activity 
Very similar to adding a JMS activity, a REST activity offers up different execution fields but usage is the same. 

![Rest](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/RestActivity.png)

### From the REST Explorer and into a script
Using this mode of operation, we use the REST API Explorer to test an actual real life Web Service and then servicenow will generate the required code for you to place into a script

### Use a REST Message object to run against a service
Configure a REST message and use the 'Test' option to execute it 

![Rest](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/RestMessage.png)


