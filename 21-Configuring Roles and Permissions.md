# 21-Configuring Roles and Permissions
Configuring roles and permissions for business data on forms is handled through :

## 1. Filters 
Filters are used to control what data is allowed to reach the screen. Consider the navigation items on the filter navigation. Many are filters on
lists of data. For example the image below shows a Security INcident filter that filters down incidents to only show those belonging to one of my team
Notice too the filters at the top that were preset. 

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/F1.png)

## 2. Data Policies
Data policies enable you to enforce data consistency by setting mandatory and read-only states for fields.

Data policies are similar to UI policies, but UI policies only apply to data entered on a form through the standard browser. Data policies can apply rules to all data entered into the system, including data brought in through import sets or web services and data entered through the mobile UI. More information can be found [here](https://docs.servicenow.com/bundle/kingston-platform-administration/page/administer/field-administration/concept/c_DataPolicy.html)

We use Data Policies in ServiceNow to control data entry and prevent modification on fields by users who do not have the correct roles and permissions


## 3. UI Policies
UI policies dynamically change information on a form. They can be used to hide fields if users do not meet certain criteria such as miss a role or do not the right ACLs. More information can be found [here](https://docs.servicenow.com/bundle/kingston-platform-administration/page/administer/form-administration/task/t_CreateAUIPolicy.html)

Below is an example of a UI Policy that will :
    *Make Groups and Users list visible only when Viewable by is Groups and Users*
#### The Top level configuration 
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/UP1.png)

#### UI Policies also require actions to be specified.
![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/UP2.png)
