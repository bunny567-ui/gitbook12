# Integration Environment Registration

To register the SAP Integration Environment, you must first register the CPI credential. Follow the[ link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-integration-suite/administration/credential-management)and complete the credential setup.

## CPI Environment Registration <a href="#pdf-page-della43ge2ynalx23r7p-cpi-environment-registration" id="pdf-page-della43ge2ynalx23r7p-cpi-environment-registration"></a>

&#x20;**Purpose** :Enable communication with the CPI Environments.

1. Navigate to **Environments** from the **Administration** menu.
2. Select CPI environment and click on register **CPI** environment.
3. Provide the following details:

| **Field**                               | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                                | Enter a unique name for the SAP CPI Environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Auth Type**                           | Select the authentication type: **Basic Auth** or **OAuth2**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **API URL**                             | Provide the **API URL** for connecting to the SAP CPI Environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Enable Test Automation** _(Optional)_ | Toggle to enable or disable test automation capabilities.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **IFLOW OAuth Credential**              | Select the OAuth credentials used for IFLOW authentication.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **IFLOW URL**                           | Enter the IFLOW URL from the service key.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Integration Advisor**                 | Enable Integration Advisor to provide the Host URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Mock Artifacts Prefix**               | Enter any name of your choice. The prefix configured in **Environment Settings** is automatically applied when naming mock artifacts generated during test execution.                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Enable Git** _(Optional)_             | Enable this option to integrate Git with the environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Git Credential**                      | Select the credential for accessing the Git repository.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Repository URL**                      | Provide the Git repository URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Branch**                              | Specify the branch to be used for the integration.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Environment Type**                    | Select the environment type (e.g., **Dev**, **QA**, **Prod**).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Web Authentication**                  | <p>There are <strong>three authentication types</strong> available for CPI Web Authentication in ReleaseOwl:</p><ol><li><strong>None</strong> – No authentication is required.</li><li><strong>Custom Identity Provider (Custom IdP)</strong> – Authentication is performed using a customer-configured Identity Provider.</li><li><strong>SAP Cloud Identity Provider</strong> – Authentication is performed using SAP Cloud Identity Services (IAS).</li><li><strong>SAP Passport</strong> – Authentication is performed using browser-based SAP Passport certificates.</li></ol> |
| **Enable monitoring ( Beta)**           | <p>Check the <strong>Monitoring</strong> option to enable runtime log tracking for deployed artifacts. </p><p></p><p>If an artifact fails during runtime, the logs can be reviewed to identify the cause of the failure and troubleshoot the issue.</p>                                                                                                                                                                                                                                                                                                                             |

<figure><img src="../../../.gitbook/assets/image (1818).png" alt=""><figcaption></figcaption></figure>



**Validate the Environment**

After the environment is created, open the registered environment where the following actions are available:

* **Test** – Use the **Test** option to confirm that the environment connection has been configured successfully.
* **Edit** – Modify the environment details.
* **Delete** – Remove the registered environment.
* **Linked Projects** – Displays all projects associated with the selected environment. This helps users identify which projects are currently using the environment.
* **Logs** – Displays environment-related logs who created it and who modified it .

<figure><img src="../../../.gitbook/assets/image (1820).png" alt=""><figcaption></figcaption></figure>

### Web Authentication : Custom Identity Provider (IDP)  <a href="#pdf-page-della43ge2ynalx23r7p-toc190778976" id="pdf-page-della43ge2ynalx23r7p-toc190778976"></a>

A **Custom Identity Provider (IDP)** is required for deploying certain artifact types—such as **Value Mapping**, **REST**, **SOAP**, and **OData APIs**—as well as for executing test cases associated with these artifacts via ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (1821).png" alt=""><figcaption></figcaption></figure>

**Steps to configure the SSO URL**

1. Navigate to the **Security** section of your SAP BTP Subaccount.
2. Go to **Trust Configuration**.
3. Click **Download SAML Metadata** to download the BTP metadata file.

<figure><img src="../../../.gitbook/assets/image (1100).png" alt=""><figcaption></figcaption></figure>

4. Open the downloaded SAML metadata XML file in a text editor (e.g., Notepad++, VS Code, or a browser).
5. Search for the `<AssertionConsumerService>` tag.
6. In this tag, locate the **Location** attribute. The value of this attribute is your **SAP BTP SSO URL**.

<figure><img src="../../../.gitbook/assets/image (1822).png" alt=""><figcaption></figcaption></figure>

7. Copy the extracted **SSO URL**.
8. Paste it into the **SSO URL** field in the **SAP CPI Environment**.

<figure><img src="../../../.gitbook/assets/image (1824).png" alt=""><figcaption></figcaption></figure>

**Steps to Configure the IDP Auth Email Address/Group Name**

1. Specify the exact attribute value returned by your Identity Provider (IdP) in the **SAML assertion** or **OIDC token** for the authenticated user.
2. This value must exactly match the configured **group name** or **email address** defined in the **Value** field of the **User Groups** or **Attribute Mappings** section within your IdP configuration.
3. During the authentication process, ReleaseOwl (or SAP Business Technology Platform, based on your authentication setup) validates the returned attribute value against the configured mappings to authorize user access.

<figure><img src="../../../.gitbook/assets/image (1652).png" alt=""><figcaption></figcaption></figure>

4. After entering all the required details, click **Save**. Once saved, a **Test** button will appear. Use this button to verify whether the provided credentials and configuration are correct. Click **Test** to validate the connection.

<figure><img src="../../../.gitbook/assets/image (1653).png" alt=""><figcaption></figcaption></figure>

5. Upon successful validation, a **Download** option will be available to download the **tenant-specific metadata** and the **SAP CPI environment descriptor file**.

<figure><img src="../../../.gitbook/assets/image (1825).png" alt=""><figcaption></figcaption></figure>

**Steps to Create Trust Configuration in SAP BTP**

1. Return to **Trust Configuration** in the SAP BTP Cockpit.
2. Click **New Trust Configuration** and select **New** **SAML Trust Configuration**.

<figure><img src="../../../.gitbook/assets/image (1103).png" alt=""><figcaption></figcaption></figure>

3. Upload the **ReleaseOwl CPI Environment metadata XML** file.
4. **Uncheck** the option **"Available for User Logon"** to prevent this IDP from appearing on the SAP login screen.
5. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (1495).png" alt=""><figcaption></figcaption></figure>

#### **Assign Role Collections (Choose One of the Methods Below)**

1. Navigate to **Security → Role Collections**.
2. Click on the **Create** button.
3. Enter a name for the role collection and create it.

<figure><img src="../../../.gitbook/assets/image (1827).png" alt=""><figcaption></figcaption></figure>

4. Search for the newly created role collection name.
5. Click on the role collection name.

<figure><img src="../../../.gitbook/assets/image (1828).png" alt=""><figcaption></figcaption></figure>

6. Click on the **Edit** button.

**Production Environment Role Collection**

7. Add the following roles to ensure proper access and deployment capabilities:

| **Role**                       | **Description**                                                                                                                               |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **WorkspacePackagesRead**      | Read CPI artifacts such as iFlow, Script Collection, Message Mapping, and Value Mapping.                                                      |
| **WorkspacePackagesConfigure** | Configure artifact settings, such as iFlow configuration parameters.                                                                          |
| **WorkspacePackagesEdit**      | Create and update artifacts such as iFlow, Script Collection, and Message Mapping. Also supports initial creation of Value Mapping artifacts. |
| **WorkspaceArtifactsDeploy**   | Deploy artifacts to runtime, including iFlow, Script Collection, Message Mapping, and Value Mapping.                                          |
| **MonitoringDataRead**         | Access message processing logs and monitoring data for iFlow, SOAP, REST, and OData APIs.                                                     |
| **MessagePayloadsRead**        | View message payloads in monitoring.                                                                                                          |

8. Click **Save** after adding the roles.

<figure><img src="../../../.gitbook/assets/image (1829).png" alt=""><figcaption></figcaption></figure>

**Non-Production Environment Role Collection**

Similarly, create a role collection for the non-production environment to enable monitoring, tracing, and deployment activities.

1. Navigate to **Security → Role Collections**.
2. Click on the **Create** button.
3. Enter a name for the non-production role collection.
4. Search for the created role collection and open it.
5. Click on the **Edit** button.

**Assign the following roles:**

Add the following roles to ensure proper access and deployment capabilities:

| **Role**                       | **Description**                                                                                                                               |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **WorkspacePackagesRead**      | Read CPI artifacts such as iFlow, Script Collection, Message Mapping, and Value Mapping.                                                      |
| **WorkspacePackagesConfigure** | Configure artifact settings (for example, iFlow configuration parameters).                                                                    |
| **WorkspacePackagesEdit**      | Create and update artifacts such as iFlow, Script Collection, and Message Mapping. Supports initial creation of Value Mapping artifacts only. |
| **WorkspaceArtifactsDeploy**   | Deploy artifacts to runtime, including iFlow, Script Collection, Message Mapping, and Value Mapping.                                          |
| **MonitoringDataRead**         | Access message processing logs and monitoring data for iFlow, SOAP, REST, and OData APIs.                                                     |
| **MessagePayloadsRead**        | View message payloads in monitoring.                                                                                                          |
| **TraceConfigurationRead**     | View the current tracing configuration.                                                                                                       |
| **TraceConfigurationEdit**     | Modify tracing configuration (enable trace configuration).                                                                                    |

6. Click **Save** to complete the setup.

<figure><img src="../../../.gitbook/assets/image (1744).png" alt=""><figcaption></figcaption></figure>

**Steps to Configure User Groups**

1. Navigate to **Security → Role Collections**.
2. Select the required **Role Collection** (e.g., _Production_ or _Non-Production_).
3. Open the **User Groups** tab.
4. Click on the **“+”** button to add a new user group.

| Field                 | Description                                                 |
| --------------------- | ----------------------------------------------------------- |
| **Identity Provider** | Select the configured Identity Provider (e.g., Custom IDP). |
| **Name**              | Enter an appropriate user group name.                       |

<figure><img src="../../../.gitbook/assets/image (1826).png" alt=""><figcaption></figcaption></figure>

#### **Role Collection Assignment Methods**

You can assign role collections using one of the following methods:

**Method 1: Assign Role Collections using User Groups**

1. Open the newly created **Custom Identity Provider (IDP) for Applications** and click **Edit**.
2. Navigate to the **User Groups** section.
3. Click the **“+”** button to add a new mapping.
4. Configure the mappings as required.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. Go to the **User Groups** section and Click the **"+"** button to add a new mapping.
6. Create a custom role collection with the following roles for assignment in non-production/ production environments:

| Field                | Description                                                                                                   |
| -------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Role Collection**  | Choose the role collection that was created earlier. ( Like production, non-production)                       |
| **User Group Name**  | Enter the exact role collection name that was configured during the earlier role collection creation process. |

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Method 2: Assign Role Collections using Attribute Mapping (Email-Based)**

1. In the same **Trust Configuration** screen, scroll to **Attribute Mappings**.
2. Click the **"+"** button to add a new mapping.
3. Define mappings like this:

| Role Collection                                                               | Attribute | Operator | Value                                 |
| ----------------------------------------------------------------------------- | --------- | -------- | ------------------------------------- |
| <p></p><ul><li>Enter the role collection that was created earlier. </li></ul> | email     | equals   | The email ID of the **service user**  |

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :** If you want to use the **Integration Advisor**, you must assign the following roles to the user:

* **iadv-content-developer**
{% endhint %}

4. The group name or email address configured in the '**Value**' section under **User Groups** or **Attribute Mappings** should match the corresponding group or email configuration in the **IDP Auth Email Address/Group Name** on the **ReleaseOwl CPI Environment** registration page.

<figure><img src="../../../.gitbook/assets/image (1740).png" alt=""><figcaption></figcaption></figure>

### SAP Cloud Identity Provider

ReleaseOwl seamlessly integrates with **SAP Cloud Identity Services** to support secure authentication and identity management across deployment pipelines. To register the SAP Cloud Identity environment, you must first register the Cloud Identity credential. Follow the[ link](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-integration-suite/administration/credential-management) and complete the credential setup.

### **Trust Configuration in SAP BTP**

1. Go to **Trust Configuration** in your SAP BTP subaccount.
2. Click on **Establish Trust**.

<figure><img src="../../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Configure Trust**

1. Select your **Cloud Identity Service tenant** → click **Next**.

<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Select your **Cloud Identity Service domain** → click **Next**.

<figure><img src="../../../.gitbook/assets/image (13) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Under **Configuration Parameters**:
   * Set **Origin Key = sap.custom**
   * Click **Next** and then **Finish**.

<figure><img src="../../../.gitbook/assets/image (14) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (15) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **OpenID Connect Settings**

1. &#x20;A new trust configuration will be created using the origin key `sap.custom` with the OpenID Connect (OIDC) protocol.

<figure><img src="../../../.gitbook/assets/image (16) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. In the **Parameters** section, enable **Available for User Logon.**&#x20;

<figure><img src="../../../.gitbook/assets/image (17) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Navigate to **Attribute Mappings** and fill in the required mappings:

| **Related Role**                                                                                                      | **Attribute Name** | **Value**                         | **Operator** |
| --------------------------------------------------------------------------------------------------------------------- | ------------------ | --------------------------------- | ------------ |
| <ul><li>Trail-content-adminstrator<br></li><li>PI_Integration_Developer</li><li>PI_Administrator</li></ul><p><br></p> | email              | Your Cloud Identity Service email | equals       |

4. Click **Save** to update the configuration.

<figure><img src="../../../.gitbook/assets/image (18) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Access Applications**

1. Log in to your **Cloud Identity Service tenant**.
2. Navigate to **Applications & Resources → Applications**.

<figure><img src="../../../.gitbook/assets/image (20) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. A new bundled application will be automatically created and associated with the trust configuration and linked to the corresponding SAP BTP subaccount.

<figure><img src="../../../.gitbook/assets/image (21) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Configure Single Sign-On**

1. Open the newly created application.
2. Go to **Single Sign-On → Subject Name Identifier**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Configure as follows:

* **Source (Primary):** Identity Directory
* **Attribute (Primary):** Email
* **Source (Fallback):** Identity Directory
* **Attribute (Fallback):** Email

4. Click on the **Save** button.&#x20;

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Configure Conditional Authentication**

1. Go to **Trust** → **Conditional Authentication**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Set **Default Identity Provider = Identity Authentication**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Environment Registration

1. Go to the SAP CPI Environment and click on the **Register SAP CPI Environment**.&#x20;

<figure><img src="../../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. **Web Authentication:** Select **SAP Cloud Identity Provider**.
3. **Credential:** Choose the **SAP Cloud Identity Credential** that you registered earlier.
4. Click on the **Create** button.

<figure><img src="../../../.gitbook/assets/image (1650).png" alt=""><figcaption></figcaption></figure>

### SAP Passport

ReleaseOwl seamlessly integrates with **SAP Passport** to enable secure certificate-based authentication for SAP CPI environments. To register the SAP Passport–based authentication, you must first generate your SAP Passport and register it as a credential in ReleaseOwl. Follow the [link](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-integration-suite/administration/credential-management) and complete the credential setup.

### Environment Registration

1. Go to the SAP CPI Environment and click on the **Register SAP CPI Environment**.&#x20;
2. Click on **Register SAP CPI Environment**.

<figure><img src="../../../.gitbook/assets/image (1644).png" alt=""><figcaption></figcaption></figure>

3. Under **Web Authentication**, select **SAP Passport**.
4. Under **Credential**, select the **SAP Passport Credential** you created earlier.
5. Click on the **Create** button to complete the configuration.

<figure><img src="../../../.gitbook/assets/image (1651).png" alt=""><figcaption></figcaption></figure>

### Adding Environments to Project

* To add environments to project, follow the [link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-admin-guide/general-administration/project-management)and complete the setup.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
**Note :** On clicking Permissions in the above screen, one can know the actions that the user role can perform each for the available features such as **Transport Management**, Change Management, Pipelines, Release Management.
{% endhint %}

