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

![]()
