# sap-dynatrace-starterpack

A set of configuration for starting to monitor SAP Fiori and S4/HANA applications, including RFC calls from JCo and NCo using Dynatrace. This can be deployed using [Dynatrace Monitoring as Code (monaco)](https://github.com/dynatrace-oss/dynatrace-monitoring-as-code/).

# How to install
* [Install Dynatrace Monaco](https://dynatrace-oss.github.io/dynatrace-monitoring-as-code/installation)
* Set the Dynatrace environment URL in ```environments.yaml``` (https://xxxxx.live.dynatrace.com for SaaS, https://xxxxxx.dynatrace-managed.com/e/environment-id for Managed)
* Create an API token with the API v1 ```Write Configuration``` permission
* Set the API token as an environment variable
  * Linux: ```export SAP_TOKEN=dtc01.xxxxxxxxx```
  * Windows: ```set SAP_TOKEN=dtc01.xxxxxxxxx```
* (monaco < 2.0) Enable the new command line syntax in monaco
  * Linux: ```export NEW_CLI=1```
  * Windows: ```set NEW_CLI=1```
* Run ```monaco deploy -e environments.yaml --specific-environment sap sap```

# Screenshots
## Analysis of JCo/NCo RFC calls
![image](https://user-images.githubusercontent.com/48479537/134671751-c9b0436d-b65c-47f4-8fd3-6e2081aabebf.png)
## Analysis of Fiori User Sessions
![image](https://user-images.githubusercontent.com/48479537/134673646-2dd9d70e-ba81-4213-8003-6cd4bfa481e8.png)
## Analysis of individual Fiori User Actions and ODATA requests
![image](https://user-images.githubusercontent.com/48479537/134674251-6456b31d-a76e-4751-9f2f-d640cb723e30.png)
## Session Replay for understanding usability problems in the Fiori Application
![image](https://user-images.githubusercontent.com/48479537/134674591-f91b4bc8-2ff9-4e30-adb4-9c338db609db.png)

# What does this do?
* Creating a Custom Service for JCo and NCo RFC connections
* Creating a request attribute for getting the RFC name
* Creating a global request naming rule for naming the RFC requests
* Creating a global error detection rule for ignoring RFC errors with NO_DATA_FOUND
* Creating 2 Applications - S4/HANA Cloud (Monitored using Dynatrace Browser Extension) and Fiori (for adding directly to the Fiori application - see https://blogs.sap.com/2018/07/17/monitoring-a-fiori-launchpad-on-sap-cloud-portal-using-dynatrace./)
  * Creating a user tag for proper naming
  * Creating user action naming rules for better naming of the user actions
  * Setting ```data-sap-ui``` as alternative for data-dtname
  * Setting the custom configuration properties ```exp=1|peti=1``` for working around some Fiori issues

# Support
This is a community-developed project. There is no official Dynatrace support for this project.

# License

Apache license 2.0
