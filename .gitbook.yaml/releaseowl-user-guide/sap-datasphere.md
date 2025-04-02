# SAP Datasphere

This document outlines the step-by-step process of registering SAP Datasphere within ReleaseOwl, managing environments, configuring user permissions, handling package synchronization, and executing deployment processes efficiently.

### Credential Registration <a href="#pdf-page-dk8rbzgxugve408ig5ly-credential-registration" id="pdf-page-dk8rbzgxugve408ig5ly-credential-registration"></a>

1. Admin users can switch to the **Administration View** to access the **Credential Manager**.
2. Click the **Credential Manager** menu option on the left-hand pane to view the list of registered credentials.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FrsE89fY2Fhmfp0N8AAUb%252Fimage.png%3Falt%3Dmedia%26token%3Ddafa81c1-3d58-4875-a59d-b7d371d992cc&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a8c7ef80&#x26;sv=2" alt=""><figcaption></figcaption></figure>

3. To add a new credential, click **Register Credential** available on the right-hand panel, and then click on the **Register Credential** button.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FOlQXbRau9NAUz064D5V8%252Fimage.png%3Falt%3Dmedia%26token%3D403b126d-ca63-4a3f-ab49-49cb64c161bd&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=cb343d62&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **SAP Datasphere**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FTjFjanAckhHaFLSjoSCg%252Fimage.png%3Falt%3Dmedia%26token%3D6c77f749-fd12-435b-97f5-a820d3dd1f55&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e5811f0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. For the Client ID, Secret, Token URL, and Authorization URL:

* Go to your **SAP  Datasphere** and navigate to **Administration**

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

* Click on **App Integration** for the **OAuth Clients**.
* Click on **Add a New OAuth Client**.
* Copy the **Client ID, Secret, Token URL,** and **Authorization URL**.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### **To Register SAP Datasphere:** <a href="#pdf-page-dk8rbzgxugve408ig5ly-to-register-sap-datasphere" id="pdf-page-dk8rbzgxugve408ig5ly-to-register-sap-datasphere"></a>

1. In Environments, go to **SAP Datasphere**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FWkFs3jmXpWieYvN0tj1S%252Fimage.png%3Falt%3Dmedia%26token%3D9a93900c-197f-4428-8b0c-d2ac7a4122f9&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d42f8345&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. Click **Register SAP Datasphere Environment**. The following screen is displayed:

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FlNVSBBPnxxhchH9jF9Fj%252Fimage.png%3Falt%3Dmedia%26token%3D38c504ad-185b-4a2d-b181-e976f43184cf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=78065561&#x26;sv=2" alt=""><figcaption></figcaption></figure>

3. **Fill in the required details:**

* **Name**: Enter a name for your reference.
* **OAuth Credentials**: Select the SAP Datasphere OAuth Credentials registered with ReleaseOwl.
* **Host URL**: Enter the host URL of the SAP Datasphere environment.
* **Environment Type**: Select the environment type you are registering (e.g., Dev or QA, etc.).

4. Click **Save** to register the environment.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fs4FGREcgPUQ3btRpxTuw%252Fimage.png%3Falt%3Dmedia%26token%3D2a366412-12dd-4039-a64e-68a2cf1f06c8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=7b28694c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. The registered environments are displayed.
6. Click on the required environment to view the details.
7. Click the **edit icon** to edit the registered SAC Environment.
8. Click the **delete icon** to delete the required environment.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fob4rW5nGU4ydmZF1hzj5%252Fimage.png%3Falt%3Dmedia%26token%3D2e54e681-ef6c-4519-b5d0-ba2a2b18c8e7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=69251e71&#x26;sv=2" alt=""><figcaption></figcaption></figure>

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

    <figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
2.  **View Package Details:**

    * Click the **Actions** button and select **Import Settings** to view package details.

    <figure><img src="../.gitbook/assets/image (975).png" alt=""><figcaption></figcaption></figure>



    * Each package has different import settings, and you need to configure the import settings for the required package.

    <figure><img src="../.gitbook/assets/image (976).png" alt=""><figcaption></figcaption></figure>
3.  **Change Management:**

    * Navigate to the **Change Management** section.
    * Go to **User Stories**, click on the **Actions** button, and select **Edit**.

    <figure><img src="../.gitbook/assets/image (980).png" alt=""><figcaption></figcaption></figure>

    * Click on the **+Add** button to add **SAP Datasphere**.
    * Click on the **Save** button.

    <figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>


4.  **Promote User Story:**

    * Click on the **Save** button.
    * Click on **Promote** to promote the user story.

    <figure><img src="../.gitbook/assets/image (978).png" alt=""><figcaption></figcaption></figure>
5.  **Check Deployment Status:**

    * Click on the **Pipeline Activity** to view the deployment status.

    <figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>



* Click on the **"Deploy Log"** button.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

* A pop-up window titled **SAP Datasphere Cloud Deploy Log** will appear, displaying deployment details.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
