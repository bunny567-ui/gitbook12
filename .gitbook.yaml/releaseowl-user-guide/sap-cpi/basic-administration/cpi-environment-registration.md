# CPI Environment Registration

1\.      Navigate to Environments from the Administration menu.

2\.      Select CPI environment and click on register CPI environment.

<figure><img src="../../../.gitbook/assets/image (962).png" alt=""><figcaption></figcaption></figure>

3\.      Provide the following details:

| Field                            | Description                                                                                               |
| -------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Name                             | Enter a unique name for the SAP CPI Environment.                                                          |
| Auth Type                        | Select the authentication type: Basic Auth or OAuth2.                                                     |
| API URL                          | Provide the API URL for connecting to the SAP CPI Environment.                                            |
| Enable Test Automation(Optional) | Toggle to enable or disable test automation capabilities.                                                 |
| IFLOW OAuth Credential           | Select the OAuth credentials used for IFLOW authentication.                                               |
| IFLOW URL                        | Enter the IFlow URL from the service key                                                                  |
| Use Custom IdP                   | Enable this option to setup custom Identity Provider (IdP). The process is outlined in the below section. |
| SSO URL                          | Provide the Single Sign-On (SSO) URL for authentication.                                                  |
| Email Address                    | Enter the service user email address                                                                      |
| Host URL                         | Provide the Host URL for the SAP CPI Environment.                                                         |
| Enable Git(Optional)             | Enable this option to integrate Git with the environment.                                                 |
| Git Credential                   | Select the credential for accessing the Git repository.                                                   |
| Repository URL                   | Provide the Git repository URL.                                                                           |
| Branch                           | Specify the branch to be used for the integration.                                                        |
| Environment Type                 | Select the environment type (e.g., Dev, QA, Prod).                                                        |

<figure><img src="../../../.gitbook/assets/image (961).png" alt=""><figcaption></figcaption></figure>

### Custom Identity Provider (IDP) Setup and Configuration <a href="#toc190778976" id="toc190778976"></a>

A Custom IDP (Identity Provider) must be configured to allow secure authentication and authorization for users who interact with the Integration Suite (CPI) instance through ReleaseOwl.

Use Case: This is particularly useful for executing test cases, simulation testing and updating value mappings as part of the pipeline.

### Steps to configure custom IDP

Custom IDP (Identity Provider) is necessary for deploying certain artifact types, such as value mapping, REST, SOAP, and OData APIs. It is also essential for executing test cases associated with the artifacts.

1\.      Copy the SAP BTP SSO URL from the downloaded SAML metadata. This value is the URL provided for the "Location" attribute in the tag “AssertionConsumerService”. Example: \<md:AssertionConsumerService Binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST" Location="https://xyz.authentication.us10.hana.ondemand.com/saml/SSO/alias/xyz.aws-live" index="0" isDefault="true"/>

<figure><img src="../../../.gitbook/assets/image (964).png" alt=""><figcaption></figcaption></figure>

2\.      Click on Download Entity Descriptor to download the tenant-specific and SAP CPI Environment metadata descriptor.

<figure><img src="../../../.gitbook/assets/image (965).png" alt=""><figcaption></figcaption></figure>

&#x20;

3\.      Go to Trust configuration in SAP BTP Cockpit and click on new SAML Trust configuration. Upload ReleaseOwl CPI Environment metadata xml in SAP BTP Trust configuration as below.

<figure><img src="../../../.gitbook/assets/image (966).png" alt=""><figcaption></figcaption></figure>

4\.      Uncheck the option "Available for User Logon" to ensure that SAP does not list this IDP during the login process.

5\.      Add Role collection mappings for the IdP:  PI\_Administrator, PI\_Business\_Expert, PI\_Integration\_Developer. With attribute value “emailAddress” to value of the service-user (The same user basic auth credential should be linked to CPI Environment) in whose mail ID the updates should happen.

<figure><img src="../../../.gitbook/assets/image (967).png" alt=""><figcaption></figcaption></figure>

6\.  Assign role collection mapping for the IDP that is required for Integration Advisor:

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

On clicking Permissions in the above screen, one can know the actions that the user role can perform each for the available features such as Transport Management, Change Management, Pipelines, Release Management.
