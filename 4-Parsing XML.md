# Parsing XML in ServiceNow
ServiceNow offers a number of APIs for handling XML inside the scripts. The API can use XPath filters to pick child nodes for mapping or manipulation

Specifically these are 

1. [XMLContent](https://docs.servicenow.com/bundle/jakarta-servicenow-platform/page/administer/edge-encryption/concept/c_XMLContentAPI.html)
A global object that provides methods to iterate over the XML content.

2. [XMLElementIterator](https://docs.servicenow.com/bundle/jakarta-servicenow-platform/page/administer/edge-encryption/concept/c_XMLElementIteratorAPI.html)
Provides methods for iterating over XML elements.

3. [XMLElement](https://docs.servicenow.com/bundle/jakarta-servicenow-platform/page/administer/edge-encryption/concept/c_XMLElementAPI.html)
Provides methods for iterating through XML elements and mapping values to fields in a table.
