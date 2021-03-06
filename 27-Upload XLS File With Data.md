# Uploading XLS data
Uploading data into ServiceNow using XLS files is quite quick and straight forward

### Step 1 - Go to the list view
Click on any column heading hamburger icon (three lines)
![Step-1](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/27-Step1-SelectImport.png)

### Step 2 - Ask Servicenow to generate a template file for you (based on your use case - insert or update)
* The Insert case will generate an empty file but all headers and possible values for fields already set up in the xls file.
* The update case will generate all the data already in the table.  
![Step-2](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/27-Step2-ChooseGenerateFile.png)

### Step 3 - Wait
Large tables with many columns take a while to generate so be patient.
![Step-3](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/27-Step3-Wait.png)

### Step 4 - Once Generated - Download the file and begin filling with data
![Step-4](https://github.com/jamesnyika/SNOWUseCases/raw/master/images/27-Step4-DownloadTemplateFile.png)

### Step 5 - Upload you data and commit the data to see it appear in the table.
Once all data is in the XLS file, return to the same screen you downloaded the form from and click on 'Upload' to submit the data file.
ServiceNow will churn through and generate a transform map on the fly to transform your data as best as it can. 
If there are conflicts or missing columns then ServiceNow was not able to reconcile your field in reference to an existing record in another table or
it might be a date field where additional processing would have been required.

## Key Points
* Use this method when the data you have is generally very straightforward and does not have date time conversions and few references.
* If you have reference field values in your data make source
  *  The reference value in your data = display value of the referenced table
  *  Date / Time fields will require additional processing an using the Transform Map approach may work better.
