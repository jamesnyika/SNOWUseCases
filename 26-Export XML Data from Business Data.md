# Export XML Data from Business Data

### Basic 
Right click on any form (eg. incident) and there export option dumps out and xml file or PDF file in two orientations. 

![Step](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/BasicXML.png)

Here is a partial example of an exported XML file
````
<?xml version="1.0" encoding="UTF-8"?>
<unload unload_date="2018-01-30 06:43:08">
<incident action="INSERT_OR_UPDATE">
<active>true</active>
<activity_due/>
<additional_assignee_list/>
<approval/>
<approval_history/>
<approval_set/>
<assigned_to display_value="David Loo">5137153cc611227c000bbd1bd8cd2007</assigned_to>
<assignment_group display_value="Service Desk" name="Service Desk">d625dccec0a8016700a222a0f7900d06</assignment_group>
<business_duration/>
<business_service display_value="North America Portal">8a7d0fd59f030200fe2ab0aec32e7021</business_service>
<business_stc/>
<calendar_duration/>
<calendar_stc/>
<caller_id display_value="Joe Employee">681ccaf9c0a8016400b98a06818d57c7</caller_id>
<category>database</category>
<caused_by display_value=""/>
<check_encryption>false</check_encryption>
<child_incidents/>
<close_code/>
<close_notes/>
<closed_at/>
<closed_by display_value=""/>
<cmdb_ci display_value="SAP Payroll">26e540d80a0a0bb400660482030d04d8</cmdb_ci>
<cmdb_ci_business_app display_value="Procurement">bd4c32c29370220028517a75e57ffb52</cmdb_ci_business_app>
<comments/>
<comments_and_work_notes/>
<company display_value="ACME North America">31bea3d53790200044e0bfc8bcbe5dec</company>
<contact_type>phone</contact_type>
<contract display_value=""/>
<correlation_display/>
<correlation_id/>
<current_impact/>
<delivery_plan display_value=""/>
<delivery_task display_value=""/>
<description>Incident is part of PA and reporting demo data.</description>
<due_date/>
<encrypted_by display_value=""/>
<encrypted_data display_value=""/>
<encrypted_data_log display_value=""/>
<encryption_context display_value=""/>
<escalation>3</escalation>
<expected_start/>
<follow_up/>
<future_impact/>
<group_list/>
<hold_reason>1</hold_reason>
<impact>2</impact>
<incident_state>3</incident_state>
<knowledge>false</knowledge>
<location display_value="San Diego">108752c8c611227501d4ab0e392ba97f</location>
<made_sla>false</made_sla>
<notify>1</notify>
<number>INC0001492</number>
<opened_at>2016-02-06 22:08:24</opened_at>
<opened_by display_value="Joe Employee">681ccaf9c0a8016400b98a06818d57c7</opened_by>
<order/>
<parent display_value=""/>
<parent_incident display_value=""/>
<phi display_value=""/>
<phi_history display_value=""/>
<priority>4</priority>
<problem_id display_value=""/>
<reassignment_count>1</reassignment_count>
<rejection_goto display_value=""/>
<reopen_count>0</reopen_count>
<reopened_by display_value=""/>
<reopened_time/>
<resolved_at/>
<resolved_by display_value=""/>
<rfc display_value=""/>
<service_offering display_value="North America Portal Standard">dc2fd20fd7b01200b96d45a3ce610369</service_offering>
<severity>1</severity>
<short_description>Need access to sales db for the west</short_description>
<situation_appraisal/>
<skills/>
<sla_due>2014-03-19 00:00:00</sla_due>
<sn_hr_le_activity display_value=""/>
<state>3</state>
<subcategory>db2</subcategory>
<sys_class_name>incident</sys_class_name>
<sys_created_by>demo.pa</sys_created_by>
<sys_created_on>2016-02-06 22:08:24</sys_created_on>
<sys_domain>global</sys_domain>
<sys_domain_path>/</sys_domain_path>
<sys_id>8d6353eac0a8016400d8a125ca14fc1f</sys_id>
<sys_mod_count>44</sys_mod_count>
<sys_updated_by>glide.maint</sys_updated_by>
<sys_updated_on>2016-01-07 22:08:24</sys_updated_on>
...
````
