# Integration Advisor

The **Integration Advisor** in SAP Integration Suite helps streamline and accelerate integration projects by providing tools to define, customize, and manage interface content such as codelists, IDocs, messages, and SOA structures. It enables organizations to adapt standard content to meet specific business requirements, ensuring consistency and reducing manual effort in integration scenarios.

Before using Integration Advisor, some setup is required both in **SAP BTP** and in **ReleaseOwl** to enable access and manage integration artifacts effectively.

### **Prerequisites**&#x20;

Before proceeding with Integration Advisor , ensure the following are in place:

1. **Integration Suite Created**: The **Integration Suite** must be set up within SAP Business Technology Platform (SAP BTP).
2. **API Instance Created**: An **API Instance** must be created to provide the credentials required for configuration in the **CPI Environment**.
3. SAP CPI Environment Configured in ReleaseOwl
4.  &#x20;**Role Collections Assigned**: To enable Integration Advisor capabilities, assign the following role collections to the **Identity Provider (IdP)**:

    * `iadv-content-read`
    * `iadv-content-administrator`
    * `Integration Advisor (Non-Prod & Prod)`&#x20;


5. **Create the Custom Role  Collection:**&#x20;

* Navigate to **Security → Role Collections** in the SAP BTP Cockpit.

<figure><img src="../../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

* Click **Create** and enter the **Role Collection Name**. Confirm by clicking **Create**.
* Once the role collection is created, select it from the list and click **Edit**.

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

* Under the **Roles** section, click **Add Role** and assign the required roles. Add the **Content Developer** role.
* Click **Save** to update the role collection.

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

### **Steps to Create a Custom Type System** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-steps-to-create-a-custom-type-system" id="pdf-page-gq2jqh5hz5sfguou1udk-steps-to-create-a-custom-type-system"></a>

1. Navigate to **Integration Suite**.
2. Click on the **Actions** button (**...**) to open the application.
3. Click on the **Design** section.
4. Under **Design**, select **Custom Type Systems**.
5. Choose the type of system you want to create:
   * **Custom Codelists**
   * **Custom IDocs**
   * **Custom Messages**
   * **Custom SOA Messages**
6. Enter the required details and save the configuration.

<figure><img src="../../../.gitbook/assets/image (97).png" alt=""><figcaption></figcaption></figure>

### **Creating MIG and MAG in Integration Advisor** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-creating-mig-and-mag-in-integration-advisor" id="pdf-page-gq2jqh5hz5sfguou1udk-creating-mig-and-mag-in-integration-advisor"></a>

1. Navigate to **Integration Advisor** and go to the **MIG** section.
2. Click on the **Create** button to initiate a new Message Implementation Guideline (MIG).
3. In the **Type Systems** step, switch to the **Custom** tab.
4. You will see the available **Custom Type Systems** that you previously configured (e.g., Custom Codelists, Custom IDocs, etc.).
5. Select the appropriate **Custom Type** System to proceed with creating your MIG or MAG.

<figure><img src="../../../.gitbook/assets/image (1122).png" alt=""><figcaption></figcaption></figure>

### **Creating the project** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-creating-the-project" id="pdf-page-gq2jqh5hz5sfguou1udk-creating-the-project"></a>

1. Go to the **Administration** page.
2. Under the **Projects** section, click on the **Create New Project** button (top-right corner).
3. Fill in the **Project Details**:
   * A popup form titled **Create Project** will appear.
   * Enter the required details in the form.
4. Click **Save** to create the project.

<figure><img src="../../../.gitbook/assets/image (1326).png" alt=""><figcaption></figcaption></figure>

### **Environment Section** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-environment-section" id="pdf-page-gq2jqh5hz5sfguou1udk-environment-section"></a>

1. The newly created project will be listed in the **Projects** table.
2. Click on **Switch to Project** and go to the **Project Settings**.
3. In the **Project Settings** page, navigate to the **Environments** tab.
4. This section displays all environments already associated with the project.
5. Click on the **+ Add** button in the top-right corner of the **Environments** table.
6. If this environment will serve as the source for deployments or synchronization, check the **Source** checkbox.
7. The newly added environment will appear in the **Environments** table with its **Name, Type, and Host URL**.

<figure><img src="../../../.gitbook/assets/image (1327).png" alt=""><figcaption></figcaption></figure>

### Managing User Permissions <a href="#pdf-page-gq2jqh5hz5sfguou1udk-managing-user-permissions" id="pdf-page-gq2jqh5hz5sfguou1udk-managing-user-permissions"></a>

1. Click on the **Users** tab.
2. Click on the **edit (lock) icon** next to the user for whom you want to manage roles and permissions.

<figure><img src="../../../.gitbook/assets/image (1328).png" alt=""><figcaption></figcaption></figure>

3. The **Permissions** page for the selected user will open.
4. Scroll down to the **Environments** section.
5. Check the **Deploy** checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="../../../.gitbook/assets/image (1329).png" alt=""><figcaption></figcaption></figure>

### Synchronization with ReleaseOwl <a href="#pdf-page-gq2jqh5hz5sfguou1udk-synchronization-with-releaseowl" id="pdf-page-gq2jqh5hz5sfguou1udk-synchronization-with-releaseowl"></a>

1. Go to the **Build** section and click on **Integration Advisor**.
2. Click on the **Synchronize** button to sync the integration artifacts.

<figure><img src="../../../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>

3. The **Sync History** provides details of previous synchronizations, including:

* **Synced On** – Timestamp of synchronization.
* **Synced By** – User who performed the synchronization.

<figure><img src="../../../.gitbook/assets/image (84).png" alt=""><figcaption></figcaption></figure>

4. By clicking the **Action** button, you can view:

* **Versions**: Displays previous versions, allowing you to roll back changes if needed.&#x20;
* When you open the **Versions** tab, you can:
  * View the complete version history.
  * **Assign** or **Unassign** a user story linked to a particular version.
  * Track changes made across different versions for audit or review purposes.

<figure><img src="../../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

* **Download**
  * The **Download** option under the Action menu lets you download the message or artifact locally.

<figure><img src="../../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

* **Details**: Provides additional information about the artifact.

<figure><img src="../../../.gitbook/assets/image (86).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

### **Creating and Managing a Release Pipeline** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-creating-and-managing-a-release-pipeline" id="pdf-page-gq2jqh5hz5sfguou1udk-creating-and-managing-a-release-pipeline"></a>

**1. Creating a New Release Pipeline**

1. Navigate to the **Release** section.
2. Click on **Release Pipeline** and select **Create New Release Pipeline**.

<figure><img src="../../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

3. Enter a **name** for the release pipeline.
4. Click **+Add Stage** to create a new stage.

<figure><img src="../../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

**2. Configuring Deployment Tasks**

1. Under the **Tasks** section, click **Add** to create a task.
2. Select the **deployment** option for the deployment process.
3. Fill in the required details:
   * **Name:** Enter the task name.
   * **Deploy Type:** Choose either **CPI** or **API**.
   * **Select Environment:** Choose the target environment for deployment.
   * **Deployment Action:**
     * **Upload and Deploy:** Uploads and immediately deploys the package.
     * **Upload Only:** Uploads the package without deployment.
   * **Rollback Settings:** Enable rollback if needed for deployment recovery.
4. Once all required details are entered, **save** the pipeline.
5. _(Optional)_ Configure **Notification Emails** to notify relevant users.

<figure><img src="../../../.gitbook/assets/image (87).png" alt=""><figcaption></figcaption></figure>

**3. Setting Up Approval Tasks**

1. Under the **Tasks** section, click **Add** to create a task and select **Approval Task**.
2. Fill in the necessary details:
   * **Name:** Assign a name to the approval task.
   * **Assign To:** Select who should approve the task:
     * **User:** Assign a specific user.
     * **Role:** Assign based on user roles.
     * **Custom:** Assign based on a custom rule.
     * **Story Assignee:** Assign to the person responsible for the user story.
3. Once configured, **save** the pipeline.

<figure><img src="../../../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

**4. Assigning Artifacts to User Stories**

1. Navigate to **Change Management** and click on **User Stories**.
2. Click **Create New User Story**, fill in the required details, and save it.
3. Click on the **Action** button, select **Edit**, and add the **integration artifacts**.

<figure><img src="../../../.gitbook/assets/image (89).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (90).png" alt=""><figcaption></figcaption></figure>

4. Click **Save** to update the user story.
5. Click **Promote** to check the **deployment status** of the user story.
6. Click **Deploy Logs** to view deployment details.

<figure><img src="../../../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

7. In the **Info Section**, you can see **artifact details**:

* **For MAG:**  You can see the details of Message type and administrative data.

<figure><img src="../../../.gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>

* **For MIG:** You can see the details of Source MIG, Target MIG, and administrative data.

<figure><img src="../../../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>
