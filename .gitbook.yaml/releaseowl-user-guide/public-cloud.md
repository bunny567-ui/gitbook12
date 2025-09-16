# Public Cloud

This user guide explains how to manage and deploy **SAP S/4HANA Public Cloud artifacts** using **ReleaseOwl**. It covers credential setup, environment registration, artifact synchronization, release pipelines, user stories, and monitoring via validation reports and deployment logs to ensure traceable and controlled deployments.

### **Credential Manager**

1. Navigate to **Administrative Manager**.
2. Click on **Register Credential**.
3. Enter the required details:
   * **Credential Name**: Provide a name of your choice.
   * **Credential Type**: Select **Public Cloud**.
   * **Scope**: Choose the visibility of the credential:
     * **Global** – Accessible to all users.
     * **Private** – Accessible only to the user who created it.
   * **User Name**: Enter the **SAP S/4HANA Cloud username**.
   * **Password**: Enter the **SAP S/4HANA Cloud password**.
4. Click **Save**.

<figure><img src="../.gitbook/assets/image (1502).png" alt=""><figcaption></figcaption></figure>

### **Environment Registration**

1. Navigate to the **Environment** section.
2. Select **S/4HANA Public Cloud Environment** and click **Register**.

<figure><img src="../.gitbook/assets/image (1533).png" alt=""><figcaption></figcaption></figure>

3. Enter the required details:

* **Name** → Provide a meaningful name.
* **Credentials** → Select the credentials created in **Credential Management**.
* **Host URL** → Enter your tenant URL in the format: `https://<tenantID>.s4hana.cloud.sap`.
*   **Client ID** → To locate the Client ID:

    * In SAP S/4HANA Cloud, go to **Profile → About**.

    <figure><img src="../.gitbook/assets/image (1535).png" alt=""><figcaption></figcaption></figure>
* Navigate to **System Information** and identify the System Name containing the system number.

<figure><img src="../.gitbook/assets/image (1536).png" alt=""><figcaption></figcaption></figure>

* **PC System Type** → Select the type of S/4HANA Public Cloud system you are registering, such as **Production**, **Quality**, or **Sandbox/Development**.
* **Environment Type** → Choose the desired environment type.

<figure><img src="../.gitbook/assets/image (1534).png" alt=""><figcaption></figcaption></figure>

#### **Assign Environment to a Project**

1. Go to the **Projects** section and select your project.
2. Enter necessary details and choose **Project Type** as **SAP Public Cloud**.

<figure><img src="../.gitbook/assets/image (1537).png" alt=""><figcaption></figcaption></figure>

3. Click **“Switch to Project”** for the project you just created.

<figure><img src="../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. From the **Projects** dropdown (top-right corner), select **Project Settings → Environment**.

<figure><img src="../.gitbook/assets/image (1538).png" alt=""><figcaption></figcaption></figure>

5. Click **+Add** to add a new environment.

<figure><img src="../.gitbook/assets/image (1539).png" alt=""><figcaption></figcaption></figure>

6. In the subsequent screen, choose the required environment from the list displayed by selecting Source. Only the artifacts with source are synced to ReleaseOwl.

<figure><img src="../.gitbook/assets/image (1513).png" alt=""><figcaption></figcaption></figure>

7. The environment is added to the corresponding project in ReleaseOwl.
8. Click on the **Users** tab. This tab lists all existing users associated with the project.
9. Click on the **edit (lock)** icon next to the user for whom you want to manage roles and permissions.&#x20;

<figure><img src="../.gitbook/assets/image (1516).png" alt=""><figcaption></figcaption></figure>

10. Scroll down to the Environments section.
11. Check the Deploy checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="../.gitbook/assets/image (1514).png" alt=""><figcaption></figcaption></figure>



#### **Synchronize Artifacts**

1. Switch to the **Project View**.
2. Click on **S/4HANA Public Cloud** in the **Build** section.
3. Click the **Synchronize** button.
   * This retrieves all artifacts of type **Transport** and **Software Collection** from the S/4HANA Public Cloud into ReleaseOwl.

<figure><img src="../.gitbook/assets/image (1517).png" alt=""><figcaption></figcaption></figure>

### **Viewing Synchronized Artifacts**

* When artifacts are synchronized from **SAP S/4HANA Public Cloud**, the following details are shown:
  * **Collection Type** – Represents the **category** of the artifact.&#x20;
  * **Type** – Defines the **artifact entity**, which can be:
    * _Transport_
    * _Software Collection_
* Display rules:
  * **Transports** → Only shown when the status is **Released**.
  * **Software Collections** → Only shown when the status is **Exported**.
* For each artifact, metadata such as **ID, Name, Status, Timestamp, and Type** is displayed for audit and traceability.

<figure><img src="../.gitbook/assets/image (1515).png" alt=""><figcaption></figcaption></figure>

14. **Transports:** &#x20;
    * When you click on the **action button** for a transport, you can see the **Objects** button.
    * Clicking **Objects** button displays the **list of technical objects** included in the synchronized transport.

<figure><img src="../.gitbook/assets/image (1518).png" alt=""><figcaption></figcaption></figure>

15. **Software\_collections:**&#x20;

* When you click the Action button for a Software Collection, the available options are: Sync, Versions, and Items.

<figure><img src="../.gitbook/assets/image (1523).png" alt=""><figcaption></figcaption></figure>

**Sync:** Used to synchronize the latest version of the software collection.

**Versions** : Displays the versions of the Software Collection, representing the history of changes made over time (e.g., Version 1, Version 2, etc.). Versions can also be **assigned to a User Story** or **unassigned** as needed for tracking and deployment purposes.

<figure><img src="../.gitbook/assets/image (1522).png" alt=""><figcaption></figcaption></figure>

**Items** : Shows the **individual items** that are part of the software collection and were created in S/4HANA Public Cloud.

<figure><img src="../.gitbook/assets/image (1521).png" alt=""><figcaption></figcaption></figure>

#### Creating a Release Pipeline <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline-3" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline-3"></a>

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

**1. Create a New Release Pipeline**

* Navigate to **Release Pipelines**.
* Click **Create New Release Pipeline**.

<figure><img src="../.gitbook/assets/image (1524).png" alt=""><figcaption></figcaption></figure>

* Provide a **Pipeline Name**.

<figure><img src="../.gitbook/assets/image (1525).png" alt=""><figcaption></figcaption></figure>

* Add stages (e.g., QA, Prod) and assign tasks to each stage.

<figure><img src="../.gitbook/assets/image (1526).png" alt=""><figcaption></figcaption></figure>

### **Validation Task**

A **Validation Task** allows you to validate S/4HANA Public Cloud artifacts as part of a pipeline execution. It ensures that the artifacts meet required quality checks before being promoted further in the pipeline

1. In a **Task Stage**, click on the **Add** button and select **Validation**.
2. Fill in the required details:

* **Name**: Provide a meaningful name for the validation task.
* **Description**: Enter a message or note to be displayed to the task approver.
* **S/4HANA Public Cloud**: Select the **target environment** where the validation will be executed.
* **Quality Checks**: Enable this option to perform automated quality checks during validation.
  * Includes **User Story Dependencies (Beta)**: This feature analyzes and validates dependent user stories to avoid conflicts or incomplete deployments.
* **Pipeline Execution**: Defines execution preferences for the validation task.
  * **Continue on Failure**: If enabled, the pipeline continues execution even if the validation task fails.

<figure><img src="../.gitbook/assets/image (1527).png" alt=""><figcaption></figcaption></figure>

#### **Deployment Tasks**

A **Deployment Task** is used to deploy artifacts into the target **S/4HANA Public Cloud** environment as part of a pipeline stage.

#### **Steps to Configure a Deployment Task**

1. In a **Task Stage**, click the **Add** button and select **Deployment Task**.
2. Fill in the required details:

* **Name** → Enter a meaningful name for the deployment task.
* **Deploy Type** → Select **S/4HANA Public Cloud**.
* **Select the Environment** → Choose the target environment where the deployment should be executed.

#### **Notification Options**

* **Notify Users** → Sends an email notification to all users involved in the pipeline when the pipeline is triggered or when specific events occur.
* **Notify Promotion User** → Sends an email notification to the user who initiated the promotion (from a user story or release package), regardless of whether the task succeeds or fails.
* **Notify To** → Allows you to configure additional recipients for deployment notifications. Options include:
  * **User** → Notify a specific user.
  * **Role** → Notify all users assigned to a specific role.
  * **Custom** → Notify based on a **custom component and role** defined in ReleaseOwl.

3. After entering the details, click **Save** to add the deployment task.

<figure><img src="../.gitbook/assets/image (1528).png" alt=""><figcaption></figcaption></figure>

&#x20;**Approval Tasks**

An **Approval Task** is used to introduce manual approval checkpoints within a pipeline stage before execution proceeds. This ensures controlled deployments and adherence to governance policies.

**Steps to Configure an Approval Task**

1. In a **Task Stage**, click the **Add** button and select **Approval Task**.
2. Fill in the required details:

* **Name** → Enter a meaningful name for the approval task.
* **Description** → Provide any context or instructions for the approver.
* **Assign To** → Select the approval mode:
  * **User** → Assign the approval to a specific user.
  * **Role** → Assign the approval to all users of a specific role (any one of them can approve).
  * **Custom** → Assign approval to a **custom component and role** defined in ReleaseOwl.

3. Click **Save**.

<figure><img src="../.gitbook/assets/image (1529).png" alt=""><figcaption></figcaption></figure>

### **Creating and Promoting a User Story**

A **User Story** in ReleaseOwl is used to track, manage, and promote changes from **SAP S/4HANA Public Cloud** artifacts.

#### **Steps to Create and Promote a User Story**

1. **Create a User Story**
   * Navigate to **Change Management**.
   * Click **Create New User Story**.
   * Enter the required details (e.g., Name, Description, and other metadata).
   * Save the User Story.
2. **Add Artifacts**
   * Open the User Story and click **Edit**.
   * Click the **+ Add** button to attach **S/4HANA Public Cloud artifacts** (such as Transports or Software Collections).
   * After selecting the required artifacts, click **Save**.
3. **Promote the User Story**
   * Once the artifacts are attached, click on the **Promote** button.
   * Promotion moves the User Story into the defined **pipeline stage**, where it will go through tasks such as **Validation**, **Approval**, and **Deployment** based on the configured pipeline.

<figure><img src="../.gitbook/assets/image (1530).png" alt=""><figcaption></figcaption></figure>

### **Validation Report and Deployment Logs**

#### **1. Validation Report**

The Validation Report is generated when a Validation Task is executed in the pipeline. It provides insights into whether the S/4HANA Public Cloud artifacts (Transports or Software Collections) meet the required conditions before deployment.

**Contents of the Validation Report:**

* **List of Validated Artifacts** → Provides details of the artifacts that were validated during execution.
* **User Story Dependencies (Beta)** → Provides details of dependent user stories to help prevent conflicts or incomplete deployments.
* **Versions** → Provides details of the artifact version history (e.g., Version 3, Version 4), helping track and compare changes over time

<figure><img src="../.gitbook/assets/image (1531).png" alt=""><figcaption></figcaption></figure>

#### **2. Deployment Logs**

The Deployment Logs are generated during the execution of a Deployment Task and provide full traceability of the deployment process.

**Contents of Deployment Logs:**

* **List of Deployed Artifacts** → Provides details of the artifacts (Transports / Software Collections) deployed during execution.
* **Deployment Status** → Provides details of whether the deployment was Successful or Failed.
* **Already Deployed** → Provides details of the artifacts that were previously deployed and skipped during execution.
* **Manual Completion** → Provides details of the deployments that were marked as completed manually instead of through automated execution.

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
