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

# Setup
## 1. Add dignostic settings from ADF / Synapse

Goto diagnostic settings on your Data factory or Synapse instance and the add diagnostic settings.  
![Goto to diagnostic settings](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/master/.github/images/add-diagnosticsettings1.jpg?raw=true)



Then add ActivityRuns, PipielineRuns, trigger runs and All metrics ( all can be checked ) and send that to the appropriate Log Analytics workspace. Use Resource Specific destination table. 
![Setup diagnostic settings](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/master/.github/images/add-diagnosticsettings2.jpg?raw=true)

## 2. Add workbook to Log Analytics
1. Goto **Workbooks** (under General)
2. Press **New** button
3. Press **Advance Editor ( </> )**
4. Copy / paste the workbook(DataFactory.workbook) from here into window and press apply
5. **Save** the workbook


# Description of Charts
## Filters
![Filters](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/master/.github/images/filters.jpg?raw=true)

* Time Range : Is the time range of which the workbook will show data
* Data factory: Filter on a specific ADF/Synapse or multipe
* Pipeline : Filter on a specifc pipeline. (IS cascading from Data factory filter)

## Overview Dashboard
### Runs per Synapse/Datafactory 
![Runs per ADF](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/master/.github/images/runs-per-adf.jpg?raw=true)

Show number of times a data facory or synapse insatnace has run pipelines. This chart is to get a glimse of which instance is running most pipelines. 

### Runs per pieline grouped by status
![Runs per Pipeline](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/master/.github/images/runs-per-pipeline.jpg?raw=true)

Show number of times a pipeline has been triggered. This chart is to get a glimse of which pipeline is running the most. Also to see which is failing or succeding. 

### Average duration per pipeline
![Runs per Pipeline](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/master/.github/images/average-duration.jpg?raw=true)

Show average duration of pipelines. This to find long runing pipelines that might need attention.

### Last runs
Gives on overview of the last runs of the pipelines.
![Last Run overview](https://github.com/johantysklind/datafactory-loganlytics-workbook/blob/master/.github/images/last-runs1.jpg?raw=true)
* Pipeline : Name of the pipeline
* Resource : Name of the ADF / Synapse instance
* Staus : Last run status 
* Start : Last run start time
* Duration : Last run duration
* Last runs : Shows the last runs as a ball. One ball represents a run within the selected Timerange. The latest run is represented by the first ball.
* Link : Link to monitor in ADF for the specific pipeline
*  