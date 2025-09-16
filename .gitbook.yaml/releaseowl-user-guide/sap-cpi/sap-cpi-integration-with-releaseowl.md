# SAP CPI Integration with ReleaseOwl

ReleaseOwl seamlessly integrates with **SAP Cloud Integration (CPI)** to enable continuous integration and delivery of integration artifacts. Through secure credential management and environment registration, ReleaseOwl connects directly with the CPI tenant to manage, deploy, and monitor artifacts across development, quality, and production landscapes.

## Step 1: Create Process Integration Runtime (PIR) Instances in SAP BTP

A **Process Integration Runtime (PIR)** instance is required in SAP BTP for ReleaseOwl to securely manage and deploy CPI artifacts across environments.

### A. Create a PIR Instance with Plan: `api`

This instance enables **programmatic access via API** for integration tasks.

#### **Steps:**

1. Log in to your SAP BTP Cockpit.
2. Navigate to your **Global Account > Subaccount**.
3. Go to **Instances and Subscriptions** from the left menu.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FUT7hY8QW2SESG2LRE3ER%252Fimage.png%3Falt%3Dmedia%26token%3Da9ab0b09-9b18-4e83-853a-7e64f8c008d6&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=95d6209e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Click on **Create**.
5. In the "**New Instance or Subscription**" wizard:

* **Service**: SAP Process Integration Runtime
* **Plan**: `api`
* **Runtime Environment**: Cloud Foundry
* **Space**: Select your development space (e.g., `dev`)
* **Instance Name**: Choose a name like `CPI_API_Instance`

6. Click **Next**, then **Create**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FIM8ZwGl8fOcA5jUeFYgC%252Fimage.png%3Falt%3Dmedia%26token%3D07cf3701-6387-4f01-b336-f88b10bdfb99&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=47edfe6a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The `api` plan provides programmatic access to the SAP Process Integration Runtime, allowing you to connect via APIs for integration tasks.
{% endhint %}

### Assign Required Roles

In the **Parameters** step, assign the following roles to allow artifact management:

| **Role**                     | **Description**                                   |
| ---------------------------- | ------------------------------------------------- |
| `MessagePayloadsRead`        | Read message payloads in the integration runtime. |
| `MonitoringDataRead`         | View monitoring data for integration flows.       |
| `TraceConfigurationEdit`     | Edit tracing configurations.                      |
| `TraceConfigurationRead`     | View current tracing configuration.               |
| `WorkspaceArtifactsDeploy`   | Deploy artifacts from workspace to runtime.       |
| `WorkspacePackagesConfigure` | Configure packages, parameters, and dependencies. |
| `WorkspacePackagesRead`      | Read-only access to integration packages.         |
| `WorkspacePackagesEdit`      | Modify and configure integration packages.        |

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FQeZkcua5pYBQBiksaMC7%252Fimage.png%3Falt%3Dmedia%26token%3D476837b5-932e-4bed-bf70-61c9bbdf6797&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a4526b6f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Create Service Key (for `api` plan)

After instance creation:

1. Go to **Instances and Subscriptions**.
2. Expand your newly created `api` instance.
3. Click **Create Service Key**.
4. Enter a name (e.g., `cpi-api-key`) and leave parameters blank.
5. Click **Create**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FQtdh3ftS2qBadEGGv2VP%252Fimage.png%3Falt%3Dmedia%26token%3Dee6c05f2-0af7-4a7f-bc69-28e6941c6a20&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=30ea3cb7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

6. Click **View Credentials** to retrieve:

* **Client ID**
* **Client Secret**
* **Token URL**

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252F1XSUCq1nxBsbL8WaXGIo%252Fimage.png%3Falt%3Dmedia%26token%3Dd2feabe3-64ba-4ef6-8274-c68fe9b874b7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2b1c4184&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### &#x20;B. Create a PIR Instance with Plan: `IFLOW`

This is used for managing and deploying **integration artifacts (iFlows)**.

#### **✅ Steps:**

1. Go to your **SAP BTP Cockpit**.
2. Select your **subaccount** that hosts SAP CPI.
3. Go to **Services > Service Marketplace**.
4. Select **SAP Process Integration Runtime** → Click **Create**.
5. Fill in the following:
   * **Service**: SAP Process Integration Runtime
   * **Plan**: `IFLOW`
   * **Runtime Environment**: Cloud Foundry
   * **Space**: Provide the appropriate space (e.g., `dev`)
   * **Instance Name**: (e.g., `CPI_IFLOW_Instance`)

<figure><img src="../../.gitbook/assets/image (1041).png" alt=""><figcaption></figcaption></figure>

6. Click **Next** and then **Create**.

<figure><img src="../../.gitbook/assets/image (1042).png" alt=""><figcaption></figcaption></figure>

### Create Service Key (for `IFLOW` plan)

1. Navigate to **Instances and Subscriptions**.
2. Locate the `IFLOW` instance.
3. Click **Actions > Create Service Key**.
4. Enter a name for the key (e.g., `cpi-iflow-key`) → Click **Create**.

<figure><img src="../../.gitbook/assets/image (1043).png" alt=""><figcaption></figcaption></figure>

5. Click on the service key name to view the key details.
6. You will need these values when setting up ReleaseOwl credentials.

<figure><img src="../../.gitbook/assets/image (1044).png" alt=""><figcaption></figcaption></figure>

### Step 2: Register Credentials in ReleaseOwl

Credential registration enables secure communication between **ReleaseOwl** and **SAP CPI** environments.

#### A. Register SAP CPI Credential (API Access)

**✅ Steps:**

1. Log in to the **ReleaseOwl Platform**.
2. Go to **Administration > Credential Manager**.

<figure><img src="../../.gitbook/assets/image (1404).png" alt=""><figcaption></figcaption></figure>

3. Click **Register Credential**.
4. Fill in the details:
   * **Credential Name:** Any identifiable name for the credential.
   * **Authentication Type:** Select OAuth2
   * **Client ID:** Provide the details from the above created API service key.
   * **Client Secret:** Provide the details from the above created API service key.
   * **Token URL:** Provide the details from the above created API service key.
5. Click **Save**.

The credential will now appear in your list and can be used in pipelines and deployments.

<figure><img src="../../.gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>

#### B. Register SAP CPI Credential (IFLOW Access)

This step allows ReleaseOwl to securely interact with CPI for **artifact deployment and management** via the IFLOW plan.

**✅ Steps:**

1. Navigate to **Credential Manager** from the **Administration** menu in the ReleaseOwl Platform.
2. Click **Register Credential**.
3. Set the **Credential Type** to **SAP Cloud Environment**.
4. Fill in the following details:
   * **Credential Name**: Enter a meaningful name (e.g., `CPI IFLOW Credential`)
   * **Authentication Type**: Select **OAuth2**
   * **Client ID:** Provide the details from the above created IFLOW service key.
   * **Client Secret:** Provide the details from the above created IFLOW service key.
   * **Token URL:** Provide the details from the above created IFLOW service key.
5. Click **Save**.
6. The new credential will now appear in the **List of Credentials** and can be used in Release Pipelines for IFLOW deployments.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### CPI Environment Registration <a href="#pdf-page-della43ge2ynalx23r7p-cpi-environment-registration" id="pdf-page-della43ge2ynalx23r7p-cpi-environment-registration"></a>

1. Navigate to Environments from the Administration menu.
2. Select CPI environment and click on register CPI environment.
3. Provide the following details:

| **Field**                               | **Description**                                                                                                                                                                                                                                                                          |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                                | Enter a unique name for the SAP CPI Environment.                                                                                                                                                                                                                                         |
| **Auth Type**                           | Select the authentication type: **Basic Auth** or **OAuth2**.                                                                                                                                                                                                                            |
| **API URL**                             | Provide the API URL for connecting to the SAP CPI Environment.                                                                                                                                                                                                                           |
| **Enable Test Automation** _(Optional)_ | Toggle to enable or disable test automation capabilities.                                                                                                                                                                                                                                |
| **IFLOW OAuth Credential**              | Select the OAuth credentials used for IFLOW authentication.                                                                                                                                                                                                                              |
| **IFLOW URL**                           | Enter the IFLOW URL from the service key.                                                                                                                                                                                                                                                |
| **Use Custom IdP**                      | Enable this option to set up a custom Identity Provider (IdP). _**Note**_**: The setup process is outlined in the section below.**                                                                                                                                                       |
| **SSO URL**                             | Provide the Single Sign-On (SSO) URL for authentication. _**Note**_**: The setup process is outlined in the section below.**                                                                                                                                                             |
| **IDP Auth Email Address / Group Name** | The group name or email address configured in the '**Value**' section under **User Groups** or **Attribute Mappings** should also match the corresponding group or email configuration in the IDP Auth Email Address/Group Name within the ReleaseOwl CPI environment registration page. |
| **Integration Advisor**                 | Enable Integration Advisor to provide the Host URL.                                                                                                                                                                                                                                      |
| **Host URL**                            | The host URL is the base address of your SAP Integration Suite instance. _(Example: https://\<subdomain>.integrationsuite-\<region>.cfapps.\<domain>.hana.ondemand.com)_                                                                                                                 |
| **Enable Git** _(Optional)_             | Enable this option to integrate Git with the environment.                                                                                                                                                                                                                                |
| **Git Credential**                      | Select the credential for accessing the Git repository.                                                                                                                                                                                                                                  |
| **Repository URL**                      | Provide the Git repository URL.                                                                                                                                                                                                                                                          |
| **Branch**                              | Specify the branch to be used for the integration.                                                                                                                                                                                                                                       |
| **Environment Type**                    | Select the environment type (e.g., **Dev**, **QA**, **Prod**).                                                                                                                                                                                                                           |

<figure><img src="../../.gitbook/assets/image (1499).png" alt=""><figcaption></figcaption></figure>

### Custom Identity Provider (IDP) Setup and Configuration <a href="#pdf-page-della43ge2ynalx23r7p-toc190778976" id="pdf-page-della43ge2ynalx23r7p-toc190778976"></a>

A Custom IDP (Identity Provider) must be configured to allow secure authentication and authorization for users who interact with the Integration Suite (CPI) instance through ReleaseOwl.

**Use Case:** This is particularly useful for executing test cases, simulation testing and updating value mappings as part of the pipeline.

#### Steps to Configure a Custom Identity Provider (IDP)

A **Custom Identity Provider (IDP)** is required for deploying certain artifact types—such as **Value Mapping**, **REST**, **SOAP**, and **OData APIs**—as well as for executing test cases associated with these artifacts via ReleaseOwl.

1. **Download SAP BTP SAML Metadata**

* Navigate to the **Security** section of your SAP BTP Subaccount.
* Go to **Trust Configuration**.
* Click **Download SAML Metadata** to download the BTP metadata file.

<figure><img src="../../.gitbook/assets/image (1100).png" alt=""><figcaption></figcaption></figure>

2. **Extract the SAP BTP SSO URL**

* Open the downloaded SAML metadata XML file in a text editor (e.g., Notepad++, VS Code, or a browser).
* Search for the `<AssertionConsumerService>` tag.
* In this tag, locate the **Location** attribute. The value of this attribute is your **SAP BTP SSO URL**.

<figure><img src="../../.gitbook/assets/image (1099).png" alt=""><figcaption></figcaption></figure>

* Copy the extracted **SSO URL**.
* Paste it into the **SSO URL** field in the **SAP CPI Environment**.

<figure><img src="../../.gitbook/assets/image (1500).png" alt=""><figcaption></figcaption></figure>

* After clicking the **Save** button, a **Test** button will appear. This button is used to verify whether the entered credentials are correct. Click on the **Test** button to validate the connection.\


<figure><img src="../../.gitbook/assets/image (1101).png" alt=""><figcaption></figcaption></figure>

* Upon successful validation, a **Download** option will be available to download the **tenant-specific metadata** and the **SAP CPI environment descriptor file**.

<figure><img src="../../.gitbook/assets/image (1494).png" alt=""><figcaption></figcaption></figure>

3. **Create Trust Configuration in SAP BTP**

* Return to **Trust Configuration** in the SAP BTP Cockpit.
* Click **New Trust Configuration** and select **New** **SAML Trust Configuration**.

<figure><img src="../../.gitbook/assets/image (1103).png" alt=""><figcaption></figcaption></figure>

* Upload the **ReleaseOwl CPI Environment metadata XML** file.
* **Uncheck** the option **"Available for User Logon"** to prevent this IDP from appearing on the SAP login screen.
* Click **Save**.

<figure><img src="../../.gitbook/assets/image (1495).png" alt=""><figcaption></figcaption></figure>

4. **Assign Role Collections (Choose One of the Methods Below)**

To assign role collections, you can choose **one** of the following methods:

**Method 1: Assign Role Collections using User Groups**

* Open the newly created **Custom IDP** and click **Edit**.
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

| **Custom Role Collection**                       | **Required Roles**                                                                                                                                                  |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Roles required for deployment automation         | <p></p><ul><li>WorkspaceArtifactsDeploy</li><li>WorkspacePackagesConfigure</li><li>WorkspacePackagesRead</li><li>WorkspacePackagesEdit</li></ul>                    |
| Roles required for ReleaseOwl CPI test generator | <p></p><ul><li>MessagePayloadsRead </li></ul><ul><li> MonitoringDataRead </li></ul><ul><li>TraceConfigurationEdit</li></ul><ul><li>TraceConfigurationRead</li></ul> |

<figure><img src="../../.gitbook/assets/image (1493).png" alt=""><figcaption></figcaption></figure>



6. The group name or email address configured in the '**Value**' section under **User Groups** or **Attribute Mappings** should match the corresponding group or email configuration in the **IDP Auth Email Address/Group Name** on the ReleaseOwl CPI environment registration page.

<figure><img src="../../.gitbook/assets/image (1108).png" alt=""><figcaption></figcaption></figure>

### Create a Project

1. Go to the projects in the adminstation view.
2. Click on the "**Create New Project**"

<figure><img src="../../.gitbook/assets/image (1047).png" alt=""><figcaption></figcaption></figure>

3. Fill in the necessary details, select the project type as '**SAP CPI'**, and click the Save button

<figure><img src="../../.gitbook/assets/image (1048).png" alt=""><figcaption></figcaption></figure>

### **Adding Environments to the Project** <a href="#pdf-page-della43ge2ynalx23r7p-adding-integration-suite-environments-to-the-project" id="pdf-page-della43ge2ynalx23r7p-adding-integration-suite-environments-to-the-project"></a>

For artifacts to load in SAP CPI Management page, the Integration Suite environments must be registered in Project Settings in ReleaseOwl.

**To register SAP Integration Suite environment:**

1\. Go to **Projects** drop down at the top right corner and click **Project Settings**.

<figure><img src="../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

2\. In Project Settings, go to **Environment**.

3\. The following screen is displayed.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4\. Click  +**Add button** to add a new environment in ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5\. In the subsequent screen, choose the required environment from the list displayed by selecting Source. Only the artifacts with source are synced to ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

6\. The environment is added to the corresponding project in ReleaseOwl.

7\. Click **Permissions** (under **Users** tab in Project Settings), to add users that can access (read or deploy to) the registered CPI environment.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

8. Click **Permissions**. The roles that are assigned to the selected user are seen.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :** On clicking Permissions in the above screen, one can know the actions that the user role can perform each for the available features such as Transport Management, Change Management, Pipelines, Release Management.
{% endhint %}

## Managing CPI Packages <a href="#pdf-page-della43ge2ynalx23r7p-managing-cpi-packages" id="pdf-page-della43ge2ynalx23r7p-managing-cpi-packages"></a>

**1. Access SAP CPI Management:**

* Switch to the Project view.
* Click on SAP CPI Management in the Build section.

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

**2. Add and Sync Packages:**

* Click the **Add Packages** button in the CPI Packages section.
* **Select Package:** Use the search bar to find a package, then check the box next to the desired package(s).
* **Sync Package:** Click Sync to add and synchronize the selected package(s).

<figure><img src="../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

* A pop-up screen will display the sync history. Use the Refresh button to update the sync status and view the latest details. Click Close when done.

<figure><img src="../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

**3. Configure Artifacts:**

* Click the arrow next to the package name.

<figure><img src="../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

* In the "**Artifacts**" list, click the three dots in the "**Actions**" column for the desired artifact.

<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

* Select "**Configure**" from the list.&#x20;

<figure><img src="../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

**4. Save Changes:**

* Modify the required values in the configuration screen.&#x20;
* **Save:** Update the existing artifact directly.
* **Save as Artifact**: Create a new version of the artifact with the modified values.

<figure><img src="../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

* After selecting "**Save as Artifact**", a new artifact is created with the updated values.
* To view more details about the new artifact, click the three dots (Actions) next to it.

<figure><img src="../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

* Click on **Edit Configuration** to open the artifact configuration.

<figure><img src="../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

* Verify or modify the updated values by clicking on the **pencil icon** (Modify Values button), then click the **Save** button to apply the changes.

<figure><img src="../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

* Editing **timer configuration parameters** (such as start time, recurrence, etc.) is **not supported** directly from ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (1021).png" alt=""><figcaption></figcaption></figure>

* A newly created artifact will be displayed with its specified name and the associated configuration settings.

<figure><img src="../../.gitbook/assets/image (53) (1).png" alt=""><figcaption></figcaption></figure>

### Creating a Release Pipeline <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

#### **1. Create a New Release Pipeline:**

* Switch to the **Project view** and select the **Release section**.
* Navigate to Release Pipelines and click on **Create New Release Pipeline**.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Provide a Pipeline Name.
* Add stages (e.g., QA, Prod) and assign tasks to each stage.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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

      <figure><img src="../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>
* **Notify Users:**  Sends a notification to selected users **when the  task is created** or **when pipeline execution reaches this stage**
* **Notify Promotion User:** Sends a notification to the **user who promoted** the artifact or initiated the deployment to this stage.
* **Notify  to Button :**  It has three options — **User**, **Role**, and **Custom** — to specify the recipients of the notification based on individual users, assigned roles, or custom groups.

| Option     | Definition                                                                                                                                                                       |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User**   | Sends the notification directly to a specific individual user.                                                                                                                   |
| **Role**   | Sends the notification to all users who belong to a specific predefined role (such as Developer, Tester, Release Manager). Every user in the role will receive the notification. |
| **Custom** | Sends the notification based on a custom mapping between components and roles. Different components can notify different roles, depending on your configuration.                 |

<figure><img src="../../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

3. &#x20;**Save and Configure Notifications:**

* Add notification emails if needed.
* Save the pipeline configuration.

<figure><img src="../../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

**Managing Sprints and User Stories**

**1. Create a Sprint:**

* In the Project View, navigate to Change Management and click Create Sprint.

<figure><img src="../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

* Enter the sprint name and click Save.

<figure><img src="../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

* Click the three dots (Actions) button and select Start Sprint.

<figure><img src="../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

**2. Create a User Story:**

* Go to User Stories and click **Create New User Story**.

<figure><img src="../../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

* Summary: Provide a summary of the user story.
* Type: Select the type of story.
* Click Save.

<figure><img src="../../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

3. **Edit and Promote User Story:**

* After creating the user story, click the three dots (Actions) and select Edit.

<figure><img src="../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

* Select the release pipeline and associated component.

<figure><img src="../../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>

* Add the artifact in CPI Artifacts and click Save.

<figure><img src="../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

#### Import Settings

The **CPI Import Settings** dialog, accessible from the **User Story Edit View** under the **CPI Artifacts** section, enables users to configure deployment settings for each target CPI environment. It allows selective activation of the **Force Deploy** option, which permits redeployment of artifact versions when necessary.

* Click the **“...”** next to a CPI artifact and select **“CPI Import Settings.”**

<figure><img src="../../.gitbook/assets/image (1333).png" alt=""><figcaption></figcaption></figure>

* In the popup, you’ll see a list of available **target environments**.
* Check the **Force Deploy** box if you want to allow redeployment of CPI artifacts.
* Click **Save**.

<figure><img src="../../.gitbook/assets/image (1332).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :**  These settings empower deployment teams to handle complex CPI deployment scenarios such as partial rollouts, forced redeployments, or selective tenant targeting—without compromising consistency or governance policies.
{% endhint %}

**Promotion of User Story**

* To promote the user story, click the three dots (Actions) and select Promote.

<figure><img src="../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>

* You can view the **Deploy Logs** under the **SAP CPI Deploy Logs** window after promoting the user story.

<figure><img src="../../.gitbook/assets/image (1022).png" alt=""><figcaption></figcaption></figure>

* **Upload Status**: Indicates whether the artifact was successfully uploaded.
* **Config Status**: Confirms if the configuration for new or updated artifacts was successful.
* **Deploy Status:** Reflects the final deployment status of the artifact.
* **Already Deployed:**  Indicates that the artifact was **previously deployed**, either during a **retry** operation or through **manual completion**. This status helps avoid duplicate deployments and provides clarity during re-runs.

<figure><img src="../../.gitbook/assets/image (1069).png" alt=""><figcaption></figcaption></figure>

* **Manual Completion:** If a deployment, configuration, or upload fails or times out, users can use the **Manual Completion** option to resolve the issue manually and continue the pipeline execution.

<figure><img src="../../.gitbook/assets/image (1049).png" alt=""><figcaption></figcaption></figure>

* **Refresh Button**\
  Fetches the CPI runtime artifact deployment status and updates the runtime status in the deployment log.

<figure><img src="../../.gitbook/assets/image (1023).png" alt=""><figcaption></figcaption></figure>

* **Retry Button**\
  Allows you to reattempt a failed deployment or pipeline stage.

<figure><img src="../../.gitbook/assets/image (1050).png" alt=""><figcaption></figcaption></figure>

* **Status Button**\
  If the status is shown as **"Suspended"**, it usually indicates that the pipeline or task has been paused or is awaiting a manual action.

<figure><img src="../../.gitbook/assets/image (1051).png" alt=""><figcaption></figcaption></figure>
