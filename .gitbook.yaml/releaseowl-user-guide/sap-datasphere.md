# SAP Datasphere

This guide details the step-by-step process for registering SAP Datasphere in ReleaseOwl, including environment management, user permission configuration, package synchronization, and efficient execution of deployment processes.

### Credential Registration <a href="#pdf-page-dk8rbzgxugve408ig5ly-credential-registration" id="pdf-page-dk8rbzgxugve408ig5ly-credential-registration"></a>

1. Admin users can switch to the **Administration View** to access the **Credential Manager**.
2. Click the **Credential Manager** menu option on the left-hand pane to view the list of registered credentials.

<figure><img src="../.gitbook/assets/image (1363).png" alt=""><figcaption></figcaption></figure>

3. To add a new credential, click **Register Credential** available on the right-hand panel, and then click on the **Register Credential** button.

<figure><img src="../.gitbook/assets/image (1364).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FOlQXbRau9NAUz064D5V8%252Fimage.png%3Falt%3Dmedia%26token%3D403b126d-ca63-4a3f-ab49-49cb64c161bd&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=cb343d62&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **SAP Datasphere.**

<figure><img src="../.gitbook/assets/image (1365).png" alt=""><figcaption></figcaption></figure>

5. For the Client ID, Secret, Token URL, and Authorization URL:
6. Log in to your **SAP Datasphere** (formerly known as SAP Data Warehouse Cloud) instance.

* Click on your **profile icon** in the top-right corner.
* Select **System** > **Administration**.

<figure><img src="../.gitbook/assets/image (1366).png" alt=""><figcaption></figcaption></figure>

* Navigate to the **App Integration** tab.

<figure><img src="../.gitbook/assets/image (1367).png" alt=""><figcaption></figcaption></figure>

7. **Add a New OAuth Client:**

* Click on **Add OAuth Client**.
* Provide a **Client Name**.
* Enter the **Redirect URI** (callback URL for your application).
* Click **Add** to register the client.

{% hint style="info" %}
**Note :** Once added, the system will generate the **Client ID** and **Client Secret**. Ensure these values are copied and stored securely.
{% endhint %}

<figure><img src="../.gitbook/assets/image (1368).png" alt=""><figcaption></figcaption></figure>

8. **Obtain OAuth Endpoints:**

* The **Authorization URL** and **Token URL** can be accessed from the **App Integration** section, typically shown outside the list of registered clients.

9. **Save OAuth Credentials:**

In the Credential Manager, provide the following details:

* **Client ID**
* **Client Secret**
* **Authorization URL**
* **Token URL**

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

* After entering the required information, click the **Save** button. Upon successful save, a **Generate Token** button will appear. Click this button to initiate token generation and validate the entered credentials.

<figure><img src="../.gitbook/assets/image (5) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* This process confirms whether the provided details can establish a successful connection with the authentication server.

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

### **To Register SAP Datasphere:** <a href="#pdf-page-dk8rbzgxugve408ig5ly-to-register-sap-datasphere" id="pdf-page-dk8rbzgxugve408ig5ly-to-register-sap-datasphere"></a>

1. In Environments, go to **SAP Datasphere**.

<figure><img src="../.gitbook/assets/image (1358).png" alt=""><figcaption></figcaption></figure>

2. Click **Register SAP Datasphere Environment**. The following screen is displayed:

<figure><img src="../.gitbook/assets/image (1359).png" alt=""><figcaption></figcaption></figure>

3. **Fill in the required details:**

* **Name**: Enter a name for your reference.
* **OAuth Credentials**: Select the SAP Datasphere OAuth Credentials registered with ReleaseOwl.
* **Host URL**: Enter the host URL of the SAP Datasphere environment.
* **Environment Type**: Select the environment type you are registering (e.g., Dev or QA, etc.).

4. Click **Save** to register the environment.

<figure><img src="../.gitbook/assets/image (1360).png" alt=""><figcaption></figcaption></figure>

5. The registered environments are displayed.
6. Click on the required environment to view the details.
7. Click the **edit icon** to edit the registered SAC Environment.
8. Click the **delete icon** to delete the required environment.

<figure><img src="../.gitbook/assets/image (1361).png" alt=""><figcaption></figcaption></figure>

### **Adding SAP Datasphere to the Project:** <a href="#pdf-page-gxe94pcl07aymb35lkd4-adding-sac-environments-to-the-project" id="pdf-page-gxe94pcl07aymb35lkd4-adding-sac-environments-to-the-project"></a>

The SAP Datasphere must be registered in **Project Settings** in ReleaseOwl.

1.  **To register SAP datasphere:**

    * Go to the **Projects** drop-down at the top right corner and click **Project Settings**.
    * In **Project Settings**, navigate to **Environment**.
    * The following screen is displayed.

    <figure><img src="../.gitbook/assets/image (968).png" alt=""><figcaption></figcaption></figure>
2.  **Click Add** to add a new environment in ReleaseOwl.

    * In the subsequent screen, select the required environments from the list displayed.
    * Select **Source environment** and **Save** the changes.

    <figure><img src="../.gitbook/assets/image (969).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Only the artifacts from the source are synced to ReleaseOwl.
{% endhint %}

3. The environment gets added to the corresponding project in ReleaseOwl.

<figure><img src="../.gitbook/assets/image (970).png" alt=""><figcaption></figcaption></figure>

4. Click on the **Users** tab. This tab lists all existing users associated with the project.
5. Click on the **edit (lock)** icon next to the user for whom you want to manage roles and permissions.
6. This will open the **Permissions** page for the selected user.

<figure><img src="../.gitbook/assets/image (981).png" alt=""><figcaption></figcaption></figure>

7. Under the **lock icon** button. The roles assigned to the selected user are displayed.

<figure><img src="../.gitbook/assets/image (973).png" alt=""><figcaption></figcaption></figure>

8. Scroll down to the Environments section.
9. Check the Deploy checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="../.gitbook/assets/image (972).png" alt=""><figcaption></figcaption></figure>

### **SAP Datasphere  and Deployment**

1.  **Sync Packages:**

    * Go to **SAP Datasphere** in the **Build** section and click on **Sync Packages**.

    <figure><img src="../.gitbook/assets/image (974).png" alt=""><figcaption></figcaption></figure>

    * You can see the **Deployment History** by clicking on the **Actions** button and selecting **Deployment History**.

    <figure><img src="../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
2.  **View Package Details:**

    * Click the **Actions** button and select **Import Settings** to view package details.

    <figure><img src="../.gitbook/assets/image (975).png" alt=""><figcaption></figcaption></figure>



    * Each package has different import settings, and you need to configure the import settings for the required package.

    <figure><img src="../.gitbook/assets/image (976).png" alt=""><figcaption></figcaption></figure>
3. **Release  Pipelines:**

* Go to the Release Pipelines and click on the **Create New Release Pipeline.**

<figure><img src="../.gitbook/assets/image (1376).png" alt=""><figcaption></figcaption></figure>

* Enter a **Pipeline Name**.

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Click **Add Stage**.

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Enter the stage name say for e.g., UAT or QA where the deployment has to be carried out and click OK.

<figure><img src="../.gitbook/assets/image (382).png" alt=""><figcaption></figcaption></figure>

* **Tasks:** Click **Add** to enter any tasks that are to be performed.

<figure><img src="../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** To remove any stage, click Remove stage button.
{% endhint %}

* Different tasks that can be added are as follows:\


<figure><img src="../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Add a Deployment Stage**

* Click on **Add** under the **Tasks** section.
* Select **SDS - Deployment** from the available task types.

**Configure Task Details**

In the **Task Details** panel on the right side, fill in the following information:

| **Field**                  | **Description**                                               |
| -------------------------- | ------------------------------------------------------------- |
| **Name**                   | Enter a unique name for your task.                            |
| **Description**            | Optionally, provide a brief description of the task.          |
| **Select SDS Environment** | Choose the SDS environment for deployment from the dropdown.  |

**Optional Settings**

You may optionally configure the following:

* **Schedule Time**\
  Enable this checkbox to schedule the deployment at a specific date and time.
* **Notify Users**\
  Enable this checkbox to send email notifications to selected users after task execution.
* **Notify Promotion User**\
  Enable this checkbox to notify the user who promoted the pipeline.

**Finalize the Task**

* Once all configurations are complete, click **Next** to proceed to **Step 3: Notification Email(s)** or continue adding more tasks as needed.

<figure><img src="../.gitbook/assets/image (1382).png" alt=""><figcaption></figcaption></figure>

4. **Change Management:**

* Navigate to the **Change Management** section.
* Go to **User Stories**, click on the **Create New User Story**.

<figure><img src="../.gitbook/assets/image (1383).png" alt=""><figcaption></figcaption></figure>

* Fill in the required fields, such as:
  * **Summary**: A clear and concise name for the user story.
  * **Description**: Detailed explanation of the requirement or feature.
  * **Release Version**, **Sprint**, **Assigned To**, and any other custom fields as applicable.
* After entering the details, click the **Save** button to create the User Story.

<figure><img src="../.gitbook/assets/image (1379).png" alt=""><figcaption></figcaption></figure>

* Once the User Story is created, it will appear in the list/grid view.
* Click on the **Edit** next to the User Story entry.

<figure><img src="../.gitbook/assets/image (1384).png" alt=""><figcaption></figcaption></figure>

* Click on the **+Add** button to add **SAC Packages**.
* Click on the **Save** button.

<figure><img src="../.gitbook/assets/image (1357).png" alt=""><figcaption></figcaption></figure>

4. **Promote User Story:**

* Click on **Promote** to promote the user story.

<figure><img src="../.gitbook/assets/image (1356).png" alt=""><figcaption></figcaption></figure>

5.  **Check Deployment Status:**

    * Click on the **Pipeline Activity** to view the deployment status.

    <figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



* Click on the **"Deploy Log"** button.

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* A pop-up window titled **SAP Datasphere Cloud Deploy Log** will appear, displaying deployment details.

<figure><img src="../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
