# HCL OneTest Performance

This action enables you to run HCL OneTest Performace tests.

## Prerequisites

1. Create a github repository
2. Create a folder named ".github/workflows" in the root of the repository
3. Create a .yml file with any name inside the ".github/workflows" folder
4. You need to add code in yml file as detailed in example below.

## Example

```yaml
name: HCL OneTest Performance

on: workflow_dispatch

jobs:
    Performance-Action:
        runs-on: self-hosted
        name: HCL OneTest Performance
        steps:
         - name: HCL OneTest Performance
           uses: anuraag-k/PerformanceTestAction@main
           with:
            workspace: 
            project: 
            suite: 
            imShared: 
            configFile: 
            duration:
            exportLog: 
            exportStatReportList: 
            exportStats: 
            exportStatsFormat: 
            exportStatsHtml: 
            labels:
            overrideRmLabels:
            overwrite: 
            publish: 
            publishFor: 
            publishReports: 
            rate:
            reportHistory:
            results: 
            swapDatasets:
            userComments:             
            users:
            varFile:
            vmArgs:
```
7. Replace the example input values with your details.
8. Push it into the main branch
9. Go to the Actions section in the repository and select the workflow.
10. Click the Run workflow dropdown and the list of input boxes get displayed.

To configure agent:
1. Go to settings (Repo).
2. Select action -> runner.
3. Click Create self-hosted runner, follow the download and configure instruction

## Inputs

### `workspace`

**Required** Complete path to Eclipse workspace, required if configFile is not specified.

### `project`

**Required** The name of the project containing the test, required if configFile is not specified.

### `suite`

**Required** Specify the relative path from the project to the test including the file name of the test. A test can be a Performance test, Schedule, or Compound test and required if configFile is not specified.

### `imShared`

**Optional** Complete path to HCLIMShared location, if it is not at default location.

### `configFile`

**Optional** The complete path to a file that contains the parameters for a test or schedule run. If Config file is specified then no other fields will be required.

### `duration`

**Optional** You can use this option to specify the duration of the stages in the Rate Schedule.

### `exportLog`

**Optional** You can use this option to specify the file directory path to store the exported HTTP test log. You can provide multiple parameter entries when running multiple tests. You must use a colon to separate the parameter entries. For example: c:/logexport.txt:c:/secondlogexport.txt

### `exportStatReportList`

**Optional** You can use this option to specify a comma-separated list of report IDs along with exportstats or exportstatshtml to list the reports that you want to export in place of the default reports, or the reports selected under Preferences. To retrieve the report IDs, navigate to Window > Preferences > Test > Performance Test Reports > Export Reports from HCL OneTest™ Performance and under Select reports to export, select the required reports, and click Copy ID to clipboard.

### `exportStats`

**Optional** Use this option to provide the complete path to a directory that you can use to store the exported report in a comma-separated values (CSV) format.

### `exportStatsFormat`
**Optional** Use this option to enter one or more formats for the reports that you want to export by using a comma as a separator. The options are simple.csv, full.csv, simple.json, full.json, csv, and json. When you want to export both simple and full reports in json or csv format, you can specify json or csv as the options. The reports are saved to the location specified in the exportStats field. This field must be used in conjunction with exportStats field.

### `exportStatsHtml`
**Optional** Use this option to provide the complete path to a directory that you can use to export web analytic results. You can analyze the results on a web browser without using HCL OneTest™ Performance.

### `labels`
**Optional** Use this option to add labels to test results. To add multiple labels to a test result, you must separate each label by using a comma.

### `overrideRmLabels`
**Optional** Use this option to enable the Resource Monitoring from Service option for a performance schedule if the Resource Monitoring from Service option is not enabled from the schedule editor in HCL OneTest™ Performance, ignore Resource Monitoring sources that were set in the performance schedule and to change for a label matching mode, replace an existing set of Resource Monitoring labels that were set in the performance schedule and run the schedule with a new set of Resource Monitoring labels.

### `overwrite`
**Optional** Determines whether a result file with the same name is overwritten. The default value, false, indicates that the new result file is created. If the value is true, the file is overwritten and retains the same file name.

### `publish`
**Optional** YYou can use this option to publish test results to the Server. The format is: serverURL#project.name=projectName&teamspace.name=teamspaceName. If the name of the project or team space contains a special character, then you must replace it with %<Hex_value_of_special_character>.

### `publishFor`
**Optional** You can use this option to publish the test results based on the completion status of the tests, supported values are FAIL,PASS,INCONCLUSIVE,ERROR,ALL.

### `publishReports`
**Optional** You can use this option to specify the reports to be published to HCL OneTest Server. The supported values are STATS,TESTLOG.

### `rate`
**Optional** Use this option to specify a rate that you want to achieve for a workload in the Rate Runner group. For example, "Rate Runner Group 1=1/s, 3/m", where, Rate Runner Group1 is the name of the rate runner group that has two stages. The desired rate for the first stage is one iteration per second and the rate for the second stage is three iterations per minute.

### `results`
**Optional** Use this option to specify the name of the results file. The default name of the result file is the test or schedule name with a timestamp appended. You must specify a folder name that is relative to the project to store the test results.

### `reportHistory`
**Optional** Use this option when you want to view a record of all events that occurred during a test or schedule run. Supported values are jaeger, testlog, null.

### `swapDatasets`

**Optional** Use this option to replace dataset values during a test or schedule run. You must ensure that both original and new datasets are in the same workspace and have the same column names. You must also include the path to the dataset. For example, /project_name/ds_path/ds_filename.csv:/project_name/ds_path/new_ds_filename.csv

### `userComments`
**Optional** Use this option to add text that you want to display in the user comments row of the report.

### `users`
**Optional** Overrides the default number of virtual users in the run. For a schedule, the default is the number of users specified in the schedule editor. For a test, the default is one user.

### `varFile`
**Optional** Use this option to specify the complete path to the XML file that contains the variable initialization.

### `vmArgs`
**Optional** Use this option to specify the Java maximum heap size for the Java process that controls the playback. For example, when you input the value as -Xmx4096m, it specifies the maximum heap size as 4GB.
