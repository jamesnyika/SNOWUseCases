# 14-File Polling
File polling in ServiceNow is handled by combining the creation of a data source with a scheduler.

Below is an example of an LDAP User import mechanism that targets a datasource and ties it to a schedule. For a more fine grained scheduling of the action, 
a job must be defined and triggered.

