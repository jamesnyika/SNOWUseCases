# 4-Parsing XML in ServiceNow

One of the best ways to pull in xml data in ServiceNow is not to work with it directly as XML but rather treat it as a [data source](#), pull the data into ServiceNow (this creates a transform map and puts it into staging tables) and then work with the Glide APIs to manipulate the data, apply business rules etc.

However, if you MUST parse data then : 

ServiceNow offers a number of APIs for programatically handling XML inside the scripts. The API can use XPath filters to pick child nodes for mapping or manipulation

Specifically these are 

1. [XMLContent](https://docs.servicenow.com/bundle/jakarta-servicenow-platform/page/administer/edge-encryption/concept/c_XMLContentAPI.html)
A global object that provides methods to iterate over the XML content.

2. [XMLElementIterator](https://docs.servicenow.com/bundle/jakarta-servicenow-platform/page/administer/edge-encryption/concept/c_XMLElementIteratorAPI.html)
Provides methods for iterating over XML elements.

3. [XMLElement](https://docs.servicenow.com/bundle/jakarta-servicenow-platform/page/administer/edge-encryption/concept/c_XMLElementAPI.html)
Provides methods for iterating through XML elements and mapping values to fields in a table.

## Using Data Sources to consume files
More information on how this is done in ServiceNow is [here](https://docs.servicenow.com/bundle/kingston-platform-administration/page/administer/import-sets/concept/c_DataSources.html)
The basic steps are 

### Step 1 : Define your data source
Navigate to Data Sources on the filternavigation and create a new Data Source record

![Step1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/DataSource1.png)

### Step 2 : Test the datasource
Each datasource gives you a set of links to test out reading from the datasource. 
Try it out an in step 3 look at the results of the import into the Staging tables.

![Step2](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/DataSource2.png)

### Step 3 : Review the results of the import in Staging
Once in staging tables, you can use [transform maps](https://docs.servicenow.com/bundle/kingston-platform-administration/page/script/server-scripting/concept/c_CreatingNewTransformMaps.html) to push them to their final resting tables.

![Step3](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/DataSource3.png)
