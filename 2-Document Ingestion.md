# Document Ingestion in ServiceNow
Document ingestion in ServiceNow from a JMS Queue must take two steps

## Step 1 - Consume XML data from the message queue and deposit into ServiceNow 
The JMS message payload must be parsed while in a process or written out to a location that it can be reached using an HTTP call. 
## Step 2 - Use the Data source functionality to consume the file and draw the data into a table. 
