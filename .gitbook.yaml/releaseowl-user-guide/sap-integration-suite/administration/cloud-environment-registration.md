# Integration Environment Registration

To register the SAP Integration Environment, you must first register the CPI credential. Follow the[ link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-integration-suite/administration/credential-management)and complete the credential setup.

### CPI Environment Registration <a href="#pdf-page-della43ge2ynalx23r7p-cpi-environment-registration" id="pdf-page-della43ge2ynalx23r7p-cpi-environment-registration"></a>

1. Navigate to Environments from the Administration menu.
2. Select CPI environment and click on register CPI environment.
3. Provide the following details:

| **Field**                               | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                                | Enter a unique name for the SAP CPI Environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Auth Type**                           | Select the authentication type: **Basic Auth** or **OAuth2**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **API URL**                             | Provide the API URL for connecting to the SAP CPI Environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Enable Test Automation** _(Optional)_ | Toggle to enable or disable test automation capabilities.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **IFLOW OAuth Credential**              | Select the OAuth credentials used for IFLOW authentication.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **IFLOW URL**                           | Enter the IFLOW URL from the service key.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **SSO URL**                             | Provide the Single Sign-On (SSO) URL for authentication. _**Note**_**: The setup process is outlined in the section below.**                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **IDP Auth Email Address / Group Name** | The group name or email address configured in the '**Value**' section under **User Groups** or **Attribute Mappings** should also match the corresponding group or email configuration in the IDP Auth Email Address/Group Name within the ReleaseOwl CPI environment registration page.                                                                                                                                                                                                                                                                                            |
| **Integration Advisor**                 | Enable Integration Advisor to provide the Host URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Host URL**                            | The host URL is the base address of your SAP Integration Suite instance. _(Example: https://\<subdomain>.integrationsuite-\<region>.cfapps.\<domain>.hana.ondemand.com)_                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Enable Git** _(Optional)_             | Enable this option to integrate Git with the environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Git Credential**                      | Select the credential for accessing the Git repository.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Repository URL**                      | Provide the Git repository URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Branch**                              | Specify the branch to be used for the integration.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Environment Type**                    | Select the environment type (e.g., **Dev**, **QA**, **Prod**).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Web Authentication**                  | <p>There are <strong>three authentication types</strong> available for CPI Web Authentication in ReleaseOwl:</p><ol><li><strong>None</strong> – No authentication is required.</li><li><strong>Custom Identity Provider (Custom IdP)</strong> – Authentication is performed using a customer-configured Identity Provider.</li><li><strong>SAP Cloud Identity Provider</strong> – Authentication is performed using SAP Cloud Identity Services (IAS).</li><li><strong>SAP Passport</strong> – Authentication is performed using browser-based SAP Passport certificates.</li></ol> |

<figure><img src="../../../.gitbook/assets/image (1649).png" alt=""><figcaption></figcaption></figure>

### Custom Identity Provider (IDP) Setup and Configuration <a href="#pdf-page-della43ge2ynalx23r7p-toc190778976" id="pdf-page-della43ge2ynalx23r7p-toc190778976"></a>

A Custom IDP (Identity Provider) must be configured to allow secure authentication and authorization for users who interact with the Integration Suite (CPI) instance through ReleaseOwl.

**Use Case:** This is particularly useful for executing test cases, simulation testing and updating value mappings as part of the pipeline.

#### Steps to Configure a Custom Identity Provider (IDP)

A **Custom Identity Provider (IDP)** is required for deploying certain artifact types—such as **Value Mapping**, **REST**, **SOAP**, and **OData APIs**—as well as for executing test cases associated with these artifacts via ReleaseOwl.

1. **Download SAP BTP SAML Metadata**

* Navigate to the **Security** section of your SAP BTP Subaccount.
* Go to **Trust Configuration**.
* Click **Download SAML Metadata** to download the BTP metadata file.

<figure><img src="../../../.gitbook/assets/image (1100).png" alt=""><figcaption></figcaption></figure>

2. **Extract the SAP BTP SSO URL**

* Open the downloaded SAML metadata XML file in a text editor (e.g., Notepad++, VS Code, or a browser).
* Search for the `<AssertionConsumerService>` tag.
* In this tag, locate the **Location** attribute. The value of this attribute is your **SAP BTP SSO URL**.

<figure><img src="../../../.gitbook/assets/image (1099).png" alt=""><figcaption></figcaption></figure>

* Copy the extracted **SSO URL**.
* Paste it into the **SSO URL** field in the **SAP CPI Environment**.

<figure><img src="../../../.gitbook/assets/image (1500).png" alt=""><figcaption></figcaption></figure>

* For the **IDP Auth Email Address/Group Name** field, enter the **exact value that your Identity Provider sends in the SAML/OIDC assertion** for the user.
* This value must match the **group name or email address defined in the&#x20;**_**Value**_**&#x20;field** of the **User Groups** or **Attribute Mappings** configuration in your IDP.\
  ReleaseOwl (or SAP BTP) uses this returned attribute value to validate user authorization.
* Refer to the _Assign Role Collections_ section to ensure that the mapped group/attribute is correctly linked to the required role collections.

<figure><img src="../../../.gitbook/assets/image (1652).png" alt=""><figcaption></figcaption></figure>

* After entering all the required details, click **Save**. Once saved, a **Test** button will appear. Use this button to verify whether the provided credentials and configuration are correct. Click **Test** to validate the connection.

<figure><img src="../../../.gitbook/assets/image (1653).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1654).png" alt=""><figcaption></figcaption></figure>

* Upon successful validation, a **Download** option will be available to download the **tenant-specific metadata** and the **SAP CPI environment descriptor file**.

<figure><img src="../../../.gitbook/assets/image (1494).png" alt=""><figcaption></figcaption></figure>

3. **Create Trust Configuration in SAP BTP**

* Return to **Trust Configuration** in the SAP BTP Cockpit.
* Click **New Trust Configuration** and select **New** **SAML Trust Configuration**.

<figure><img src="../../../.gitbook/assets/image (1103).png" alt=""><figcaption></figcaption></figure>

* Upload the **ReleaseOwl CPI Environment metadata XML** file.
* **Uncheck** the option **"Available for User Logon"** to prevent this IDP from appearing on the SAP login screen.
* Click **Save**.

<figure><img src="../../../.gitbook/assets/image (1495).png" alt=""><figcaption></figcaption></figure>

4. **Assign Role Collections (Choose One of the Methods Below)**

To assign role collections, you can choose **one** of the following methods:

**Method 1: Assign Role Collections using User Groups**

* Open the newly created **Custom IDP for Applocations** and click **Edit**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Go to the **User Groups** section and Click the **"+"** button to add a new mapping.
* Configure the mappings like the example below:

| Role Collection            | Attribute | Operator | Value      |
| -------------------------- | --------- | -------- | ---------- |
| PI\_Integration\_Developer | Groups    | equals   | group name |

**Method 2: Assign Role Collections using Attribute Mapping (Email-Based)**

* In the same **Trust Configuration** screen, scroll to **Attribute Mappings**.
* Click the **"+"** button to add a new mapping.
* Define mappings like this:

| Role Collection            | Attribute    | Operator | Value                                 |
| -------------------------- | ------------ | -------- | ------------------------------------- |
| PI\_Integration\_Developer | emailAddress | equals   | The email ID of the **service user**  |

**Method 3: Configure Custom Role Collection Mappings for the IdP**

You can configure granular permissions by creating the custom role collection with the below required roles:

| **Custom Role Collection**                       | **Required Roles**                                                                                            |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| Roles required for ReleaseOwl CPI test generator | <p></p><ul><li>Trail-content-adminstrator</li><li>PI_Integration_Developer</li><li>PI_Administrator</li></ul> |

<figure><img src="../../../.gitbook/assets/image (1607).png" alt=""><figcaption></figcaption></figure>

6. The group name or email address configured in the '**Value**' section under **User Groups** or **Attribute Mappings** should match the corresponding group or email configuration in the **IDP Auth Email Address/Group Name** on the ReleaseOwl CPI environment registration page.

<figure><img src="../../../.gitbook/assets/image (1108).png" alt=""><figcaption></figcaption></figure>

### SAP Cloud Identity Provider

ReleaseOwl seamlessly integrates with **SAP Cloud Identity Services** to support secure authentication and identity management across deployment pipelines. To register the SAP Cloud Identity environment, you must first register the Cloud Identity credential. Follow the[ link](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-integration-suite/administration/credential-management) and complete the credential setup.

### **Trust Configuration in SAP BTP**

1. Go to **Trust Configuration** in your SAP BTP subaccount.
2. Click on **Establish Trust**.

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

#### **Configure Trust**

1. Select your **Cloud Identity Service tenant** → click **Next**.

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

2. Select your **Cloud Identity Service domain** → click **Next**.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

3. Under **Configuration Parameters**:
   * Set **Origin Key = sap.custom**
   * Click **Next** and then **Finish**.

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

#### **OpenID Connect Settings**

1. &#x20;A new trust configuration will be created using the origin key `sap.custom` with the OpenID Connect (OIDC) protocol.

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

2. In the **Parameters** section, enable **Available for User Logon.**&#x20;

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

3. Navigate to **Attribute Mappings** and fill in the required mappings:

| **Related Role**                                                                                                      | **Attribute Name** | **Value**                         | **Operator** |
| --------------------------------------------------------------------------------------------------------------------- | ------------------ | --------------------------------- | ------------ |
| <ul><li>Trail-content-adminstrator<br></li><li>PI_Integration_Developer</li><li>PI_Administrator</li></ul><p><br></p> | email              | Your Cloud Identity Service email | equals       |

4. Click **Save** to update the configuration.

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

### **Access Applications**

1. Log in to your **Cloud Identity Service tenant**.
2. Navigate to **Applications & Resources → Applications**.

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

3. A new bundled application will be automatically created and associated with the trust configuration and linked to the corresponding SAP BTP subaccount.

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

#### **Configure Single Sign-On**

1. Open the newly created application.
2. Go to **Single Sign-On → Subject Name Identifier**.

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

3. Configure as follows:

* **Source (Primary):** Identity Directory
* **Attribute (Primary):** Email
* **Source (Fallback):** Identity Directory
* **Attribute (Fallback):** Email

4. Click on the **Save** button.&#x20;

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### **Configure Conditional Authentication**

1. Go to **Trust** → **Conditional Authentication**.

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

2. Set **Default Identity Provider = Identity Authentication**.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

#### Environment Registration

1. Go to the SAP CPI Environment and click on the **Register SAP CPI Environment**.&#x20;

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

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

### Create a Project

* To create a new project, follow the [link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-admin-guide/general-administration/project-management)and complete the setup.

<figure><img src="../../../.gitbook/assets/image (1637).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :** On clicking Permissions in the above screen, one can know the actions that the user role can perform each for the available features such as Transport Management, Change Management, Pipelines, Release Management.
{% endhint %}

## Managing CPI Packages <a href="#pdf-page-della43ge2ynalx23r7p-managing-cpi-packages" id="pdf-page-della43ge2ynalx23r7p-managing-cpi-packages"></a>

**1. Access SAP CPI Management:**

* Switch to the Project view.
* Click on SAP CPI Management in the Build section.

<figure><img src="../../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

**2. Add and Sync Packages:**

* Click the **Add Packages** button in the CPI Packages section.
* **Select Package:** Use the search bar to find a package, then check the box next to the desired package(s).
* **Sync Package:** Click Sync to add and synchronize the selected package(s).

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

* A pop-up screen will display the sync history. Use the Refresh button to update the sync status and view the latest details. Click Close when done.

<figure><img src="../../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

**3. Configure Artifacts:**

* Click the arrow next to the package name.

<figure><img src="../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

* In the "**Artifacts**" list, click the three dots in the "**Actions**" column for the desired artifact.

<figure><img src="../../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

* Select "**Configure**" from the list.&#x20;

<figure><img src="../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

**4. Save Changes:**

* Modify the required values in the configuration screen.&#x20;
* **Save:** Update the existing artifact directly.
* **Save as Artifact**: Create a new version of the artifact with the modified values.

<figure><img src="../../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

* After selecting "**Save as Artifact**", a new artifact is created with the updated values.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* To view more details about the new artifact, click the three dots (Actions) next to it.
* Click on **Edit Configuration** to open the artifact configuration.

<figure><img src="../../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

* Verify or modify the updated values by clicking on the **pencil icon** (Modify Values button), then click the **Save** button to apply the changes.

<figure><img src="../../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

* Editing **timer configuration parameters** (such as start time, recurrence, etc.) is **not supported** directly from ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (1021).png" alt=""><figcaption></figcaption></figure>

* A newly created artifact will be displayed with its specified name and the associated configuration settings.

<figure><img src="../../../.gitbook/assets/image (53) (1).png" alt=""><figcaption></figcaption></figure>

### Creating a Release Pipeline <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

#### **1. Create a New Release Pipeline:**

* Switch to the **Project view** and select the **Release section**.
* Navigate to Release Pipelines and click on **Create New Release Pipeline**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Provide a Pipeline Name.
* Add stages (e.g., QA, Prod) and assign tasks to each stage.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fp9bYnD6MU10rrjza1IzY%252Fimage.png%3Falt%3Dmedia%26token%3D7e30a12a-4061-483e-a9a2-06d82b9f2caf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3549c696&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**2. Add Deployment Tasks:**

* Click the **Add button** in a task stage to include deployment tasks.
* Fill in the required details:
  * **Name:** Enter a preferred name for the deployment task.
  * **Deploy Type:** Select the type of deployment.
  * **Select CPI Environment:** Select the target CPI environment where the deployment will take place.
  *   **Deployment Action:** Choose between:

      * **Upload Only:** Uploads the deployment package without executing the deployment.
      * **Upload and Deploy:** Uploads the deployment package and executes the deployment.

      <figure><img src="../../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>
* **Notify Users:**  Sends a notification to selected users **when the  task is created** or **when pipeline execution reaches this stage**
* **Notify Promotion User:** Sends a notification to the **user who promoted** the artifact or initiated the deployment to this stage.
* **Notify  to Button :**  It has three options — **User**, **Role**, and **Custom** — to specify the recipients of the notification based on individual users, assigned roles, or custom groups.

| Option     | Definition                                                                                                                                                                       |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User**   | Sends the notification directly to a specific individual user.                                                                                                                   |
| **Role**   | Sends the notification to all users who belong to a specific predefined role (such as Developer, Tester, Release Manager). Every user in the role will receive the notification. |
| **Custom** | Sends the notification based on a custom mapping between components and roles. Different components can notify different roles, depending on your configuration.                 |

<figure><img src="../../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

3. &#x20;**Save and Configure Notifications:**

* Add notification emails if needed.
* Save the pipeline configuration.

<figure><img src="../../../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

**Managing Sprints and User Stories**

**1. Create a Sprint:**

* In the Project View, navigate to Change Management and click Create Sprint.

<figure><img src="../../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

* Enter the sprint name and click Save.

<figure><img src="../../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

* Click the three dots (Actions) button and select Start Sprint.

<figure><img src="../../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

**2. Create a User Story:**

* Go to User Stories and click **Create New User Story**.

<figure><img src="../../../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

* Summary: Provide a summary of the user story.
* Type: Select the type of story.
* Click Save.

<figure><img src="../../../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

3. **Edit and Promote User Story:**

* After creating the user story, click the three dots (Actions) and select Edit.

<figure><img src="../../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

* Select the release pipeline and associated component.

<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Add the artifact in CPI Artifacts and click Save.

<figure><img src="../../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

#### Import Settings

The **CPI Import Settings** dialog, accessible from the **User Story Edit View** under the **CPI Artifacts** section, enables users to configure deployment settings for each target CPI environment. It allows selective activation of the **Force Deploy** option, which permits redeployment of artifact versions when necessary.

* Click the **“...”** next to a CPI artifact and select **“CPI Import Settings.”**

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* In the popup, you’ll see a list of available **target environments**.
* Check the **Force Deploy** box if you want to allow redeployment of CPI artifacts.
* Click **Save**.

<figure><img src="../../../.gitbook/assets/image (1332).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :**  These settings empower deployment teams to handle complex CPI deployment scenarios such as partial rollouts, forced redeployments, or selective tenant targeting—without compromising consistency or governance policies.
{% endhint %}

### Adding Links in the Attachments Section

The **Attachments** section allows users to add reference links directly to their items for easy access and documentation.

#### Steps to Add a Link

1. Navigate to the **Attachments** section of the desired item.
2. Click the **Link** button.
3. In the dialog box, enter the following details:
   * **Name** – Provide a meaningful name for the link.
   * **URL** – Enter the complete URL of the reference link.
4. Click **Add** to attach the link.

<figure><img src="../../../.gitbook/assets/image (12) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. The added link will be listed in the **Attachments** section and can be viewed by all relevant users

<figure><img src="../../../.gitbook/assets/image (11) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Promotion of User Story**

* To promote the user story, click the three dots (Actions) and select Promote.

<figure><img src="../../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>

* You can view the **Deploy Logs** under the **SAP CPI Deploy Logs** window after promoting the user story.

<figure><img src="../../../.gitbook/assets/image (1022).png" alt=""><figcaption></figcaption></figure>

* **Upload Status**: Indicates whether the artifact was successfully uploaded.
* **Config Status**: Confirms if the configuration for new or updated artifacts was successful.
* **Deploy Status:** Reflects the final deployment status of the artifact.
* **Already Deployed:**  Indicates that the artifact was **previously deployed**, either during a **retry** operation or through **manual completion**. This status helps avoid duplicate deployments and provides clarity during re-runs.

<figure><img src="../../../.gitbook/assets/image (1069).png" alt=""><figcaption></figcaption></figure>

* **Manual Completion:** If a deployment, configuration, or upload fails or times out, users can use the **Manual Completion** option to resolve the issue manually and continue the pipeline execution.

<figure><img src="../../../.gitbook/assets/image (1049).png" alt=""><figcaption></figcaption></figure>

* **Refresh Button**\
  Fetches the CPI runtime artifact deployment status and updates the runtime status in the deployment log.

<figure><img src="../../../.gitbook/assets/image (1023).png" alt=""><figcaption></figcaption></figure>

* **Retry Button**\
  Allows you to reattempt a failed deployment or pipeline stage.

<figure><img src="../../../.gitbook/assets/image (1050).png" alt=""><figcaption></figcaption></figure>

* **Status Button**\
  If the status is shown as **"Suspended"**, it usually indicates that the pipeline or task has been paused or is awaiting a manual action.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
