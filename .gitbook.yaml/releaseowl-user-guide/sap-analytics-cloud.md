# SAP Analytics Cloud

SAP Analytics Cloud (SAC) is a cloud-based business intelligence (BI) and analytics platform that integrates data visualization, planning, and predictive analytics.

### Credential Registration <a href="#pdf-page-gxe94pcl07aymb35lkd4-credential-registration" id="pdf-page-gxe94pcl07aymb35lkd4-credential-registration"></a>

1. Admin users can switch to the **Administration View** to access the **Credential Manager**.
2. Click the **Credential Manager** menu option on the left-hand pane to view the list of registered credentials.

<figure><img src="../.gitbook/assets/image (41) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. To add a new credential, click **Register Credential** available on the right-hand panel, and then click on the **Register Credential** button.

<figure><img src="../.gitbook/assets/image (1343).png" alt=""><figcaption></figcaption></figure>

4. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **SAP Analytics Cloud**.

<figure><img src="../.gitbook/assets/image (1344).png" alt=""><figcaption></figcaption></figure>

5. For the Client ID, Secret, Token URL, and Authorization URL:

* Go to your **SAP Analytics Cloud** and navigate to **Administration**.

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

* Click on **App Integration** for the **OAuth Clients**.
* Click on **Add an OAuth Client**.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

* Copy the **Client ID, Secret, Token URL,** and **Authorization URL**.

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

### **To Register SAC Environment:** <a href="#pdf-page-gxe94pcl07aymb35lkd4-to-register-sac-environment" id="pdf-page-gxe94pcl07aymb35lkd4-to-register-sac-environment"></a>

1. In Environments, go to **SAP Analytics Cloud**.

<figure><img src="../.gitbook/assets/image (1338).png" alt=""><figcaption></figcaption></figure>

2. Click **Register SAC Environment**. The following screen is displayed:

<figure><img src="../.gitbook/assets/image (1339).png" alt=""><figcaption></figcaption></figure>

3. **Fill in the required details:**

* **Name**: Enter a name for your reference.
* **Landscape**: Select the Landscape in use.
* **OAuth Credentials**: Select the SAC OAuth Credentials registered with ReleaseOwl.
* **Host URL**: Enter the host URL of the SAP Analytics Cloud environment.
* **Environment Type**: Select the environment type you are registering (e.g., Dev or QA, etc.).

<figure><img src="../.gitbook/assets/image (1340).png" alt=""><figcaption></figcaption></figure>

4. Click **Save** to register the environment.

<figure><img src="../.gitbook/assets/image (1341).png" alt=""><figcaption></figcaption></figure>

5. Similarly, register the target SAC environment as follows:
6. The registered environments are displayed.

<figure><img src="../.gitbook/assets/image (1342).png" alt=""><figcaption></figcaption></figure>

7. Click on the required environment to view the details.
8. Click the **edit icon** to edit the registered SAC Environment.
9. Click the **delete icon** to delete the required environment.

<figure><img src="../.gitbook/assets/image (1345).png" alt=""><figcaption></figcaption></figure>

### **Adding SAC Environments to the Project:** <a href="#pdf-page-gxe94pcl07aymb35lkd4-adding-sac-environments-to-the-project" id="pdf-page-gxe94pcl07aymb35lkd4-adding-sac-environments-to-the-project"></a>

The SAC environments must be registered in **Project Settings** in ReleaseOwl.

1.  **To register SAC environment:**

    * Go to the **Projects** drop-down at the top right corner and click **Project Settings**.
    * In **Project Settings**, navigate to **Environment**.
    * The following screen is displayed.

    <figure><img src="../.gitbook/assets/image (1347).png" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F8kmqQm963h5jWidjxkFl%252Fimage.png%3Falt%3Dmedia%26token%3D1e8202b1-d3e7-4cf5-80cb-86549577aae9&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b2dd4bc3&#x26;sv=2" alt=""><figcaption></figcaption></figure>
2.  Click **Add** to add a new environment in ReleaseOwl.

    * In the subsequent screen, select the required environments from the list displayed.
    * Select **Source environment** and **Save** the changes.

    <figure><img src="../.gitbook/assets/image (1346).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Only the artifacts from the source are synced to ReleaseOwl.
{% endhint %}

3. The environment gets added to the corresponding project in ReleaseOwl.

<figure><img src="../.gitbook/assets/image (1348).png" alt=""><figcaption></figcaption></figure>

4. Click on the **Users** tab. This tab lists all existing users associated with the project.4
5. Click on the **edit (lock)** icon next to the user for whom you want to manage roles and permissions.

<figure><img src="../.gitbook/assets/image (1349).png" alt=""><figcaption></figcaption></figure>

6. This will open the **Permissions** page for the selected user.

<figure><img src="../.gitbook/assets/image (1352).png" alt=""><figcaption></figcaption></figure>

7. Scroll down to the Environments section.
8. Check the Deploy checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="../.gitbook/assets/image (1351).png" alt=""><figcaption></figcaption></figure>

### **SAC Management and Deployment**

1.  **Sync Packages:**

    * Go to **SAC Management** in the **Build** section and click on **Sync Packages**.

    <figure><img src="../.gitbook/assets/image (1353).png" alt=""><figcaption></figcaption></figure>



* You can see the **Deployment History** by clicking on the **Actions** button and selecting **Deployment History**.

<figure><img src="../.gitbook/assets/image (1354).png" alt=""><figcaption></figcaption></figure>

2. **View Package Details:**

* Click the **Actions** button and select **Import Settings** to view package details.

<figure><img src="../.gitbook/assets/image (44) (1).png" alt=""><figcaption></figcaption></figure>

* Each package has different import settings, and you need to configure the import settings for the required package.

<figure><img src="../.gitbook/assets/image (1355).png" alt=""><figcaption></figcaption></figure>

3. **Change Management:**

* Navigate to the **Change Management** section.
* Go to **User Stories**, click on the **Actions** button, and select **Edit**.

<figure><img src="../.gitbook/assets/image (46) (1).png" alt=""><figcaption></figcaption></figure>

* Click on the **+Add** button to add **SAC Packages**.
* Click on the **Save** button.

<figure><img src="../.gitbook/assets/image (1357).png" alt=""><figcaption></figcaption></figure>

4. **Promote User Story:**

* Click on the **Save** button.
* Click on **Promote** to promote the user story.

<figure><img src="../.gitbook/assets/image (1356).png" alt=""><figcaption></figcaption></figure>

5. **Check Deployment Status:**

* Click on the **Pipeline Activity** to view the deployment status.

<figure><img src="../.gitbook/assets/image (47) (1).png" alt=""><figcaption></figcaption></figure>

* Click the **"Deploy Log"** button to open a pop-up window displaying deployment details.

<figure><img src="../.gitbook/assets/image (48) (1).png" alt=""><figcaption></figcaption></figure>



