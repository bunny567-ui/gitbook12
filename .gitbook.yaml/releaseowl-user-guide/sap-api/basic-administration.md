# Basic Administration

**1. Navigate to Credential Manager**

* From the Administration menu, go to **Credential Manager**.
* Click **Register Credential**.

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**2. Provide Credential Details**

* **a. Credential Name**: Enter any identifiable name for the credential.
* **b. Credential Type**: Select **API Management**.
* **c. Authentication Type**: Select **OAuth2**.
* **d. Client ID, Client Secret, and Token URL**: Follow the steps below to retrieve these details.

<figure><img src="../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

### Steps to Retrieve API Management Details from SAP BTP Cockpit

**4. Access the SAP BTP Cockpit**

1\.      Go to SAP BTP cockpit.

2\.      Select the subaccount that hosts your SAP Cloud Integration application.

3\.      Choose your subaccount, navigate to Services ->Service Marketplace, and select Process Integration Runtime and Choose Create.

4\.      Provide the details as shown below

a)      **Service**: SAP Process Integration Runtime

b)     **Plan:** API

c)      **Runtime environment:** Cloud Foundry

d)     **Space:** Provide the space name

e)      **Instance name:** Provide any name for the instance

<figure><img src="../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

f) Select the roles as mentioned below and click on create.

| Role                       | Description                                                                                                          |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| MessagePayloadsRead        | Allows users to read and view message payloads within the integration runtime environment.                           |
| MonitoringDataRead         | Grants permission to access and view monitoring data related to integration flows, messages, and system performance. |
| TraceConfigurationEdit     | Allows users to update tracing settings for integration flows.                                                       |
| TraceConfigurationRead     | Allows users to read the current tracing configuration of integration flows.                                         |
| WorkspaceArtifactsDeploy   | Grants permission to deploy integration artifacts from the design workspace to runtime environments.                 |
| WorkspacePackagesConfigure | Allows users to configure integration packages in the workspace, including defining parameters and dependencies.     |
| WorkspacePackagesRead      | Provides read-only access to integration packages in the workspace.                                                  |
| WorkspacePackagesEdit      | Allows users to modify integration packages, including artifact updates and configuration changes.                   |

&#x20;

### **Steps to Create Service Key**

**7. Add Service Key**

* In the **SAP BTP Cockpit**, go to **Instances and Subscriptions**.
* Locate the instance **API Management, API portal** with the plan **apiportal-apiaccess**.
* Under the **Actions** column, choose **Create Service Key**.
* Provide a name for the service key under **Service Key Name**.
* Click **Create**.

<figure><img src="../../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

**8. Copy Service Key Details**

* Select the newly created service key to display its details.
*   Copy the following details:

    * **Client ID**
    * **Client Secret**
    * **Token URL**

    <figure><img src="../../.gitbook/assets/image (14) (1).png" alt=""><figcaption></figcaption></figure>

### Steps to Complete Credential Registration in ReleaseOwl

**9. Enter Service Key Details in ReleaseOwl**

* Use the copied details from the service key:
  * **d. Client ID**: Paste the Client ID.
  * **e. Client Secret**: Paste the Client Secret.
  * **f. Token URL**: Paste the Token URL.

**10. Save Credential**

* Click **Save**.
* The credential will appear in the **List of Credentials**.

<figure><img src="../../.gitbook/assets/image (15) (1).png" alt=""><figcaption></figcaption></figure>

