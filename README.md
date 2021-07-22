# Data Factory / Synapse Pipeline Workbook

A log analytics workbook for monitoring and operating multiple Data factories and Synapse Pipelines.  It is used to get an overview of all runs that ADF and Synapse have done. 

The workbook supports answering questions:
* Which ADF / Synapse Instance has the most runs?
* Which piplines are succedding or failing?
* What are the longest running pipelines? 
* When was the last run?
* Has the last x runs succeed or failed? 
  * With drill down possiblity to see specific times and states of individual runs and activites
* Which day has had more or less pipelines running
* At what time during the day is my pipelines running?
* Is there more or less data transfered over time
* What errors is thrown?    

### **Overview Page**
![Overview page](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/master/.github/images/overview.jpg?raw=true)

### **Details Page**
![Detials page](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/0c3e6afe6d18530bf39b3d8aca2c264eeebe834b/.github/images/datapipeline-detail.jpg?raw=true)
