# Basic Administration

### Access the Credential Manager: <a href="#pdf-page-della43ge2ynalx23r7p-id-1.-access-the-credential-manager" id="pdf-page-della43ge2ynalx23r7p-id-1.-access-the-credential-manager"></a>

* Log in to the ReleaseOwl dashboard.
* Navigate to the Administration view.
* Select the Credential Manager section.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fk800L6JDYJwQBgE8mEJe%252Fimage.png%3Falt%3Dmedia%26token%3D397cdf1f-59cf-4fba-9798-9d771c71fcc1&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4d48d67&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click the Register Credential link to add a new credential.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fiw8wzydLO5hixKHCXbq5%252Fimage.png%3Falt%3Dmedia%26token%3D47f804b4-c21a-4044-8f85-6774339cf8b9&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1c5a07e9&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Fill in the Necessary Fields:**

* Credential Name: Enter a name for easy reference.
* Credential Type: Select SAP Cloud Environment from the dropdown.
* Authentication Type: Choose OAuth2 as the authentication method.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FoILqxO8vxpW7E2niPaer%252Fimage.png%3Falt%3Dmedia%26token%3D78b2a965-fe12-41b0-a806-464c81516c04&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5bbcb69d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Enter OAuth2 Details:**

Retrieve the following details from the service key of your SAP CPI instance:

* Client ID: Found under clientid in the service key.
* Client Secret: Found under clientsecret in the service key.
* Token URL: Found under url in the service key.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fld3REShXTgri2uFCrKLS%252Fimage.png%3Falt%3Dmedia%26token%3D6a8c489b-80e9-42a1-9eeb-c2754c38b438&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=346c58a5&#x26;sv=2" alt=""><figcaption></figcaption></figure>

Fill in the fields in the Credential dialog:

* Client ID: Paste the clientid from the service key.
* Client Secret: Paste the clientsecret from the service key.
* Token URL: Paste the token URL from the service key.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F45whsd3NvhnFX5GErK32%252Fimage.png%3Falt%3Dmedia%26token%3Deafb1204-87b9-4cb0-873f-b2fd8d6c9dfe&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b14cfb92&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click Save to store the credential.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FHK3NGtqd7YihiS3dNyhK%252Fimage.png%3Falt%3Dmedia%26token%3Db5da0244-75db-4857-87c8-4f47eccc3ab7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f780e1a8&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### CPI Environment Registration <a href="#pdf-page-della43ge2ynalx23r7p-cpi-environment-registration" id="pdf-page-della43ge2ynalx23r7p-cpi-environment-registration"></a>

1. Navigate to Environments from the Administration menu.
2. Select CPI environment and click on register CPI environment.
3. Provide the following details:

| **Field**                               | **Description**                                                                                                                                                          |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Name**                                | Enter a unique name for the SAP CPI Environment.                                                                                                                         |
| **Auth Type**                           | Select the authentication type: **Basic Auth** or **OAuth2**.                                                                                                            |
| **API URL**                             | Provide the API URL for connecting to the SAP CPI Environment.                                                                                                           |
| **Enable Test Automation** _(Optional)_ | Toggle to enable or disable test automation capabilities.                                                                                                                |
| **IFLOW OAuth Credential**              | Select the OAuth credentials used for IFLOW authentication.                                                                                                              |
| **IFLOW URL**                           | Enter the IFLOW URL from the service key.                                                                                                                                |
| **Use Custom IdP**                      | Enable this option to set up a custom Identity Provider (IdP). _Note_: The setup process is outlined in the section below.                                               |
| **SSO URL**                             | Provide the Single Sign-On (SSO) URL for authentication.                                                                                                                 |
| **Email Address**                       | Enter the service user email address.                                                                                                                                    |
| **Integration Advisor**                 | Enable Integration Advisor to provide the Host URL.                                                                                                                      |
| **Host URL**                            | The host URL is the base address of your SAP Integration Suite instance. _(Example: https://\<subdomain>.integrationsuite-\<region>.cfapps.\<domain>.hana.ondemand.com)_ |
| **Enable Git** _(Optional)_             | Enable this option to integrate Git with the environment.                                                                                                                |
| **Git Credential**                      | Select the credential for accessing the Git repository.                                                                                                                  |
| **Repository URL**                      | Provide the Git repository URL.                                                                                                                                          |
| **Branch**                              | Specify the branch to be used for the integration.                                                                                                                       |
| **Environment Type**                    | Select the environment type (e.g., **Dev**, **QA**, **Prod**).                                                                                                           |

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FPe2tkiskOjZvpg2MxrA4%252Fimage.png%3Falt%3Dmedia%26token%3Ddf4d7ea5-a2a3-4987-8f64-5da1cde3c138&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3ae47f55&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Custom Identity Provider (IDP) Setup and Configuration <a href="#pdf-page-della43ge2ynalx23r7p-toc190778976" id="pdf-page-della43ge2ynalx23r7p-toc190778976"></a>

A Custom IDP (Identity Provider) must be configured to allow secure authentication and authorization for users who interact with the Integration Suite (CPI) instance through ReleaseOwl.

Use Case: This is particularly useful for executing test cases, simulation testing and updating value mappings as part of the pipeline.

### Steps to configure custom IDP <a href="#pdf-page-della43ge2ynalx23r7p-steps-to-configure-custom-idp" id="pdf-page-della43ge2ynalx23r7p-steps-to-configure-custom-idp"></a>

Custom IDP (Identity Provider) is necessary for deploying certain artifact types, such as value mapping, REST, SOAP, and OData APIs. It is also essential for executing test cases associated with the artifacts.

1\. Copy the SAP BTP SSO URL from the downloaded SAML metadata. This value is the URL provided for the "**Location**" attribute in the tag “AssertionConsumerService”. Example: \<md:AssertionConsumerService Binding="urn:oasis:names:tc:SAML:2.0:bindings:HTTP-POST" Location="https://xyz.authentication.us10.hana.ondemand.com/saml/SSO/alias/xyz.aws-live" index="0" isDefault="true"/>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FFzLeJBWKoXPer2uAYjdp%252Fimage.png%3Falt%3Dmedia%26token%3D20ced9da-c78b-4c84-a7a3-4e1f4a928fc8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=61da5594&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. Click on Download Entity Descriptor to download the tenant-specific and SAP CPI Environment metadata descriptor.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FfOf3OW02XFh4aRswCKhN%252Fimage.png%3Falt%3Dmedia%26token%3D6dea107a-1937-46f5-84b8-53e9793f4636&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f59c5afb&#x26;sv=2" alt=""><figcaption></figcaption></figure>

3. Go to Trust configuration in SAP BTP Cockpit and click on new SAML Trust configuration. Upload ReleaseOwl CPI Environment metadata xml in SAP BTP Trust configuration as below.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FW3b54rJxrQXthjWrEcgF%252Fimage.png%3Falt%3Dmedia%26token%3D69e69252-fed6-4ab1-8d20-ac72dd03e8d1&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=88b63aff&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Uncheck the option "**Available for User Logon**" to ensure that SAP does not list this IDP during the login process.
5. Add Role collection mappings for the IdP: PI\_Administrator, PI\_Business\_Expert, PI\_Integration\_Developer. With attribute value “emailAddress” to value of the service-user (The same user basic auth credential should be linked to CPI Environment) in whose mail ID the updates should happen.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FFKY1s3oc7Poh4O3XDTTb%252Fimage.png%3Falt%3Dmedia%26token%3D59dc599f-cf18-4f9f-ac8e-9ed53f88484c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a1a84392&#x26;sv=2" alt=""><figcaption></figcaption></figure>

6\. Assign role collection mapping for the IDP that is required for Integration Advisor:

iadv-content-read ,iadv-content-administrator. With attribute value “emailAddress” to value of the service-user (The same user basic auth credential should be linked to CPI Environment) in whose mail ID the updates should happen.

### **Adding Integration Suite Environments to the Project** <a href="#pdf-page-della43ge2ynalx23r7p-adding-integration-suite-environments-to-the-project" id="pdf-page-della43ge2ynalx23r7p-adding-integration-suite-environments-to-the-project"></a>

For artifacts to load in SAP CPI Management page, the Integration Suite environments must be registered in Project Settings in ReleaseOwl.

To register SAP Integration Suite environment:

1\. Go to Projects drop down at the top right corner and click Project Settings.

2\. In Project Settings, go to Environment.

3\. The following screen is displayed.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2Fwww.docs.releaseowl.com%2Fassets%2Fimg%2Fsap-cpi-cloud-environment-registration-5.jpg&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c8b46193&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4\. Click Add Environment to add a new environment in ReleaseOwl.

5\. In the subsequent screen, choose the required environment from the list displayed by selecting Source. Only the artifacts with source are synced to ReleaseOwl.

6\. The environment is added to the corresponding project in ReleaseOwl.

7\. Click Permissions (under Users tab in Project Settings), to add users that can access (read or deploy to) the registered CPI environment.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2Fwww.docs.releaseowl.com%2Fassets%2Fimg%2Fsap-cpi-cloud-environment-registration-6.jpg&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=15339cc6&#x26;sv=2" alt=""><figcaption></figcaption></figure>

Click Permissions. The roles that are assigned to the selected user are seen.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2Fwww.docs.releaseowl.com%2Fassets%2Fimg%2Fsap-cpi-cloud-environment-registration-7.jpg&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b374d431&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Note:** On clicking Permissions in the above screen, one can know the actions that the user role can perform each for the available features such as Transport Management, Change Management, Pipelines, Release Management.

## Managing CPI Packages <a href="#pdf-page-della43ge2ynalx23r7p-managing-cpi-packages" id="pdf-page-della43ge2ynalx23r7p-managing-cpi-packages"></a>

**1. Access SAP CPI Management:**

* Switch to the Project view.
* Click on SAP CPI Management in the Build section.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FDY8532JKy97FEAWNGPfE%252Fimage.png%3Falt%3Dmedia%26token%3D00cb54fa-b689-44c4-8a5c-b18fcd32a372&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=dfb3b10c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**2. Add and Sync Packages:**

* Click the Add Packages button in the CPI Packages section.
* Select Package: Use the search bar to find a package, then check the box next to the desired package(s).
* Sync Package: Click Sync to add and synchronize the selected package(s).

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FBNGQqBvJpmRLkGVzkx7M%252Fimage.png%3Falt%3Dmedia%26token%3D081d0983-b4a0-47fd-a432-1d12da109b45&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9e4788de&#x26;sv=2" alt=""><figcaption></figcaption></figure>

A pop-up screen will display the sync history. Use the Refresh button to update the sync status and view the latest details. Click Close when done.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FxR53HIUnszNwQpGhGb1a%252Fimage.png%3Falt%3Dmedia%26token%3D63951d9a-ab11-4c12-8d36-aecaa4479eeb&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=815929b6&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**3. Configure Artifacts:**

* Click the arrow next to the package name.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F4ZoUhbOgzp6AfiRbV5bC%252Fimage.png%3Falt%3Dmedia%26token%3D479e8317-51ac-48b5-8ad6-ade48805d128&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c753ab50&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* In the "**Artifacts**" list, click the three dots in the "**Actions**" column for the desired artifact.
* Select "**Configure**" from the dropdown menu.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FlbZM9a8r4g2vTGwlhBOq%252Fimage.png%3Falt%3Dmedia%26token%3Da9355e5e-b1d2-41d0-8761-ed0577d87228&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=11f2a353&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Modify the required values in the configuration screen.

**4. Save Changes:**

* Save: Update the existing artifact directly.
* Save as Artifact: Create a new version of the artifact with the modified values.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FLHWBcEw5gF3LF8PUl8wb%252Fimage.png%3Falt%3Dmedia%26token%3D338402a3-8ef4-4009-bc8d-f36a8ddb0bf5&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=464c2fdd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* After selecting "**Save as Artifact**", a new artifact is created with the updated values.
* To view more details about the new artifact, click the three dots (Actions) next to it.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FLY2gyFZQ4zxQSdQYgSBD%252Fimage.png%3Falt%3Dmedia%26token%3D5ad8a9b2-8307-492e-a565-068daefe35b4&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a36fc8b8&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click on "**Edit Configuration**" to open the artifact configuration and verify the updated values.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FIVpiCFhc5IWKJ3lvVNO2%252Fimage.png%3Falt%3Dmedia%26token%3D34ed57b3-47a9-4a47-99b0-0dfd82803bed&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9caf00f0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Creating a Release Pipeline <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

#### **1. Create a New Release Pipeline:**

* Switch to the Project view and select the Release section.
* Navigate to Release Pipelines and click on Create New Release Pipeline.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FXhYGhFplDlLXx78KjgLs%252Fimage.png%3Falt%3Dmedia%26token%3D023e5378-ac92-4f1c-a2ea-4a57531c4b5a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=160216a8&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Provide a Pipeline Name.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F02Nu3sYI7jhLWH36mwUk%252Fimage.png%3Falt%3Dmedia%26token%3Db0546bb3-8bb9-4902-889b-4ac5022d1e6c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=18908539&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Add stages (e.g., QA, Prod) and assign tasks to each stage.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fp9bYnD6MU10rrjza1IzY%252Fimage.png%3Falt%3Dmedia%26token%3D7e30a12a-4061-483e-a9a2-06d82b9f2caf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3549c696&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**2. Add Deployment Tasks:**

* Click the Add button in a task stage to include deployment tasks.
*   Fill in the required details:

    * Name: Enter a preferred name for the deployment task.
    * Deploy Type: Select the type of deployment.
    * Select CPI Environment: Select the target CPI environment where the deployment will take place.
    * Deployment Action: Choose between:
      * Upload Only: Uploads the deployment package without executing the deployment.
      * Upload and Deploy: Uploads the deployment package and executes the deployment.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F0cCugnYu2HHv1bBf3XwA%252Fimage.png%3Falt%3Dmedia%26token%3D28a6b6e7-163f-457b-8619-c9aa2a260498&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f952c3b7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**3. Save and Configure Notifications:**

* Add notification emails if needed.
* Save the pipeline configuration.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FDW5AwYxweav5t3jazGeI%252Fimage.png%3Falt%3Dmedia%26token%3Dd6cf62fb-9b18-43e6-8486-ef397c3ae2e3&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=cca39b71&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### Managing Sprints and User Stories <a href="#pdf-page-della43ge2ynalx23r7p-managing-sprints-and-user-stories" id="pdf-page-della43ge2ynalx23r7p-managing-sprints-and-user-stories"></a>

**1. Create a Sprint:**

* In the Project View, navigate to Change Management and click Create Sprint.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FmNKU2sdABLSdYD8THBMJ%252Fimage.png%3Falt%3Dmedia%26token%3D148b7df6-3388-4f68-8608-f07fcfca3bc2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d26feb3a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Enter the sprint name and click Save.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fe1LV3pYaq8dIsceMCoXr%252Fimage.png%3Falt%3Dmedia%26token%3D6135bc9b-ee72-40bb-ad18-74d42f8e8c37&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=29d3f868&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click the three dots (Actions) button and select Start Sprint.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FNDMKoPBrp2ayYaDaiwEc%252Fimage.png%3Falt%3Dmedia%26token%3D144fc05a-7c29-4ab4-bfdf-94c157a48d67&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d8926cd9&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**2. Create a User Story:**

* Go to User Stories and click Create User Story.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FYlwvD3NwEiFem8OD9m5Z%252Fimage.png%3Falt%3Dmedia%26token%3Ddfc50a0f-8c73-4d9f-a01f-32cea788ba3a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2c8f8987&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Fill in the required details:
  * Summary: Provide a summary of the user story.
  * Type: Select the type of story.
* Click Save.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fc9TGaPtrkmNBxUzDYVxD%252Fimage.png%3Falt%3Dmedia%26token%3D28da5785-6e65-4173-a54e-3d851a38f0bc&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=90df48aa&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**3. Edit and Promote User Story:**

* After creating the user story, click the three dots (Actions) and select Edit.
* Select the release pipeline and associated component.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FeD366SyvvQ7ouh2VbX02%252Fimage.png%3Falt%3Dmedia%26token%3D535bf75c-91ba-4574-a5f4-7ae8787b89c0&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=822952da&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Add the artifact in CPI Artifacts and click Save.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FPcITB55xOHIa1iAxWnyl%252Fimage.png%3Falt%3Dmedia%26token%3D9e314683-38d7-43d2-9bc7-4f113664ef35&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4d69f1a7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* To promote the user story, click the three dots (Actions) and select Promote.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F1EFquacxP4WyuxUXUCZF%252Fimage.png%3Falt%3Dmedia%26token%3D18776298-676d-4d55-b0b0-1ba192953b3b&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c4368f77&#x26;sv=2" alt=""><figcaption></figcaption></figure>

You can view the Deploy Logs in the ReleaseOwl Dashboard under the SAP CPI Deploy Logs window after promoting the user story.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FdhXdkl0pUKtuJV6Gywm0%252Fimage.png%3Falt%3Dmedia%26token%3D05473dc5-ec4a-4a83-99c4-6211b496ab7e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b86e793d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* **Upload Status**: Indicates whether the artifact was successfully uploaded.
* **Config Status**: Confirms if the configuration for new or updated artifacts was successful.
* **Deploy Status:** Reflects the final deployment status of the artifact.
