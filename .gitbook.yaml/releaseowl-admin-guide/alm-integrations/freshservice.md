# Freshservice

This user guide provides step-by-step instructions to integrate **Freshservice** with the **ReleaseOwl Dashboard**, enabling seamless **ticket management, automation, and real-time visibility** of Freshservice updates within ReleaseOwl.

### Registering Freshservice in ReleaseOwl Dashboard&#x20;

1. Navigate to **Administration** in the ReleaseOwl dashboard.
2. Click on **Credential Manager**.
3. On the **Credential Manager** page, click **Register Credential**.

<figure><img src="../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

4. Fill in the details as follows:

* **Credential Name:** Provide a descriptive name for the credential for easy identification.
* **Credential Type:** Select **Freshservice** from the list.
* **Authentication Type:** Choose **Basic**.
* **API Key:** Enter your Freshservice API key.
* **Password:** Enter "**X"** (as required for basic authentication).
* **Instance URL:** Enter your Freshservice instance URL, e.g., `https://<yourdomain>.freshservice.com`.

5. Click **Save** to complete the registration.

<figure><img src="../../.gitbook/assets/image (1462).png" alt=""><figcaption></figcaption></figure>

### How to Retrieve the API Key in Freshservice

1. Log in to your **Freshservice** account.
2. Click on your **profile icon** (top-right corner) and select **Profile Settings**.

<figure><img src="../../.gitbook/assets/image (1463).png" alt=""><figcaption></figcaption></figure>

3. In the **Profile Settings** page, locate the **API Key** section on the right-hand side.
4. Click **Show API Key**, then copy the displayed key.
5. Paste this API key into the **API Key** field in ReleaseOwl Credential Manager.

<figure><img src="../../.gitbook/assets/image (1464).png" alt=""><figcaption></figcaption></figure>

### **Freshservice Project Integration**

To link a **Freshservice** project with a **ReleaseOwl** project, follow these steps:

**1. Navigate to Project Settings**

* Switch to the required **working project** in **ReleaseOwl**.
* Go to **Project Settings**.
* In **Project Settings**, navigate to **ALM Integrations** and click on **Add**.

<figure><img src="../../.gitbook/assets/image (1465).png" alt=""><figcaption></figcaption></figure>

**2. Fill in the Required Details**

* **Name:** Enter a unique name for the integration.
* **Description (Optional):** Provide a description for reference.
* **External System:** Select **Freshservice** from the dropdown list.
* **Credential:** Select the registered **Freshservice API credential** from the dropdown list.
* **Host URL:** This will automatically populated.&#x20;

3. If you select **Service Requests**, ReleaseOwl will **only sync tickets** categorized as **Service Requests** from Freshservice. you can further **refine** what kind of requests should be synced based on specific criteria by using the Filter option.

<figure><img src="../../.gitbook/assets/image (1466).png" alt=""><figcaption></figcaption></figure>

4. If you select Change Requests, ReleaseOwl will synchronize only the Change Requests from Freshservice. Within the Change Requests section, you can configure this using either a **Filter** or a **View.**
5. **Filter:**
   * To use the **Filter** option, navigate to the **Ticket List** in Freshservice and select the list that displays the created Change Requests. In the URL, locate the **filter ID** (a numeric value) and copy it. Then, paste this ID into the **Filter** field in ReleaseOwl.
6. **View:**

* Similarly, to use the **View** option, navigate to the **Ticket List** in Freshservice, select the saved view that displays your Change Requests, and copy the **view ID** from the URL. Then, paste this ID into the **View** field in ReleaseOwl to complete the configuration.

<figure><img src="../../.gitbook/assets/image (1467).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (885).png" alt=""><figcaption></figcaption></figure>

### **Integrating User Stories from Freshservice to ReleaseOwl**

ReleaseOwl is bidirectional, so the user stories created in Freshservice can be synced with ReleaseOwl and vice-versa.

To integrate user stories from Freshservice, follow these steps:

1. Navigate to the required Project.
2. In **Change Management**, select **User Stories** Menu
3. Click the **Sync User stories** icon.
4. Once the sync is completed, you will get a pop up saying, **User Story Sync completed**.
5. Click **Ok**.

<figure><img src="../../.gitbook/assets/image (1468).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** At the top right, there is a **"Sync History"** button. This button likely provides a log or history of all previous synchronization activities related to user stories.
{% endhint %}

