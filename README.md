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
![image](https://user-images.githubusercontent.com/48479537/134671751-c9b0436d-b65c-47f4-8fd3-6e2081aabebf.png)

![image](https://user-images.githubusercontent.com/48479537/134673646-2dd9d70e-ba81-4213-8003-6cd4bfa481e8.png)

![image](https://user-images.githubusercontent.com/48479537/134674251-6456b31d-a76e-4751-9f2f-d640cb723e30.png)

![image](https://user-images.githubusercontent.com/48479537/134674591-f91b4bc8-2ff9-4e30-adb4-9c338db609db.png)


# License

Apache license 2.0
