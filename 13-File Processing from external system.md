# 13-File Processing from external system
Accessing FTP endpoint from ServiceNow is also an out of the box supported function

### Solution: Data Sources
Data Sources provide a mechanism for defining a source of information and configuring it in ServiceNow. Once configured, a data source can be pulled from
using a scheduler or on demand.

For an example see the screen below where we configure a data source for pulling FTP files from an external system.
Things to notice:
 - ServiceNow offers multiple types of protocols from which to pull files for processing including HTTP(S), (S)FTP, SCP and attachments.
 - There is a choice received files that are already archived in Zip format too.

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/FTP2.png)
