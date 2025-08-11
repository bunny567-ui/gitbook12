# Jira Cloud

This user guide provides step-by-step instructions to integrate Jira with the ReleaseOwl Dashboard, enabling seamless project tracking, automation, and real-time visibility of Jira updates within ReleaseOwl. By following this guide, users can create an OAuth 2.0 integration, configure permissions, register Jira credentials in ReleaseOwl, and establish webhook connections to ensure a smooth data flow between the two platforms.

### 1. Sign in to the Atlassian Developer Account

1\.       Go to the [Atlassian Developer Console](https://developer.atlassian.com/).

2\.       Log in using your Atlassian account credentials.

<figure><img src="../../../.gitbook/assets/image (507).png" alt=""><figcaption></figcaption></figure>

### 2. Create an OAuth 2.0 Integration

1\.       Click on the Developer Console option.

2\.       Click on Create and select OAuth 2.0 Integration from the available options.

<figure><img src="../../../.gitbook/assets/image (508).png" alt=""><figcaption></figcaption></figure>

### 3. Create an App

1. Enter a name for the app that reflects its purpose for Jira.
2. Check the box to agree to the terms and conditions.
3. Click on the Create button to proceed.

<figure><img src="../../../.gitbook/assets/image (509).png" alt=""><figcaption></figcaption></figure>

### 4. Add Permissions

1\.       After the app is created, navigate to the Permissions section.

2\.       Select Jira API and click on the Add button to grant the necessary permissions.

<figure><img src="../../../.gitbook/assets/image (510).png" alt=""><figcaption></figcaption></figure>

### 5. Authorization Configuration

1. Go to the Authorization section.
2. Click on the Add button in the action item to set the authorization type.

<figure><img src="../../../.gitbook/assets/image (511).png" alt=""><figcaption></figcaption></figure>

3. For the Callback URL, enter:\
   [https://na3.releaseowl.com/ratesaptms/api/accesstoken](https://na3.releaseowl.com/ratesaptms/api/accesstoken)
4. &#x20;Click on Save Changes.

<figure><img src="../../../.gitbook/assets/image (512).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** In the OAuth framework, there are refresh tokens and access tokens. When the access token expires, a refresh token is used to obtain a new access token. The configuration must be set to send the refresh token when required. Since local URLs are not recognized due to intra-network restrictions, the callback URL uses the ReleaseOwl server (na3.releaseowl.com) to handle token exchange.
{% endhint %}

### 6. Copy ClientID and Secret

1. Go to Settings in the Developer Console.
2. Copy the Client ID and Client Secret for later use when registering Jira in the ReleaseOwl Dashboard.

<figure><img src="../../../.gitbook/assets/image (25) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **7. Registering Jira in ReleaseOwl Dashboard**

To integrate Jira with ReleaseOwl for issue tracking and traceability, follow the steps below to register Jira credentials and set up project integration.

#### **A. Registering Jira using OAuth2 Authentication**

1. Go to  the ReleaseOwl Dashboard.
2. Navigate to Administration, then select Credential Manager.
3. Click on Register Credential.

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

4. Fill out the credential form with the following details:

* **Credential Name:** Enter your preferred name for the credential.
* **Credential Type**: Jira
* **Authentication Type**: Select the authentication type as theOAuth2
* **Client ID and Client Secret:** Paste the Client ID and Client Secret obtained from the OAuth2 integration you created in the Atlassian Developer Console.
* **Jira URL**:  [https://saparate.atlassian.net](https://saparate.atlassian.net)
* **Proxy Type**: Select None

5. Click **Save** to register the credential.

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### **B. Registering Jira using Basic Authentication**

**Steps to Generate API Token in Jira**

1. Log in to your Jira account.
2. Go to Account Settings, then select Security.

<figure><img src="../../../.gitbook/assets/image (28) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Click on **Create and manage API tokens**.

<figure><img src="../../../.gitbook/assets/image (29) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Click Create API Token, provide a token name, and click **Create**.

<figure><img src="../../../.gitbook/assets/image (30) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. Copy the generated **API** token.

<figure><img src="../../../.gitbook/assets/image (31) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Register API Token in ReleaseOwl**

1. Open the ReleaseOwl Dashboard.
2. Navigate to Administration, then select **Credential Manager**.
3. Click on **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

4. Fill in the form with the following details:

* **Credential Name:** Enter your preferred name for the credential.
* Credential Type: Jira
* **Authentication Type:** Basic
* **Username:** Your Jira account username (usually an email address)
* **Password or API Token:** Paste the copied API token
* **Jira URL:**  [https://saparate.atlassian.net](https://saparate.atlassian.net)
* **Proxy Type**: Select None

5. Click Save to register the credential.

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### 8. Jira Project Integration&#x20;

To link a Jira project with a ReleaseOwl project, follow these steps:

**1. Navigate to Project Settings**

1. Switch to the required working project in **ReleaseOwl**.
2. Go to **Project Settings**.
3. In the **Project Settings**, navigate to **ALM Integrations** and click on **Add**.

#### **2. Fill in the Required Details**

* **Name**: Enter a unique name for the integration.
* **Description**: (Optional) Provide a description for reference.
* **External System**: Select **Jira** from the dropdown list.
* **Credential**: Select the registered Jira credential from the dropdown list.
* **Host URL**: The Jira server URL (e.g., `https://saparate.atlassian.net`).

<figure><img src="../../../.gitbook/assets/image (1094).png" alt=""><figcaption></figcaption></figure>

#### **3. Select Hosting Type**

Under **Hosting Type**, choose **On-Premise** if your Jira instance is hosted on a private server rather than Atlassian’s cloud. Choose **Cloud** if your Jira instance is hosted on Atlassian’s cloud platform. You can then choose from the following options:

**A. Using Boards**

* **Select Boards** if you want to sync issues based on a specific Jira board.
* **External Project**: Select the Jira project you want to link with ReleaseOwl from the pop-up list.
* **Board**: Select the appropriate **Scrum** or **Kanban** board for the project.
* **Webhook URL**:
  * This URL is autogenerated by ReleaseOwl.
  * The Webhook URL is used to capture and sync events from Jira to ReleaseOwl.
* **Webhook Request URL for Automation Rule** :
  * This URL is autogenerated by ReleaseOwl.
* **Disable writing of comments/ notes:** You can turn off comments within ALM Integration.
* After entering all the integration details, click on the **Save** button.&#x20;

<figure><img src="../../../.gitbook/assets/image (34) (1).png" alt=""><figcaption></figcaption></figure>

* Once saved, the integration will appear in the list, and if the **"Default Integration"** checkbox was selected, it will be marked as **Default**. This means the system will automatically use this integration unless another one is specified.

<figure><img src="../../../.gitbook/assets/image (35) (1).png" alt=""><figcaption></figcaption></figure>

**B. Using Filters**

* **Select Filters:** Use this option if you want to sync issues based on Jira's saved filters instead of boards or JQL querie&#x73;**. View all filters** available on the Jira board will also be visible in the user stories when filters are chosen.
* **External Project**: Choose the Jira project you want to link with ReleaseOwl.
*   **Filters**:

    * Click on the dropdown or the filter selection icon.
    * A list of available Jira filters will be displayed.
    * Select the desired **saved filter** from Jira.
    * Ensure the selected filter has proper permissions and is shared with the required users.

    <figure><img src="../../../.gitbook/assets/image (36) (1).png" alt=""><figcaption></figcaption></figure>

**C. Using JQL (Jira Query Language)**

* Select **JQL**, a powerful tool to fetch the details in Jira.
* **External Project**: Choose the Jira project you want to link with ReleaseOwl.
*   **JQL Query**:

    * Create a JQL query in Jira that retrieves the required issues.
    * Copy and paste the JQL query into ReleaseOwl.

    <figure><img src="../../../.gitbook/assets/image (839).png" alt=""><figcaption></figcaption></figure>

### 9. How to Configure Webhook URL

1. Log in to your Jira account.
2. Go to Settings and click on System.

<figure><img src="../../../.gitbook/assets/image (516).png" alt=""><figcaption></figcaption></figure>

3. In the System section, navigate to General Configuration and click on Webhooks.

<figure><img src="../../../.gitbook/assets/image (517).png" alt=""><figcaption></figcaption></figure>

4. This will take you to the webhook configuration page.

<figure><img src="../../../.gitbook/assets/image (518).png" alt=""><figcaption></figcaption></figure>

5. Copy the **Webhook URL** that was generated in ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (1095).png" alt=""><figcaption></figcaption></figure>

5. Paste the copied URL in the Webhook configuration page in Jira.

<figure><img src="../../../.gitbook/assets/image (515).png" alt=""><figcaption></figcaption></figure>

7. Select the issue-related events that you want to track for your project (e.g., story creation, updates, etc.).

<figure><img src="../../../.gitbook/assets/image (514).png" alt=""><figcaption></figcaption></figure>

8. After entering all the details, you can enable or disable the webhook in the status section.

<figure><img src="../../../.gitbook/assets/image (513).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Further information on registering / configuring webhooks in JIRA can be found @ [https://developer.atlassian.com/server/jira/platform/webhooks/](https://developer.atlassian.com/server/jira/platform/webhooks/)
{% endhint %}

### **Integrating User Stories from Jira to ReleaseOwl**

ReleaseOwl is bidirectional, so the user stories created in Jira can be synced with ReleaseOwl and vice-versa.

To integrate user stories from Jira, follow these steps:

1. Navigate to the required Project.
2. In **Change Management**, select **User Stories** Menu
3. Click the **Sync User stories** icon.

<figure><img src="../../../.gitbook/assets/image (26) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Once the sync is completed, you will get a pop up saying, **User Story Sync completed**.
5. Click **Ok**.

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
