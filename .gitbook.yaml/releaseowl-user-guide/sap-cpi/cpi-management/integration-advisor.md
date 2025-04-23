# Integration Advisor

**Prerequisites** : Before proceeding with Integration Advisor , ensure the following are in place:

1. **Integration Suite Created**: The **Integration Suite** must be set up within SAP Business Technology Platform (SAP BTP).
2. **API Instance Created**: An **API Instance** must be created to provide the credentials required for configuration in the **CPI Environment**.
3. SAP CPI Environment Configured in ReleaseOwl

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

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F4jQm2pQVZonuKCc9mWeb%252Fimage.png%3Falt%3Dmedia%26token%3D6ab8b264-ff50-4da4-85e5-6802faaf7b76&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ac6dc6ca&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Creating MIG and MAG in Integration Advisor** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-creating-mig-and-mag-in-integration-advisor" id="pdf-page-gq2jqh5hz5sfguou1udk-creating-mig-and-mag-in-integration-advisor"></a>

The following integration artifacts are created within the **Integration Advisor** service in **SAP Business Technology Platform (SAP BTP)**:

* **MIG (Message Implementation Guideline)**
* **MAG (Mapping Guideline)**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FWh88x04EPBMdYDQxMis8%252Fimage.png%3Falt%3Dmedia%26token%3D5e025e74-426f-4635-9d5e-bca20d788e78&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1b29766b&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Creating the project** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-creating-the-project" id="pdf-page-gq2jqh5hz5sfguou1udk-creating-the-project"></a>

1. Go to the **Administration** page.
2. Under the **Projects** section, click on the **Create New Project** button (top-right corner).
3. Fill in the **Project Details**:
   * A popup form titled **Create Project** will appear.
   * Enter the required details in the form.
4. Click **Save** to create the project.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FiNc7EpUgYqLEXu9klmAH%252Fimage.png%3Falt%3Dmedia%26token%3D7c78e385-e4c7-4b4b-b46f-7dfd90c6fffa&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9e9e4993&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Environment Section** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-environment-section" id="pdf-page-gq2jqh5hz5sfguou1udk-environment-section"></a>

1. The newly created project will be listed in the **Projects** table.
2. Click on **Switch to Project** and go to the **Project Settings**.
3. In the **Project Settings** page, navigate to the **Environments** tab.
4. This section displays all environments already associated with the project.
5. Click on the **+ Add** button in the top-right corner of the **Environments** table.
6. If this environment will serve as the source for deployments or synchronization, check the **Source** checkbox.
7. The newly added environment will appear in the **Environments** table with its **Name, Type, and Host URL**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FNMVWnATkmG60IB12U59B%252Fimage.png%3Falt%3Dmedia%26token%3D4c10b5ba-111d-4c09-89a3-4ca9d63dfffd&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9469559b&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Managing User Permissions <a href="#pdf-page-gq2jqh5hz5sfguou1udk-managing-user-permissions" id="pdf-page-gq2jqh5hz5sfguou1udk-managing-user-permissions"></a>

1. Click on the **Users** tab.
2. Click on the **edit (lock) icon** next to the user for whom you want to manage roles and permissions.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FGicwuJGYnjRXVwGhx0iw%252Fimage.png%3Falt%3Dmedia%26token%3Df13b964f-c9d7-4f09-96e2-1f43351a489b&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9b867037&#x26;sv=2" alt=""><figcaption></figcaption></figure>

3. The **Permissions** page for the selected user will open.
4. Scroll down to the **Environments** section.
5. Check the **Deploy** checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F9Qr27CHz3jVl6fYzalV3%252Fimage.png%3Falt%3Dmedia%26token%3Ddc3a9f97-6966-4819-9e5f-4f4513e04914&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=dc3c4008&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Synchronization with ReleaseOwl <a href="#pdf-page-gq2jqh5hz5sfguou1udk-synchronization-with-releaseowl" id="pdf-page-gq2jqh5hz5sfguou1udk-synchronization-with-releaseowl"></a>

1. Go to the **Build** section and click on **Integration Advisor**.
2. Click on the **Synchronize** button to sync the integration artifacts.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FmFpuaBpGStdno4xQiDy2%252Fimage.png%3Falt%3Dmedia%26token%3Dc59963be-2177-4df3-b493-26783c2ad838&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4f9fa7a2&#x26;sv=2" alt=""><figcaption></figcaption></figure>

3. The **Sync History** provides details of previous synchronizations, including:

* **Synced On** – Timestamp of synchronization.
* **Synced By** – User who performed the synchronization.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FFPvPAoAw6OcveTuQ8WQi%252Fimage.png%3Falt%3Dmedia%26token%3D052ffbab-3df3-4b30-bf23-60ffd53adf20&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1331cc1d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. By clicking the **Action** button, you can view:

* **Versions**: Displays previous versions, allowing you to roll back changes if needed.
* **Details**: Provides additional information about the artifact.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FTD7R4MPSlL5jO1o4hqYD%252Fimage.png%3Falt%3Dmedia%26token%3D4dec8a50-c84d-4032-a537-156bc131bdff&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=10c0f343&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Creating and Managing a Release Pipeline** <a href="#pdf-page-gq2jqh5hz5sfguou1udk-creating-and-managing-a-release-pipeline" id="pdf-page-gq2jqh5hz5sfguou1udk-creating-and-managing-a-release-pipeline"></a>

**1. Creating a New Release Pipeline**

1. Navigate to the **Release** section.
2. Click on **Release Pipeline** and select **Create New Release Pipeline**.
3. Enter a **name** for the release pipeline.
4. Click **+Add Stage** to create a new stage.

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

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FaOUCd2mJzY9qdUkCWpih%252Fimage.png%3Falt%3Dmedia%26token%3D064efdb7-b814-4220-9a12-693a3880bda1&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4ce95ce1&#x26;sv=2" alt=""><figcaption></figcaption></figure>

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

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fd5eqDRNGEwNyduLR488w%252Fimage.png%3Falt%3Dmedia%26token%3Dc9991fd5-208d-4f2c-b023-1ed642800725&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=db745875&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**4. Assigning Artifacts to User Stories**

1. Navigate to **Change Management** and click on **User Stories**.
2. Click **Create New User Story**, fill in the required details, and save it.
3. Click on the **Action** button, select **Edit**, and add the **integration artifacts**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FkLlWHDONOgwBpiDtKCnY%252Fimage.png%3Falt%3Dmedia%26token%3D103cb251-78c0-48bd-b818-1e61e7a31343&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3c3f9b36&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Click **Save** to update the user story.
5. Click **Promote** to check the **deployment status** of the user story.
6. Click **Deploy Logs** to view deployment details.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FQONwRnh04PDIdvuFhuNt%252Fimage.png%3Falt%3Dmedia%26token%3Df0c4cd0e-098b-4ba5-b639-d092338aaeb7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e364beeb&#x26;sv=2" alt=""><figcaption></figcaption></figure>

7. In the **Info Section**, you can see **artifact details**:

* **For MAG:**  You can see the details of Message type and administrative data.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FWWwAmMIsMhIoQQ8WTmbp%252Fimage.png%3Falt%3Dmedia%26token%3D8d155c19-ae3a-48e3-a3b1-fb1c3c809645&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=efb81760&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* **For MIG:** You can see the details of Source MIG, Target MIG, and administrative data.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FxBEPO7qRLrbcGHwY8Bx2%252Fimage.png%3Falt%3Dmedia%26token%3Db10c1192-3e78-47e0-963d-b61649da4ba5&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=eaaccd39&#x26;sv=2" alt=""><figcaption></figcaption></figure>
