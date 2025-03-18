# Basic Administration

## Registering SAP CPI Credentials

### 1. Access the Credential Manager:

* Log in to the ReleaseOwl dashboard.
* Navigate to the Administration view.
* Select the Credential Manager section.

<figure><img src="../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

* Click the Register Credential link to add a new credential.

<figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

**Fill in the Necessary Fields:**

* Credential Name: Enter a name for easy reference.
* Credential Type: Select SAP Cloud Environment from the dropdown.
* Authentication Type: Choose OAuth2 as the authentication method.

<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

**Enter OAuth2 Details:**

Retrieve the following details from the service key of your SAP CPI instance:

* Client ID: Found under clientid in the service key.
* Client Secret: Found under clientsecret in the service key.
* Token URL: Found under url in the service key.

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

Fill in the fields in the Credential dialog:

* Client ID: Paste the clientid from the service key.
* Client Secret: Paste the clientsecret from the service key.
* Token URL: Paste the token URL from the service key.

<figure><img src="../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

* Click Save to store the credential.

<figure><img src="../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

### CPI Environment Registration

1. Navigate to Environments from the Administration menu.
2. Select CPI environment and click on register CPI environment.
3. &#x20;Provide the following details:

| Field                            | Description                                                                                                                     |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Name                             | Enter a unique name for the SAP CPI Environment.                                                                                |
| Auth Type                        | Select the authentication type: Basic Auth or OAuth2.                                                                           |
| API URL                          | Provide the API URL for connecting to the SAP CPI Environment.                                                                  |
| Enable Test Automation(Optional) | Toggle to enable or disable test automation capabilities.                                                                       |
| IFLOW OAuth Credential           | Select the OAuth credentials used for IFLOW authentication.                                                                     |
| IFLOW URL                        | Enter the IFlow URL from the service key                                                                                        |
| Use Custom IdP                   | Enable this option to setup custom Identity Provider (IdP). The process is outlined in the below section.                       |
| SSO URL                          | Provide the Single Sign-On (SSO) URL for authentication.                                                                        |
| Email Address                    | Enter the service user email address.                                                                                           |
| Integration Advisor              | Enable Integration Advisor to provide the Host URL.                                                                             |
| Host URL                         | The host URL is the base address of your SAP Integration Suite instance. (https://.integrationsuite-.cfapps..hana.ondemand.com) |
| Enable Git(Optional)             | Enable this option to integrate Git with the environment.                                                                       |
| Git Credential                   | Select the credential for accessing the Git repository.                                                                         |
| Repository URL                   | Provide the Git repository URL.                                                                                                 |
| Branch                           | Specify the branch to be used for the integration.                                                                              |
| Environment Type                 | Select the environment type (e.g., Dev, QA, Prod).                                                                              |

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

### Custom Identity Provider (IDP) Setup and Configuration <a href="#toc190778976" id="toc190778976"></a>

A Custom IDP (Identity Provider) must be configured to allow secure authentication and authorization for users who interact with the Integration Suite (CPI) instance through ReleaseOwl.

Use Case: This is particularly useful for executing test cases, simulation testing and updating value mappings as part of the pipeline.

### Steps to configure custom IDP

Custom IDP (Identity Provider) is necessary for deploying certain artifact types, such as value mapping, REST, SOAP, and OData APIs. It is also essential for executing test cases associated with the artifacts.

1\.      Copy the SAP BTP SSO URL from the downloaded SAML metadata. This value is the URL provided for the "**Location**" attribute in the tag “AssertionConsumerService”. Example: \<md:AssertionConsumerService Binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST" Location="https://xyz.authentication.us10.hana.ondemand.com/saml/SSO/alias/xyz.aws-live" index="0" isDefault="true"/>

<figure><img src="../../.gitbook/assets/image (218).png" alt=""><figcaption></figcaption></figure>

2. Click on Download Entity Descriptor to download the tenant-specific and SAP CPI Environment metadata descriptor.

<figure><img src="../../.gitbook/assets/image (219).png" alt=""><figcaption></figcaption></figure>

3. Go to Trust configuration in SAP BTP Cockpit and click on new SAML Trust configuration. Upload ReleaseOwl CPI Environment metadata xml in SAP BTP Trust configuration as below.

<figure><img src="../../.gitbook/assets/image (220).png" alt=""><figcaption></figcaption></figure>

4. Uncheck the option "**Available for User Logon**" to ensure that SAP does not list this IDP during the login process.
5. Add Role collection mappings for the IdP:  PI\_Administrator, PI\_Business\_Expert, PI\_Integration\_Developer. With attribute value “emailAddress” to value of the service-user (The same user basic auth credential should be linked to CPI Environment) in whose mail ID the updates should happen.

<figure><img src="../../.gitbook/assets/image (221).png" alt=""><figcaption></figcaption></figure>

6\.      Assign role collection mapping for the IDP that is required for Integration Advisor:

iadv-content-read ,iadv-content-administrator. With attribute value “emailAddress” to value of the service-user (The same user basic auth credential should be linked to CPI Environment) in whose mail ID the updates should happen.

### **Adding Integration Suite Environments to the Project**

For artifacts to load in SAP CPI Management page, the Integration Suite environments must be registered in Project Settings in ReleaseOwl.

To register SAP Integration Suite environment:

1\. Go to Projects drop down at the top right corner and click Project Settings.

2\. In Project Settings, go to Environment.

3\. The following screen is displayed.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/sap-cpi-cloud-environment-registration-5.jpg" alt=""><figcaption></figcaption></figure>

4\. Click Add Environment to add a new environment in ReleaseOwl.

5\. In the subsequent screen, choose the required environment from the list displayed by selecting Source. Only the artifacts with source are synced to ReleaseOwl.

6\. The environment is added to the corresponding project in ReleaseOwl.

7\. Click Permissions (under Users tab in Project Settings), to add users that can access (read or deploy to) the registered CPI environment.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/sap-cpi-cloud-environment-registration-6.jpg" alt=""><figcaption></figcaption></figure>

Click Permissions. The roles that are assigned to the selected user are seen.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/sap-cpi-cloud-environment-registration-7.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** On clicking Permissions in the above screen, one can know the actions that the user role can perform each for the available features such as Transport Management, Change Management, Pipelines, Release Management.
{% endhint %}

### Managing CPI Packages

#### 1. Access SAP CPI Management:

* Switch to the Project view.
* Click on SAP CPI Management in the Build section.

<figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

#### 2. Add and Sync Packages:

* Click the Add Packages button in the CPI Packages section.
* Select Package: Use the search bar to find a package, then check the box next to the desired package(s).
* Sync Package: Click Sync to add and synchronize the selected package(s).

<figure><img src="../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

A pop-up screen will display the sync history. Use the Refresh button to update the sync status and view the latest details. Click Close when done.

<figure><img src="../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

#### 3. Configure Artifacts:

* Click the arrow next to the package name.

<figure><img src="../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

* In the "**Artifacts**" list, click the three dots in the "**Actions**" column for the desired artifact.
* Select "**Configure**" from the dropdown menu.

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

* Modify the required values in the configuration screen.

#### 4. Save Changes:

* Save: Update the existing artifact directly.
* Save as Artifact: Create a new version of the artifact with the modified values.

<figure><img src="../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

* After selecting "**Save as Artifact**", a new artifact is created with the updated values.
* To view more details about the new artifact, click the three dots (Actions) next to it.

<figure><img src="../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

* Click on "**Edit Configuration**" to open the artifact configuration and verify the updated values.

<figure><img src="../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

### Creating a Release Pipeline

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

#### 1. Create a New Release Pipeline:

* Switch to the Project view and select the Release section.
* Navigate to Release Pipelines and click on Create New Release Pipeline.

<figure><img src="../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

* Provide a Pipeline Name.

<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

* Add stages (e.g., QA, Prod) and assign tasks to each stage.

<figure><img src="../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

#### 2. Add Deployment Tasks:

* Click the Add button in a task stage to include deployment tasks.
*   Fill in the required details:

    * Name: Enter a preferred name for the deployment task.
    * Deploy Type: Select the type of deployment.
    * Select CPI Environment: Select the target CPI environment where the deployment will take place.
    *   Deployment Action: Choose between:

        * Upload Only: Uploads the deployment package without executing the deployment.
        * Upload and Deploy: Uploads the deployment package and executes the deployment.



    <figure><img src="../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

#### 3. Save and Configure Notifications:

* Add notification emails if needed.
* Save the pipeline configuration.

<figure><img src="../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

### Managing Sprints and User Stories

#### 1. Create a Sprint:

* In the Project View, navigate to Change Management and click Create Sprint.

<figure><img src="../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

* Enter the sprint name and click Save.

<figure><img src="../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

* Click the three dots (Actions) button and select Start Sprint.

<figure><img src="../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

#### 2. Create a User Story:

* Go to User Stories and click Create User Story.

<figure><img src="../../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

* Fill in the required details:
  * Summary: Provide a summary of the user story.
  * Type: Select the type of story.
* Click Save.

<figure><img src="../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

#### 3. Edit and Promote User Story:

* After creating the user story, click the three dots (Actions) and select Edit.
* Select the release pipeline and associated component.

<figure><img src="../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

* Add the artifact in CPI Artifacts and click Save.

<figure><img src="../../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

* To promote the user story, click the three dots (Actions) and select Promote.

<figure><img src="../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

You can view the Deploy Logs in the ReleaseOwl Dashboard under the SAP CPI Deploy Logs window after promoting the user story.

<figure><img src="../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

* **Upload Status**: Indicates whether the artifact was successfully uploaded.
* **Config Status**: Confirms if the configuration for new or updated artifacts was successful.
* **Deploy Status:** Reflects the final deployment status of the artifact.

