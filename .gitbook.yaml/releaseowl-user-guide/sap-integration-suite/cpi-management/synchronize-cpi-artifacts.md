# Synchronize CPI Artifacts

### **Prerequisites**

1. Begin by registering your SAP BTP credentials and the corresponding SAP Integration Suite environment within ReleaseOwl.
2.  Navigate to the **Projects** section and create a new project.

    * **Project Type**: Select **SAP CPI**.

    <figure><img src="../../../.gitbook/assets/image (1052).png" alt=""><figcaption></figcaption></figure>
3. Once the project is created, add the registered environments to the project via **Project Settings > Environment**.

<figure><img src="../../../.gitbook/assets/image (1053).png" alt=""><figcaption></figcaption></figure>

4. Click **Sync All Artifacts** to fetch and display the available CPI artifacts within the selected project.
5. Navigate to **Build > SAP CPI Management** and click on the **actions** button to view **Sync Artifacts**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* The **Modified By** and **Modified Date** information displayed in the ReleaseOwl dashboard is **sourced directly from SAP CPI** for supported artifact types such as **IFLOW**, **ODATAAPIPROVIDER**, **SOAPAPIPROVIDER**, and **RESTAPIPROVIDER**.
* For artifact types like **SCRIPT\_COLLECTION**, **MESSAGE\_MAPPING**, and **VALUE\_MAPPING**, SAP CPI **does not provide these metadata fields via its public APIs**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* In such cases, ReleaseOwl **derives and updates the Modified By and Modified Date based on ReleaseOwl activity and processing timestamps**, reflecting when the artifact was last handled or updated within ReleaseOwl rather than the original CPI metadata.

### **Synchronize Integration Suite Artifacts**

6. Click **Sync  Artifacts** to fetch various artifacts like IFlows, Value Maps, Packages, Configuration parameters, etc. from the registered SAP CPI environment into ReleaseOwl.
7. If there are changes made to the existing artifacts, the changes will also be updated.
8. Click **Sync Artifacts** to sync the CPI artifacts.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Sync History**

With this, you can view the history of all the artifact syncs that have occurred. Click **Sync History**, to view the CPI sync history of this project.

<figure><img src="../../../.gitbook/assets/image (1055).png" alt=""><figcaption></figcaption></figure>

### **Sort**

You can sort the artifacts as per your convenience. To sort them:

1. Click the **Sort icon**.
2.  In the page displayed, choose an option and click **OK**.<br>

    <figure><img src="../../../.gitbook/assets/image (1056).png" alt=""><figcaption></figcaption></figure>

### **Actions**

Multiple actions can be performed on an artifact, based on the type of artifact. These actions include – View Test Cases, Comment , Configure, Deployment History, Versions and Download.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Manage Environment Wide IFlow Configurations**

You can maintain configuration parameters for IFlows for each environment separately in ReleaseOwl. These will be updated accordingly during the deployment.

#### **To configure an artifact:**

1\. Go to the required artifact, click **Actions** and choose **Configure**.

2\. The following screen is displayed that will show various configuration parameters for the Integration Suite environments that are part of the landscape.

3\. No changes can be made to **Dev** environment.

4\. To make changes in any other environment, click the edit icon on the required name and make changes. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (1059).png" alt=""><figcaption></figcaption></figure>

### **Artifact Versions**

1\. To view the versions, go to the required artifact, click **Actions** and choose **Versions**.

<figure><img src="../../../.gitbook/assets/image (1060).png" alt=""><figcaption></figcaption></figure>

2. &#x20;The following screen is displayed showing the user different versions of the artifact.

<figure><img src="../../../.gitbook/assets/image (1061).png" alt=""><figcaption></figcaption></figure>

3. **Assign User Story** option is used to link a specific version of an artifact (such as a configuration or integration flow) to a designated User Story.
4. On clicking **Assign User Story**, the system will prompt you to:

* Select a User Story from a searchable button.&#x20;
* Associate the current version of the artifact with the selected User Story, establishing a traceable link between the artifact version and the development requirement.

<figure><img src="../../../.gitbook/assets/image (1062).png" alt=""><figcaption></figcaption></figure>



5. Click **Actions and** choose either **Download** or **Where Used List** based on the requirement.

<figure><img src="../../../.gitbook/assets/image (1063).png" alt=""><figcaption></figcaption></figure>

## Creating a Release Pipeline <a href="#pdf-page-della43ge2ynalx23r7p-managing-cpi-packages" id="pdf-page-della43ge2ynalx23r7p-managing-cpi-packages"></a>

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

#### **1. Create a New Release Pipeline:**

* Switch to the **Project view** and select the **Release section**.
* Navigate to Release Pipelines and click on **Create New Release Pipeline**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Provide a Pipeline Name.
* Add stages (e.g., QA, Prod) and assign tasks to each stage.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Add the artifact in CPI Artifacts and click Save.

<figure><img src="../../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

#### Import Settings

The **CPI Import Settings** dialog, accessible from the **User Story Edit View** under the **CPI Artifacts** section, enables users to configure deployment settings for each target CPI environment. It allows selective activation of the **Force Deploy** option, which permits redeployment of artifact versions when necessary.

* Click the **“...”** next to a CPI artifact and select **“CPI Import Settings.”**

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. The added link will be listed in the **Attachments** section and can be viewed by all relevant users

<figure><img src="../../../.gitbook/assets/image (11) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
