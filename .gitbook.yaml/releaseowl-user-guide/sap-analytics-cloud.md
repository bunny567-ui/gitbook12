# SAP Analytics Cloud

SAP Analytics Cloud (SAC) is a cloud-based business intelligence (BI) and analytics platform that integrates data visualization, planning, and predictive analytics.

## Credential Registration

1. Admin users can switch to the **Administration View** to access the **Credential Manager**.
2. Click the **Credential Manager** menu option on the left-hand pane to view the list of registered credentials.

<figure><img src="../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>

3. To add a new credential, click **Register Credential**, available on the right-hand panel.

* The following screen will be displayed.
* Click on the **Register Credential** button.

<figure><img src="../.gitbook/assets/image (86).png" alt=""><figcaption></figcaption></figure>

4. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **SAP Analytics Cloud**.

<figure><img src="../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>

5. For the Client ID, Secret, Token URL, and Authorization URL:

* Go to your **SAP Analytics Cloud** and navigate to **Administration**.

<figure><img src="../.gitbook/assets/image (87).png" alt=""><figcaption></figcaption></figure>

* Click on **App Information** for the **OAuth Clients**.
* Click on **Add a New OAuth Client**.
* Copy the **Client ID, Secret, Token URL,** and **Authorization URL**.

<figure><img src="../.gitbook/assets/image (88).png" alt=""><figcaption></figcaption></figure>

## **To Register SAC Environment:**

1.  In Environments, go to **SAP Analytics Cloud**.

    <figure><img src="../.gitbook/assets/image (89).png" alt=""><figcaption></figcaption></figure>


2.  Click **Register SAC Environment**. The following screen is displayed:

    <figure><img src="../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>
3.  **Fill in the required details:**

    * **Name**: Enter a name for your reference.
    * **Landscape**: Select the Landscape in use.
    * **OAuth Credentials**: Select the SAC OAuth Credentials registered with ReleaseOwl.
    * **Host URL**: Enter the host URL of the SAP Analytics Cloud environment.
    * **Environment Type**: Select the environment type you are registering (e.g., Dev or QA, etc.).

    <figure><img src="../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure>
4. **Click Save** to register the environment.
5. Similarly, register the target SAC environment as follows:

<figure><img src="../.gitbook/assets/image (93).png" alt=""><figcaption></figcaption></figure>

6. The registered environments are displayed.

<figure><img src="../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

7. Click on the required environment to view the details.
8. Click the **edit icon** to edit the registered SAC Environment.
9. Click the **delete icon** to delete the required environment.

## **Adding SAC Environments to the Project:**

The SAC environments must be registered in **Project Settings** in ReleaseOwl.

1.  **To register SAC environment:**

    * Go to the **Projects** drop-down at the top right corner and click **Project Settings**.
    * In **Project Settings**, navigate to **Environment**.
    * The following screen is displayed.

    <figure><img src="../.gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure>
2.  **Click Add** to add a new environment in ReleaseOwl.

    * In the subsequent screen, select the required environments from the list displayed.

    <figure><img src="../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>

    * Select **Source environment** and **Save** the changes.

{% hint style="info" %}
**Note:** Only the artifacts from the source are synced to ReleaseOwl.
{% endhint %}

* The environment gets added to the corresponding project in ReleaseOwl.

<figure><img src="../.gitbook/assets/image (97).png" alt=""><figcaption></figcaption></figure>

* **Click Permissions** (under the **Users** tab in Project Settings) to add users that can access (read or deploy to) the registered SAC environment.

<figure><img src="../.gitbook/assets/image (98).png" alt=""><figcaption></figcaption></figure>

* Click **Permissions**. The roles assigned to the selected user are displayed.

<figure><img src="../.gitbook/assets/image (99).png" alt=""><figcaption></figcaption></figure>

* On clicking **Permissions** in the above screen, deployment permission can be granted to the given user.

<figure><img src="../.gitbook/assets/image (102).png" alt=""><figcaption></figcaption></figure>

**SAC Management and Deployment**

1.  **Sync Packages:**

    * Go to **SAC Management** in the **Build** section and click on **Sync Packages**.

    <figure><img src="../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

    * You can see the **Deployment History** by clicking on the **Actions** button and selecting **Deployment History**.

    <figure><img src="../.gitbook/assets/image (112).png" alt=""><figcaption></figcaption></figure>
2.  **View Package Details:**

    * Click the **Actions** button and select **Import Settings** to view package details.

    <figure><img src="../.gitbook/assets/image (113).png" alt=""><figcaption></figcaption></figure>

    * Each package has different import settings, and you need to configure the import settings for the required package.

    <figure><img src="../.gitbook/assets/image (114).png" alt=""><figcaption></figcaption></figure>
3.  **Change Management:**

    * Navigate to the **Change Management** section.
    * Go to **User Stories**, click on the **Actions** button, and select **Edit**.

    <figure><img src="../.gitbook/assets/image (118).png" alt=""><figcaption></figcaption></figure>

    * Click on the **+Add** button to add **SAC Packages**.
    * Click on the **Save** button.

    <figure><img src="../.gitbook/assets/image (115).png" alt=""><figcaption></figcaption></figure>
4.  **Promote User Story:**

    * Click on the **Save** button.
    * Click on **Promote** to promote the user story.

    <figure><img src="../.gitbook/assets/image (116).png" alt=""><figcaption></figcaption></figure>
5.  **Check Deployment Status:**

    * Click on the **Pipeline Activity** to view the deployment status.

    <figure><img src="../.gitbook/assets/image (120).png" alt=""><figcaption></figcaption></figure>

    * Click on the **Deploy Logs** to view the deployment status of the button.

    <figure><img src="../.gitbook/assets/image (119).png" alt=""><figcaption></figcaption></figure>

