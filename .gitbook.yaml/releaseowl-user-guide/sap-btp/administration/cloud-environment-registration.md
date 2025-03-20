# Cloud Environment Registration

### **Register SAP BTP Environment**

You have to register the SAP BTP login credentials first to access the SAP BTP environment with ReleaseOwl.

Register a new SAP BTP Environment as follows:

1. In Administration View, go to Environments and select SAP Cloud Environment.
2. In the page displayed, click Register Cloud Environment.

The following screen is displayed.

![](https://www.docs.releaseowl.com/assets/img/cloud-environment-registration-1.jpg)\
\


Fill in the required details and save the changes:

| Name            | Enter the name of your choice for the BTP Environment that is being registered.                                                                                                                                                                                                                                                                                                                                                                              |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Region          | Select the appropriate region (represents a geographical location - for e.g., Europe, US East etc.,) where applications, data, or services are hosted.                                                                                                                                                                                                                                                                                                       |
| API Endpoint    | <p>An API endpoint is the point of entry in a communication channel when two systems are interacting.<br>In the Cloud Foundry environment, the region in which a global account was created determines the API endpoint of all subaccounts associated with it.<br>For e.g., subaccounts created in a global account in region eu10 share the API endpoint URL <a href="https://api.cf.eu10.hana.ondemand.com/">https://api.cf.eu10.hana.ondemand.com</a></p> |
| Credential Name | Select any SAP BTP credential registered with ReleaseOwl which can be used to access the SAP BTP environment that is being registered.                                                                                                                                                                                                                                                                                                                       |
| Org             | <p>An Org or Organization is a development account that an individual or multiple collaborators can own and use in the respective SAP BTP environment.<br>Select any value from the dropdown. These values are retrieved by ReleaseOwl app from the SAP BTP environment that is being used.</p>                                                                                                                                                              |
| Space           | <p>A space provides users with access to a shared location for app development, deployment, and maintenance. An org can contain multiple spaces.<br>Select any value from the dropdown. These values are retrieved by ReleaseOwl app from the selected Org from the SAP BTP environment that is being used.</p>                                                                                                                                              |
