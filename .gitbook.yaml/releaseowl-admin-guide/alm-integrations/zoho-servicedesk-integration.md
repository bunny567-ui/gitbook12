# Zoho ServiceDesk Integration

This document explains how to connect **Zoho ServiceDesk Plus Cloud** to ReleaseOwl using **OAuth 2.0**. Once connected, ReleaseOwl can read and update ServiceDesk Plus **requests and changes.**

### Prerequisites <a href="#user-content-prerequisites" id="user-content-prerequisites"></a>

* A Zoho account that can open your ServiceDesk Plus portal.
* The ReleaseOwl callback (redirect) URL varies depending on the environment.

### Configure the Zoho API Console <a href="#user-content-part-a--zoho-api-console" id="user-content-part-a--zoho-api-console"></a>

1. Open the[ Zoho API Console ](https://api-console.zoho.in/)and sign in using the Zoho account associated with ServiceDesk Plus.
2. Click **Add Client** in the upper-right corner of the Applications list.

<figure><img src="../../.gitbook/assets/image (2425).png" alt=""><figcaption></figcaption></figure>

3. Select **Server-based Applications**.
4. Click **Create Now** under Server-based Applications.

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

5\. Enter the required client details and configure the application.

| Field                    | Enter                               |
| ------------------------ | ----------------------------------- |
| Client Name              | Enter a name of your choice         |
| Homepage URL             | Enter your ReleaseOwl homepage URL  |
| Authorized Redirect URIs | Enter your ReleaseOwl callback URL  |

{% code overflow="wrap" expandable="true" %}
```
Authorized URL:https://<region>.releaseowl.com/rateloginserver/api/oauth/accesstoken
```
{% endcode %}

<figure><img src="../../.gitbook/assets/image (2426).png" alt=""><figcaption></figcaption></figure>

6. Open the **Client Secret** tab. Use the copy icons to copy the **Client ID** and **Client Secret**. You will need these credentials when configuring the OAuth connection in ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### Set Up OAuth Authentication in ReleaseOwl

1. In ReleaseOwl, navigate to **Administration → Credential Manager**.
2. Click **Register Credential** to create a new credential.

<figure><img src="../../.gitbook/assets/image (2334).png" alt=""><figcaption></figcaption></figure>

3.  Fill in the details as follows:

    | Field               | Value                                                                                                                                                                                                                                       |
    | ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
    | Credential Name     | Enter a name                                                                                                                                                                                                                                |
    | Credential Type     | Zoho Service Desk                                                                                                                                                                                                                           |
    | Scope               | Global                                                                                                                                                                                                                                      |
    | Authentication Type | OAuth2                                                                                                                                                                                                                                      |
    | Client ID           | Paste the Client ID you created in the Zoho Console                                                                                                                                                                                         |
    | Client Secret       | Paste the Client Secret you created in the Zoho Console                                                                                                                                                                                     |
    | Token URL           | `https://accounts.zoho.in/oauth/v2/token`                                                                                                                                                                                                   |
    | Authorization URL   | `https://accounts.zoho.in/oauth/v2/auth`                                                                                                                                                                                                    |
    | OAuth Scope         | SDPOnDemand.requests.READ,SDPOnDemand.changes.READ,SDPOnDemand.projects.READ,SDPOnDemand.releases.READ,SDPOnDemand.setup.READ,SDPOnDemand.requests.UPDATE,SDPOnDemand.changes.UPDATE,SDPOnDemand.requests.CREATE,SDPOnDemand.changes.CREATE |

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

4. After saving the credential, click **Generate Token**. You will be redirected to a Zoho authorization page.&#x20;
5. Select **I allow … to access the above data** and click **Accept**. Once authorization is successful, a success message appears, confirming that the token has been generated successfully.

<div><figure><img src="../../.gitbook/assets/image (2336).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure></div>

#### ReleaseOwl Project Settings

After creating the credential, connect it to a ReleaseOwl project by configuring the integration settings.

1. Open the required project and navigate to its integration settings.
2. Add the **Zoho Service Desk** integration.
3.  Configure the following fields:

    | Field                | Description                                              |
    | -------------------- | -------------------------------------------------------- |
    | Credential           | Select the credential created in the previous section.   |
    | Host URL             | Enter your ServiceDesk Plus portal URL.                  |
    | Filter Configuration | Select the filter to specify which items to synchronize. |
4. Save the configuration to complete the integration setup.

<figure><img src="../../.gitbook/assets/image (2427).png" alt=""><figcaption></figcaption></figure>

#### Choosing what to sync <a href="#user-content-choosing-what-to-sync" id="user-content-choosing-what-to-sync"></a>

The **Board Type** you choose decides which ServiceDesk Plus records ReleaseOwl syncs.

**Board Type = Filter**

ReleaseOwl fetches only the modules you configure. Add a `request` block, a `change` block, or both. Each block is a ServiceDesk Plus `list_info` search, for example:

{% code overflow="wrap" expandable="true" %}
```abap
{
  "request": {
    "list_info": {
      "row_count": 50,
      "start_index": 1,
      "search_criteria": { "field": "status.name", "condition": "is", "value": "Open" }
    }
  },
  "change": {
    "list_info": { "row_count": 50, "start_index": 1 }
  }
}
```
{% endcode %}

ReleaseOwl uses a filter to decide which ServiceDesk Plus requests to sync. The easiest way to get a valid filter is to copy the one ServiceDesk Plus itself uses.

**Copy the filter from ServiceDesk Plus**

1. Log in to ServiceDesk Plus and open **Requests**.
2. Choose the list view you want to sync, for example **Open Requests** or **All Requests**.
3. Press **F12** (or right-click the page → **Inspect**) to open the browser’s developer tools.
4. Open the **Network** tab and click **Fetch/XHR**.
5. Type `requests` in the filter box, then refresh the page (**F5**).
6. In the list, click the call that starts with **`requests?input_data=`**.
7. Open the **Payload** tab. Under **Query String Parameters**, right-click **input\_data** and choose **Copy value**.

<figure><img src="../../.gitbook/assets/image (2386).png" alt=""><figcaption></figcaption></figure>

**Add the filter in ReleaseOwl**

1. In ReleaseOwl, open the integration.
2. Select **Filters** and click **+ Add**.
3. Set **Type** to **Request** and paste the copied value into **Filter**.
4. Click **Save**.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### **Integrating User Stories from Zoho Service Plus to ReleaseOwl**

ReleaseOwl is bidirectional, so the user stories created in Zoho Service Plus can be synced with ReleaseOwl and vice-versa.

To integrate user stories from Zoho Service Plus, follow these steps:

1. Navigate to the required Project.
2. In **Change Management**, select **User Stories** Menu
3. Click the **Sync User stories** icon.

<figure><img src="../../.gitbook/assets/image (2377).png" alt=""><figcaption></figcaption></figure>

4. After synchronization is complete, the user stories will be available in ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (2378).png" alt=""><figcaption></figcaption></figure>

### Zoho ServiceDesk Webhook Configuration

Manual sync brings records in only when you ask. To have ReleaseOwl update automatically whenever a request or change is created or edited, set up a webhook and a trigger in ServiceDesk Plus.

**Step 1: Get the webhook URL from ReleaseOwl**

When you save the integration, ReleaseOwl generates a webhook URL and secret key for it:

```
<ReleaseOwl host>/ratesaptms/webhook/tenant/<tenant>/project/<projectId>/zohodesk/{module}/sync?secretKey=<secretKey>
```

Replace `{module}` with `request` or `change`, depending on which module the webhook is for.

**Step 2: Create the webhook in ServiceDesk Plus**

A webhook enables ZohoServiceDesk Plus to notify ReleaseOwl when a request or change is created or updated, allowing ReleaseOwl to synchronize the information.

1. In ServiceDesk Plus, navigate to **Setup**.

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Under Setup, select **Automation → Custom Actions → Webhooks** and click **New Webhook**.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Configure the following webhook details:

| Field        | Value                                                                                              |
| ------------ | -------------------------------------------------------------------------------------------------- |
| Name         | Enter a name of your choice.                                                                       |
| URL          | Enter the ReleaseOwl webhook URL and replace `{module}` with `request` or `change`, as applicable. |
| Method       | `POST`                                                                                             |
| Content Type | `application/json`                                                                                 |
| Content      | `{"id": "${id}"}`                                                                                  |

4. Save the webhook. Create **one webhook per module** (requests, changes), each with its own  module value. The webhook shows in the Custom Actions list with **Trigger: 0**.

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

### Triggers

1. Go to **Admin → Automation → Triggers** and click **New Trigger**.
2. Under **Trigger Definition**, fill in:

| Field                     | Value                                        |
| ------------------------- | -------------------------------------------- |
| Name                      | Releaseowl Request Sync Trigger              |
| Description               | Push request ID to ReleaseOwl project 948    |
| Trigger applies to        | Requests                                     |
| Execute when a request is | ☑ Created, ☑ Edited (leave Deleted unticked) |
| Execute during            | Any time                                     |
| Enable Trigger            | ☑                                            |

3. Under **Conditions**, select **Without condition**. SDP shows "Actions will be executed on all the requests".

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

4. Under **Actions**, click **Select Custom Actions → Webhook**.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

5. In the **Select Webhook** pop-up, pick your webhook request and click **Select**. The webhook's URL, method and body now show under Actions.
6. Click **Save**. SDP confirms with "Trigger details added".

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note**: Only one enabled trigger should point to the ReleaseOwl webhook. If more than one does, ReleaseOwl gets duplicate calls for every request that is created or edited.
{% endhint %}

**Test the integration**

**Step 1: Create a test request in ServiceDesk Plus**

1. Go to **Requests** and click **New Incident**

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

2. Select a **Requester**, enter a **Subject** and **Description**, and set a **Priority**.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

3. Click **Add Request**. SDP confirms with “Request added” and shows the new request number.

<div><figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure></div>

**Step 2: Check the request in ReleaseOwl**

1. Log in to ReleaseOwl and open your project.
2. Go to **Change Management → User Stories**.
3. In **ALM Integration**, select your ServiceDesk Plus integration.
4. Click the **Refresh** icon (↻).
5. The new request appears as a user story with:
   * **External ID**: the ServiceDesk Plus request ID
   * **Summary**: the request subject
   * **Status**: the current status in SDP (for example, Open)
   * **Type**: Request
6. Click the **External ID** link to open the matching request in ServiceDesk Plus.

<figure><img src="../../.gitbook/assets/image (2428).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Use **Refresh**, not **Sync User Stories**. Sync User Stories pulls data manually, so it can’t tell you whether the webhook is working.
{% endhint %}
