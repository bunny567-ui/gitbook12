# Zoho ServiceDesk Integration

This document explains how to connect **Zoho ServiceDesk Plus Cloud** to ReleaseOwl using **OAuth 2.0**. Once connected, ReleaseOwl can read and update ServiceDesk Plus **requests, changes and problems**.

### Prerequisites <a href="#user-content-prerequisites" id="user-content-prerequisites"></a>

* A Zoho account that can open your ServiceDesk Plus portal.
*   The ReleaseOwl callback (redirect) URL:

    <pre data-overflow="wrap"><code>https://na2.releaseowl.com/rateloginserver/api/oauth/accesstoken
    </code></pre>

### Configure the Zoho API Console <a href="#user-content-part-a--zoho-api-console" id="user-content-part-a--zoho-api-console"></a>

1. Open the[ Zoho API Console ](https://api-console.zoho.in/)and sign in using the Zoho account associated with ServiceDesk Plus.
2. Click **Add Client** in the upper-right corner of the Applications list.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Select **Server-based Applications**.
4. Click **Create Now** under Server-based Applications.

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

5\. Enter the required client details and configure the application.

| Field                    | Enter                               |
| ------------------------ | ----------------------------------- |
| Client Name              | Enter a name of your choice         |
| Homepage URL             | Enter your ReleaseOwl homepage URL  |
| Authorized Redirect URIs | Enter your ReleaseOwl callback URL  |

<figure><img src="../../.gitbook/assets/image (2337).png" alt=""><figcaption></figcaption></figure>

6. Open the **Client Secret** tab. Use the copy icons to copy the **Client ID** and **Client Secret**. You will need these credentials when configuring the OAuth connection in ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (2333).png" alt=""><figcaption></figcaption></figure>



### Set Up OAuth Authentication in ReleaseOwl

1. In ReleaseOwl, navigate to **Administration → Credential Manager**.
2. Click **Register Credential** to create a new credential.

<figure><img src="../../.gitbook/assets/image (2334).png" alt=""><figcaption></figcaption></figure>

3.  Fill in the details as follows:

    | Field               | Value                                                                                                                                                                   |
    | ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
    | Credential Name     | Enter a name                                                                                                                                                            |
    | Credential Type     | Zoho Service Desk                                                                                                                                                       |
    | Scope               | Global                                                                                                                                                                  |
    | Authentication Type | OAuth2                                                                                                                                                                  |
    | Client ID           | Paste the Client ID you created in the Zoho Console                                                                                                                     |
    | Client Secret       | Paste the Client Secret you created in the Zoho Console                                                                                                                 |
    | Token URL           | `https://accounts.zoho.in/oauth/v2/token`                                                                                                                               |
    | Authorization URL   | `https://accounts.zoho.in/oauth/v2/auth`                                                                                                                                |
    | OAuth Scope         | <p><code>SDPOnDemand.requests.ALL</code><br><code>SDPOnDemand.requests.READ</code><br><code>SDPOnDemand.changes.ALL</code><br><code>SDPOnDemand.problems.ALL</code></p> |

    <figure><img src="../../.gitbook/assets/image (2335).png" alt=""><figcaption></figcaption></figure>
4. After saving the credential, click **Generate Token**. You will be redirected to a Zoho authorization page.&#x20;
5. Select **I allow … to access the above data** and click **Accept**. Once authorization is successful, a success message appears, confirming that the token has been generated successfully.

<div><figure><img src="../../.gitbook/assets/image (2336).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure></div>

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

#### Choosing what to sync <a href="#user-content-choosing-what-to-sync" id="user-content-choosing-what-to-sync"></a>

**Board Type = `filter`.** ReleaseOwl fetches only the modules you configure. Add a `request` block, a `change` block, or both. Each block is a ServiceDesk Plus `list_info` search, for example:

{% code overflow="wrap" %}
```abap
{  "request": {    "list_info": {      "row_count": 50,      "start_index": 1,      "search_criteria": { "field": "status.name", "condition": "is", "value": "Open" }    }  },  "change": {    "list_info": { "row_count": 50, "start_index": 1 }  }}
```
{% endcode %}

* A module with no block is **not** synced.
* If you provide no `search_criteria`, ReleaseOwl uses the default list (first 50 records).
* The filter must be valid JSON; otherwise the sync fails with _Error parsing a JSON Text_.

**Board Type = `project`.** ReleaseOwl syncs the **tasks** of the SDP project whose id is set as the integration's external id. A project can be looked up by title.

#### What ReleaseOwl reads and writes <a href="#user-content-what-releaseowl-reads-and-writes" id="user-content-what-releaseowl-reads-and-writes"></a>

| Direction      | Details                                                                                                                                                                                                                                                           |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Read           | Requests, changes (and project tasks): subject/title, description, priority, status, assignee (`technician`, else `change_owner`, else `change_manager`), created and last-updated time                                                                           |
| Statuses       | Request statuses and change statuses are imported per integration. Change statuses are shown as `<Stage> - <Status>`. A status counts as **Done** when its stage is `close`, or (without a stage) its name contains _closed_, _resolved_, _completed_ or _cancel_ |
| Write – status | Updating a ReleaseOwl user story updates the SDP request/change status. For changes the stage is also set                                                                                                                                                         |
| Write – notes  | Comments are added as a **request note** (requests) or **note** (changes)                                                                                                                                                                                         |
| Transitions    | SDP exposes no per-item transition graph, so any status can be selected                                                                                                                                                                                           |

#### Webhook URL and secret key <a href="#user-content-webhook-url-and-secret-key" id="user-content-webhook-url-and-secret-key"></a>

When you save the integration, ReleaseOwl generates a webhook URL and secret key for it:

{% code overflow="wrap" %}
```
<ReleaseOwlhost>/ratesaptms/webhook/tenant/<tenant>/project/<projectId>/zohodesk/{module}/sync?secretKey=<secretKey>
```
{% endcode %}

Replace `{module}` with `request` or `change`, depending on the module the webhook is for.

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

### Zoho ServiceDesk Webhook Configuration

A webhook enables ZohoServiceDesk Plus to notify ReleaseOwl when a request or change is created or updated, allowing ReleaseOwl to synchronize the information.

1. In ServiceDesk Plus, navigate to **Setup**.

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

2. Under Setup, select **Automation → Custom Actions → Webhooks** and click **New Webhook**.

<figure><img src="../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

3. Configure the following webhook details:

| Field        | Value                                                                                                                                                                                |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Name         | Enter a name of your choice.                                                                                                                                                         |
| URL          | Enter the ReleaseOwl webhook URL and replace `{module}` with `request` or `change`, as applicable.                                                                                   |
| Method       | `POST`                                                                                                                                                                               |
| Content Type | `application/json`                                                                                                                                                                   |
| Payload      | Enter a JSON body containing the record ID, such as `{ "id": "<record id>" }`. Replace `<record id>` with the appropriate ServiceDesk Plus placeholder for the request or change ID. |

4. Save the webhook. Create **one webhook per module** (requests, changes), each with its own  module value.

<figure><img src="../../.gitbook/assets/image (2338).png" alt=""><figcaption></figcaption></figure>
