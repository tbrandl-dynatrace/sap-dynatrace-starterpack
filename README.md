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

# License

Apache license 2.0
