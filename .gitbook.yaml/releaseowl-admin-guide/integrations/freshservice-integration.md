# Freshservice Integration

This user guide provides step-by-step instructions to integrate **Freshservice** with the **ReleaseOwl Dashboard**, enabling seamless **ticket management, automation, and real-time visibility** of Freshservice updates within ReleaseOwl.

### Registering Freshservice in ReleaseOwl Dashboard&#x20;

* In Administration, go to **Credential Manager.**
* On the page displayed, click on the **Register Credential** button.

<figure><img src="../../.gitbook/assets/image (879).png" alt=""><figcaption></figcaption></figure>

3. Fill in the necessary details as follows:&#x20;

* **Credential Name**: Enter a name for the credential for your reference.
* **Credential Type**: Choose Freshservice as the credential type.&#x20;
* &#x20;**Authentication Type**: For authentication type, choose Basic.&#x20;
* &#x20;**API Key**: Enter your Freshservice API key.
* &#x20;**Password**:  Enter the associated password.
* **Instance URL**: Enter your Freshservice instance URL (e.g., https://\<yourdomain.freshservice.com>).

5. Click on the **Save** button.

<figure><img src="../../.gitbook/assets/image (878).png" alt=""><figcaption></figcaption></figure>

**Creating a Credential in Freshservice**&#x20;

&#x20;1\. Navigate to Admin → Automation & Productivity → Credentials.

<figure><img src="../../.gitbook/assets/image (880).png" alt=""><figcaption></figcaption></figure>

2. Click on **New Credential** .

<figure><img src="../../.gitbook/assets/image (881).png" alt=""><figcaption></figcaption></figure>

3. Freshservice API key authentication can be achieved by using **basic auth** with the following values.

Username: **\<API key>**

Password: **x**

<figure><img src="../../.gitbook/assets/image (883).png" alt=""><figcaption></figcaption></figure>

### **Freshservice Project Integration**

To link a **Freshservice** project with a **ReleaseOwl** project, follow these steps:

**1. Navigate to Project Settings**

* Switch to the required **working project** in **ReleaseOwl**.
* Go to **Project Settings**.
* In **Project Settings**, navigate to **ALM Integrations** and click on **Add**.

**2. Fill in the Required Details**

* **Name:** Enter a unique name for the integration.
* **Description (Optional):** Provide a description for reference.
* **External System:** Select **Freshservice** from the dropdown list.
* **Credential:** Select the registered **Freshservice API credential** from the dropdown list.
* **Host URL:** Enter the **Freshservice instance URL** (e.g., `https://yourcompany.freshservice.com`)
* If you select **Service Requests**, ReleaseOwl will **only sync tickets** categorized as **Service Requests** from Freshservice. you can further **refine** what kind of requests should be synced based on specific criteria by using the Filter option.

<figure><img src="../../.gitbook/assets/image (884).png" alt=""><figcaption></figcaption></figure>

If you select **Change Requests**, ReleaseOwl will **only sync Change Requests** from Freshservice. In the **Change Requests** section, you have two options:

1. **Filter:**
   * This allows you to define specific criteria to limit which change requests should be considered.
2. **View:**

* This could be an option to **select a pre-defined view** from Freshservice.

<figure><img src="../../.gitbook/assets/image (885).png" alt=""><figcaption></figcaption></figure>

### **Integrating User Stories from Freshservice to ReleaseOwl**

ReleaseOwl is bidirectional, so the user stories created in Freshservice can be synced with ReleaseOwl and vice-versa.

To integrate user stories from Freshservice, follow these steps:

1. Navigate to the required Project.
2. In **Change Management**, select **User Stories** Menu
3. Click the **Sync User stories** icon.
4. Once the sync is completed, you will get a pop up saying, **User Story Sync completed**.
5. Click **Ok**.

<figure><img src="../../.gitbook/assets/image (27) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** At the top right, there is a **"Sync History"** button. This button likely provides a log or history of all previous synchronization activities related to user stories.
{% endhint %}
