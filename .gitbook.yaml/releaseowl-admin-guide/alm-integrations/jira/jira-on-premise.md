# Jira On-Premise

This guide provides detailed instructions for integrating Jira with ReleaseOwl to streamline user story management and automation. After successful configuration, ReleaseOwl automatically fetches **Projects**, **Sprints**, and **User Stories** from your Jira instance based on the settings you define.

To enable continuous, real-time synchronization of User Stories, Jira must be configured with appropriate **Webhooks** or **Automation Rules**. These configurations ensure that ReleaseOwl receives updates instantly whenever changes occur in Jira.

### **1. Jira Environment & Connectivity Requirements**

Ensure that the following prerequisites are met before configuring the integration:

* **Jira URL is reachable** from ReleaseOwl
* **Basic Authentication** is enabled
* **REST API endpoints** are accessible
* If Jira uses an **IP Allowlist**, ensure ReleaseOwl’s IP/domain is added to the allowed list

### **2. Required Jira Global Permissions**

The Jira user account configured in ReleaseOwl must have the following permissions:

* **Browse Users**
* **Create Shared Objects** (optional, but recommended for shared filters and boards)

### **3. Register Jira On-Premise Credential ( Basic Authentication)**

Follow the steps below to register your Jira credentials in ReleaseOwl:

1. Go to  the ReleaseOwl Dashboard.
2. Navigate to **Administration**, then select **Credential Manager**.
3. Click on **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Fill out the credential form with the following details:

* **Credential Name:** Enter a preferred name for this credential.
* **Credential Type:** Jira
* **Authentication Type:** Basic
* **Scope** – Select the scope of the credential:
  * **Global** – Visible to all users.
  * **Private** – Visible only to the user who created it.
* **Username:** Provide the username associated with the credential (e.g., Jira account)
* **Password/API Token**: Enter the password or API token for authentication with the chosen system.
* **Jira URL:** Paste your local or organization-specific Jira URL
* **Proxy Type:** None
* **Hosting Type:** Choose **On-Premise**.

5. Click **Save** to complete the credential registration.

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Do not paste the Bearer Token in the Password/API field under Basic Authentication, as it will not work. Always select **Bearer Token** as the authentication type.
{% endhint %}

### **4. Register Jira On-Premise Credential (OAuth Authentication)**

Follow the steps below to register your Jira credentials in ReleaseOwl:

1. Select **Applications** from the Jira administration menu.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. In the **Applications** section, click **Application Links**, then click **Create link**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. For **Application type**, select **External Application**.
4. For **Direction**, select **Incoming**, and then click **Continue**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. Under _**Application Permissions**_, select only _**Admin**_**&#x20;permissions**.
6. For the **Redirect URL**, enter: [https://na3.releaseowl.com/rateloginserver/api/jira/accesstoken](https://na3.releaseowl.com/rateloginserver/api/jira/accesstoken)
7. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

8. After saving, copy the **Client ID** and **Client Secret** for use in ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Registering Jira in ReleaseOwl Dashboard**

To integrate Jira with ReleaseOwl for issue tracking and traceability, follow the steps below to register Jira credentials and set up project integration.

1. Go to  the ReleaseOwl Dashboard.
2. Navigate to **Administration**, then select **Credential Manager**.
3. Click on **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Fill out the credential form with the following details:

* **Credential Name:** Enter your preferred name for the credential.
* **Credential Type**: Jira
* **Authentication Type**: Select the authentication type as theOAuth2
* **Scope** – Select the scope of the credential:
  * **Global** – Visible to all users.
  * **Private** – Visible only to the user who created it.
* **Client ID and Client Secret:** Paste the Client ID and Client Secret obtained from the OAuth2 integration you created in the Atlassian Developer Console.
* **Jira URL**:  Paste your local or organization-specific Jira URL
* **Proxy Type**: Select None
* **Hosting Type**: Choose **On-Premise.**

5. Click **Save** to register the credential.

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

### **5. Register Jira On-Premise Credential ( Bearer Token)**

* Log in to your Jira account.
* Navigate to your **Profile** in Jira.

<figure><img src="../../../.gitbook/assets/image (1689).png" alt=""><figcaption></figcaption></figure>

* Click on **Create Token**.

<figure><img src="../../../.gitbook/assets/image (1690).png" alt=""><figcaption></figcaption></figure>

* Provide the required details (such as token name and expiration, if applicable).
* Click **Create** to generate the token.

<figure><img src="../../../.gitbook/assets/image (1691).png" alt=""><figcaption></figcaption></figure>

* Copy the generated **Bearer Token** for use in ReleaseOwl credential configuration

<figure><img src="../../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>

#### Jira Bearer Token Integration with ReleaseOwl

To integrate Jira with ReleaseOwl for issue tracking and traceability, follow the steps below to register Jira credentials and set up project integration.

1. Go to  the ReleaseOwl Dashboard.
2. Navigate to **Administration**, then select **Credential Manager**.
3. Click on **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Fill out the credential form with the following details:

* **Credential Name:** Enter your preferred name for the credential.
* **Credential Type**: Jira
* **Authentication Type**: Select **Bearer Token**.
* **Scope** – Select the scope of the credential:
  * **Global** – Visible to all users.
  * **Private** – Visible only to the user who created it.
* **Token:** Paste the copied **Bearer Token**.&#x20;
* **Jira URL**:  Paste your local or organization-specific Jira URL
* **Proxy Type**: Select **None**

5. Click **Save** to register the credential.

<figure><img src="../../../.gitbook/assets/image (1688).png" alt=""><figcaption></figcaption></figure>

## 6. Proxy Type : SAP Cloud Connector

When the Proxy Type is selected as **SAP Cloud Connector** for Jira On-Premise integration, you need to follow the steps below:

#### **A. Configure Destination in SAP BTP**

1. Go to the SAP BTP Cockpit.
2. Navigate to **Subaccount → Connectivity → Destinations**.
3. Click on **Create** → **From Scratch**.
4. Enter the destination details as shown:
   * **Name**: Enter a name of your choice (e.g., `JIRA_ONPREM`)
   * **Type**: Select **HTTP**
   * **URL**: Provide the Jira On-Premise endpoint URL or virtual host (e.g., `http://<host>:<port>`)
   * **Proxy Type**: Select **OnPremise**
   * **Authentication**: Select **BasicAuthentication**
   * **User**: Enter the Jira On-Premise username
   * **Password**: Enter the corresponding password or API token
   * **Location ID**: Enter the Location ID configured in SAP Cloud Connector&#x20;
5. Click on "**Create**".
6. After creating, click on **Check Connection** to validate the setup.

<figure><img src="../../../.gitbook/assets/image (1788).png" alt=""><figcaption></figcaption></figure>

#### **B. Configure SAP Cloud Connector**

**1. Navigate to Cloud To On-Premise**

* Open SAP Cloud Connector
* Select your Subaccount
* Click **Cloud To On-Premise**

<figure><img src="../../../.gitbook/assets/image (1778).png" alt=""><figcaption></figcaption></figure>

**2. Add System Mapping**

* Click **“+” (Add)**

**3. Back-end Type**

* Select **Non-SAP System**
* Click **Next**

<figure><img src="../../../.gitbook/assets/image (1779).png" alt=""><figcaption></figcaption></figure>

**4. Protocol**

* Select **HTTP / HTTPS** (Recommended: HTTPS)
* Click **Next**

<figure><img src="../../../.gitbook/assets/image (1780).png" alt=""><figcaption></figcaption></figure>

#### **5. Internal System Details**

* **Internal Host**: Specify the fully qualified domain name (FQDN) or IP address of the Jira On-Premise system (or the public/ngrok endpoint if used).
* **Internal Port**: Specify the port on which the Jira application is running (e.g., `443` for HTTPS, `8080` for HTTP). This must correspond to the actual backend service port and **not necessarily the port defined in SAP BTP Destination**.
* Ensure that the internal host and port are **reachable from the host where SAP Cloud Connector is installed**.

<figure><img src="../../../.gitbook/assets/image (1781).png" alt=""><figcaption></figcaption></figure>

#### **6. Virtual Host Configuration**

* **Virtual Host**: Enter virtual host from the BTP tenant (e.g., `jira_ro.com`)
* **Virtual Port**: Enter port (e.g., `443`). Must match the **Destination URL** in SAP BTP

<figure><img src="../../../.gitbook/assets/image (1782).png" alt=""><figcaption></figcaption></figure>

#### **7. Principal Type**

* **Principal Type** defines how authentication is handled between SAP BTP and the On-Premise system via SAP Cloud Connector.
* Select **X.509 Certificate (Advanced)** to enable certificate-based authentication.

<figure><img src="../../../.gitbook/assets/image (1783).png" alt=""><figcaption></figcaption></figure>

**8. Complete System Mapping**

After maintaining all required configuration details (Protocol, Internal Host, and Virtual Host):

* Click on **“Check Internal Host”** to validate connectivity from SAP Cloud Connector to the On-Premise system.  Ensure that the internal host is **reachable** before proceeding.
* Once the validation is successful, click on **Finish** to complete the system mapping.

<figure><img src="../../../.gitbook/assets/image (1784).png" alt=""><figcaption></figcaption></figure>

**9. Configure Access Control and Resources**

After completing the system mapping, the entry will be added under the **Access Control** tab in SAP Cloud Connector.

**Add Resource Configuration**

1. Select the newly created system mapping.
2. Navigate to the **Resources** section.
3. Click on **Add** to define a resource.

**Maintain Resource Details**

* **URL Path**: Enter `/`This exposes the **entire application** (all endpoints) of the Jira On-Premise system.
* **Access Policy**: Select **Path and All Sub-Paths**
* Click on **Save** to apply the resource configuration.

<figure><img src="../../../.gitbook/assets/image (1785).png" alt=""><figcaption></figcaption></figure>

* The resource will be added under the mapping.
* The system status should remain **Reachable (Green)**.
* SAP BTP can now access all endpoints of the On-Premise Jira system via the defined virtual host

<figure><img src="../../../.gitbook/assets/image (1786).png" alt=""><figcaption></figcaption></figure>

### Jira Integration via SAP Cloud Connector with ReleaseOwl

To integrate Jira with ReleaseOwl using **SAP Cloud Connector** as the proxy type, follow the steps below:

#### Step 1: Configure SAP Cloud Environment Credentials

1. Log in to the ReleaseOwl Dashboard.
2. Navigate to **Administration** → **Credential Manager**.
3. Click **Register Credential**.

Provide the following details:

* **Credential Type:** Select **SAP Cloud Environment**.
* **Authentication Type:** Select **Basic Authentication**.
* **Username:** Enter the username configured for SAP BTP credentials.
* **Password:** Enter the corresponding password for the SAP BTP credential.

4. Click **Save** to complete the SAP Cloud Environment credential configuration.

<figure><img src="../../../.gitbook/assets/image (1795).png" alt=""><figcaption></figcaption></figure>

#### Step 2: Configure Jira Credentials

1. Navigate to **Administration** → **Credential Manager**.
2. Click **Register Credential**.

Fill out the credential form with the following details:

* **Credential Name:** Enter a preferred name for the credential.
* **Credential Type:** Select **Jira**.
* **Scope:** Choose the required scope:
  * **Global:** Visible to all users
  * **Private:** Visible only to the user who created it
* **Proxy Type:** Select **SAP Cloud Connector**.
* **Proxy URL:** Enter your ReleaseOwl tenant URL.
* **Destination:** Select the destination created in SAP Business Technology Platform.
* **SAP Cloud Credentials:** Select the SAP Cloud credentials configured in Step 1.
* **Hosting Type:** Select **On-Premise**.

3. Click **Save** to register the Jira credential.

<figure><img src="../../../.gitbook/assets/image (1796).png" alt=""><figcaption></figcaption></figure>

## **Jira Project Integration**

To link a Jira project with a ReleaseOwl project, follow the steps below:

### **1. Navigate to Project Settings**

* Switch to the required working project in ReleaseOwl.
* Go to **Project Settings**.
* In Project Settings, navigate to **ALM Integrations** and click **Add**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **2. Fill in the Required Details**

* **Name:** Enter a unique integration name.
* **Description:** (Optional) Add a relevant description.
* **External System:** Select Jira.
* **Credential:** Choose the registered Jira credential.
* **Host URL:** Jira Server URL (e.g., [_https://jira-dev.releaseowl.com/_](https://jira-dev.releaseowl.com/)).

### **3. Select Hosting Type**

* Choose **On-Premise** if your Jira runs on a private server.
* Choose **Cloud** if your Jira instance is hosted on Atlassian Cloud.

### **4. Select External Project**

* Choose the Jira project from the pop-up list.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **A. Using Boards**

* Select **Boards** to sync issues using a specific Jira board.
* **Board:** Choose the required Scrum or Kanban board.
* Click **Save**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Once saved, the integration appears in the list. If **Default Integration** is selected, it will be used by default.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **B. Using Filters**

* Select **Filters** to sync issues using Jira’s saved filters.
* All available filters that user has permission will be displayed.
* Choose the desired filter.
* Ensure the filter has proper permissions and is shared with required users.

#### **C. Using JQL (Jira Query Language)**

* Select **JQL** to fetch issues using advanced queries.
* Create a JQL query in Jira.
* Copy and paste the query into ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Note**

* **Webhook URL:** Auto-generated by ReleaseOwl and used to capture and sync Jira events.
* **Webhook Request URL for Automation Rule:** Also auto-generated by ReleaseOwl.
* **Disable Writing of Comments/Notes:** An optional toggle that allows you to control whether comments or notes are automatically added.

## **Configuring the Webhook URL**

ReleaseOwl supports automatic synchronization of user story changes made in Jira through webhooks.

1. Log in to your Jira account.
2. Go to **Settings → System → WebHooks**.

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Copy the Webhook URL generated in ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Paste it in the **URL** field on the Jira WebHook configuration page.

<figure><img src="../../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. In the events section, instead of all events it is recommended to add filter condition for Project.

<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. Select the issue-related events that you want to track for your project (e.g., story creation, updates, etc.).
7. After entering all the details, you can enable or disable the webhook in the status section.&#x20;

<figure><img src="../../../.gitbook/assets/image (13) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

