# Central Business Configuration

This user guide explains how to integrate and manage SAP Central Business Configuration (CBC) with ReleaseOwl. It covers credential registration, environment setup, artifact synchronization, pipeline configuration, user story promotion, and monitoring through logs and reports to enable streamlined and traceable CBC deployments.

### **Credential Manager** <a href="#credential-manager" id="credential-manager"></a>

1. Navigate to **Administrative Manager**.
2. Click on **Register Credential**.
3. Enter the required details:
   * **Credential Name**: Provide a name of your choice.
   * **Credential Type**: Select **Central Business Configuration**.
   * **Scope**: Choose the visibility of the credential:
     * **Global** – Accessible to all users.
     * **Private** – Accessible only to the user who created it.
   * **User Name**: Enter the **SAP CBC username**.
   * **Password**: Enter the **SAP CBC  password**.
4. Click **Save**.

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

### **Environment Registration** <a href="#environment-registration" id="environment-registration"></a>

1. Navigate to the **Environment** section.
2. Select **Central Business Configuration** and click **Register**.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Enter the required details:

* **Name** → Provide a meaningful name.
* **Credentials** → Select the credentials created in **Credential Management**.
* **Host URL** → Enter your tenant URL in the format: `https://<tenantID>.cbc.ap.one.cloud.sap.`
* **Workspace** → After entering the Host URL, the available CBC workspaces will be auto-populated in the dropdown, from which you can select the required workspace.
* **Environment Type** → Choose the appropriate type of environment (e.g., Development, Test, Production).

4. Click on the **Create** button to register the configuration.

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

### **Assign Environment to a Project**

1. Go to the **Projects** section and select your project.
2. Enter necessary details and choose **Project Type** as **SAP Public Cloud**.

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

3. Click **“Switch to Project”** for the project you just created.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FoY3Qi0wCDH1IdOUqlqCM%252Fimage.png%3Falt%3Dmedia%26token%3D4a0c87d4-12f3-49cd-b4c6-dd80e8051c41&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=36fc4a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. From the **Projects** dropdown (top-right corner), select **Project Settings → Environment**.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FFRngNLa4zFflP57OEDkW%252Fimage.png%3Falt%3Dmedia%26token%3D7cb30c81-5048-4fd4-840b-1394ad9d2003&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e25e5410&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. Click **+Add** to add a new environment.

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

6. On the subsequent screen, select the required environment from the Source list. Only artifacts with a defined source are synced to ReleaseOwl, and you can also add multiple source environments.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FiLZgyh0opkwImR2q0yzw%252Fimage.png%3Falt%3Dmedia%26token%3D97bb773c-438d-4a7a-aefd-805cb5853316&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=602ae35e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

7. The environment is added to the corresponding project in ReleaseOwl.
8. Click on the **Users** tab. This tab lists all existing users associated with the project.
9. Click on the **edit (lock)** icon next to the user for whom you want to manage roles and permissions.

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

10. Scroll down to the Environments section.
11. Select the _**Deploy**_ checkbox for the relevant environment(s) to grant the user deployment access.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F0cPCCoVERKPduu1KvXau%252Fimage.png%3Falt%3Dmedia%26token%3D01ab2d64-1f49-44a5-87c6-b2880a7956fa&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a378ba3d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Synchronize Artifacts**

1. Switch to the **Project View**.
2. Click on **Central Business Configuration** in the **Build** section.
3. Within the CBC screen, click the **Synchronize** button.
4. When synchronization is triggered, the system retrieves Deploy Scope and Organizational Structure activities from CBC where the **Action** is set to **Deploy**.

<figure><img src="../.gitbook/assets/image (1561).png" alt=""><figcaption></figcaption></figure>

5. These activities are then pulled into the project, ensuring that the latest CBC configurations are available for deployment workflows.

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

6. After synchronization, click on the **Action** button for the desired activity.
7. This will open detailed information about the selected activity.

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

8. Under the **Versions** tab, you can view the history of all modifications performed on the activity.\
   **Note:** The **Versions** tab is not available in the CBC (Central Business Configuration).
   * If the task is in **Open** status and is synchronized with Central Business Configuration, the task will be reopened.
   * If the task is in **Deploy** status and is reopened on a later date, a new version will be created to capture the changes.
9. This allows teams to track changes over time and ensure accountability.

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

10. **Change Logs**: It shows the details of activity changes, including the **Task Name, Area, Workspace, Changed By,** and **Changed On**. It provides visibility into where the change was made and by whom, helping teams monitor updates across tasks and workspaces.

<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

### **Creating a Release Pipeline**

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

**1. Create a New Release Pipeline**

* Navigate to **Release Pipelines**.
* Click **Create New Release Pipeline**.

<figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

* Provide a **Pipeline Name**.

<figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

* Add stages (e.g., QA, Prod) and assign tasks to each stage.

<figure><img src="../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

**Deployment Tasks**

A **Deployment Task** is used to deploy artifacts into the target **S/4HANA Public Cloud** environment as part of a pipeline stage.

**Steps to Configure a Deployment Task**

1. In a **Task Stage**, click the **Add** button and select **Deployment Task**.
2. Fill in the required details:

* **Name** → Enter a meaningful name for the deployment task.
* **Deploy Type** → Select **CBC**.
* **Select the Environment** → Choose the target environment where the deployment should be executed.

**Notification Options**

* **Notify Users** : Sends an email notification to all users involved in the pipeline when the pipeline is triggered or when specific events occur. By selecting this you will see the following options:&#x20;
* **Notify To** : Allows you to configure additional recipients for deployment notifications. Options include:
  * **User:** Notify a specific user.
  * **Role** : Notify all users assigned to a specific role.
  * **Custom:** Notify based on a **custom component and role** defined in ReleaseOwl.
* **Notify Promotion User** → Sends an email notification to the user who initiated the promotion (from a user story or release package), regardless of whether the task succeeds or fails.

3. After entering the details, click **Save** to add the deployment task.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FwonM23bT0N26ZFUfrLHz%252Fimage.png%3Falt%3Dmedia%26token%3D312a9a79-83e9-43d1-b558-76c0be6e1941&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ee0157a8&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Creating and Promoting a User Story**

A **User Story** in ReleaseOwl is used to **track, manage, and deploy tasks** from the source system to the target (destination) environment.

**Steps to Create and Promote a User Story**

1. **Create a User Story**
   * Navigate to **Change Management**.
   * Click **Create New User Story**.
   * Enter the required details (e.g., Name, Description, and other metadata).
   * Save the User Story.
2. **Add Artifacts**
   * Open the User Story and click **Edit**.
   * Click the **+ Add** button to attach CBC activities as artifacts.
   * After selecting the required artifacts, click **Save**.
3. **Promote the User Story**

* Once the artifacts are attached, click on the **Promote** button.
* Promotion moves the User Story into the defined pipeline stage, where it proceeds through tasks such as deployment according to the configured pipeline.

<figure><img src="../.gitbook/assets/image (15) (1).png" alt=""><figcaption></figcaption></figure>

#### **Deployment Logs**

The **Deployment Logs** are generated during execution of a **Deployment Task** and provide full traceability of the deployment process.

**Details captured in Deployment Logs:**

* **Deployed Environment** → Target environment where the artifacts were deployed.
* **Version** → Version of the artifacts included in the deployment.
* **User Story** → Associated user story that triggered the deployment.
* **Deployment Status** → Status of the deployment (Successful or Failed).
* **Tenant URL** → URL of the tenant where the deployment was executed.
* **Deployment ID** → A unique identifier assigned to the deployment for traceability. Selecting the Deployment ID redirects to the execution details of the deployment.

<figure><img src="../.gitbook/assets/image (16) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1560).png" alt=""><figcaption></figcaption></figure>
