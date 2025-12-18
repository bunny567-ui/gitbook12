# ServiceNow

ServiceNow is a cloud-based SaaS (Software-as-a-Service) platform that automates organizational processes and delivers a consistent, consumer-like experience. It is a comprehensive development environment in which you can build, test and implement applications that provide automated workflows for challenges such as case management, operations management and services management.&#x20;

{% hint style="info" %}
The detailed user guide can be found at [https://docs.servicenow.com/en-US/bundle/sandiego-platform-user-interface/page/administer/navigation-and-ui/concept/c\_SystemUserGuide.html](https://docs.servicenow.com/en-US/bundle/sandiego-platform-user-interface/page/administer/navigation-and-ui/concept/c_SystemUserGuide.html)
{% endhint %}

## Prerequisites

To successfully integrate ServiceNow with ReleaseOwl, ensure you have the following:

* **ServiceNow**: A functional ServiceNow instance with the necessary permissions to access and configure Application Registry and OAuth settings.
* **ReleaseOwl Dashboard**: Access to the ReleaseOwl platform with appropriate administrative rights to manage credentials and integrations.

## Registering ServiceNow

### Step 1: Access Credential Manager

1. In Administration, go to **Credential Manager**.
2. On the displayed page, click **Register Credential**.

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

### Step 2: Fill in Credential Details

To set up your credentials in ReleaseOwl, complete the following fields:

1. **Credential Name**:\
   Enter a descriptive name for the credential, which will help you identify it later in ReleaseOwl.
2. **Credential Type**:\
   Select **ServiceNow** from the list of available credential types.
3. **Scope** – Select the scope of the credential:
   * **Global** – Visible to all users.
   * **Private** – Visible only to the user who created it.
4. **Authentication Type**:\
   Choose one of the following authentication methods:
   * **OAuth2**: Use this option for token-based authentication.
   * **Basic Authentication**: Use this option for username and password-based access.
5. **Instance URL**:\
   Enter your ServiceNow hosting URL (e.g., `https://<instance-name>.service-now.com`).

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

### Step 3: OAuth2 Authentication (For Client ID and Client Secret):

1. Log in to the **ServiceNow** website.
2. Go to **ALL** and search for **Application Registry.**
3. Click on **Application Registry.**

<figure><img src="../../.gitbook/assets/image (639).png" alt=""><figcaption></figcaption></figure>

4. Click the **New** button.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. Select **Create an OAuth API endpoint for external clients**.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. ServiceNow will generate a **Client ID** and **Client Secret** automatically.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

7. Copy these credentials and paste them into the appropriate fields in the **Register Credential** form in ReleaseOwl under OAuth2 Authentication.
8. Click the **Save** button.

<figure><img src="../../.gitbook/assets/image (641).png" alt=""><figcaption></figcaption></figure>

9. Click on **Generate Token.** A popup screen will appear prompting you to enter a username and password.
10. Enter your **ServiceNow** username and password.
11. Click the **Generate** button.

<figure><img src="../../.gitbook/assets/image (642).png" alt=""><figcaption></figcaption></figure>

12. The generated token will be available in the **Manage Tokens** section under **ALL** in the ServiceNow website.

<figure><img src="../../.gitbook/assets/image (643).png" alt=""><figcaption></figcaption></figure>

### Step4: Configure Basic Authentication (For Basic Authentication)

To perform **Basic Authentication**, follow the steps below:

1. In Administration, go to **Credential Manager**.
2. On the displayed page, click **Register Credential**.

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

3. Fill in the credential details as shown in the table below:

| **Field**               | **Description**                                                                                                                 |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| **Credential Name**     | Enter a name of your choice.                                                                                                    |
| **Credential Type**     | Select **ServiceNow**                                                                                                           |
| **Scope**               | Select the scope of the credential:- **Global** – Visible to all users.- **Private** – Visible only to the user who created it. |
| **Authentication Type** | Choose **Basic**.                                                                                                               |
| **Username**            | Enter **ServiceNow username**.                                                                                                  |
| **Password**            | Enter **ServiceNow password**.                                                                                                  |
| **Instance URL**        | Enter your ServiceNow hosting URL (e.g., `https://<instance-name>.service-now.com`).                                            |

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Integrating User Stories from ServiceNow to ReleaseOwl

#### &#x20;1. Open Project Settings

* Navigate to the top-right corner of the ReleaseOwl environment and click on Project Settings.

<figure><img src="../../.gitbook/assets/image (647).png" alt=""><figcaption></figcaption></figure>

#### 2. Go to ALM Integrations

1. In Project Settings, go to the ALM Integrations section and click on the +Add button.
2. Fill in the necessary fields:

* Name: Enter a name of your choice.
* External System: Select ServiceNow for integration.
* Language:  Select the language that enables users to change the language of the user story task.&#x20;
* Credential: The registered credential will be auto-populated.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### 3. Access Filters Option

* Under the Host URL, you will find options for Assignment Group, Filters and Project.

#### 4. Webhook URL & Save

* The Webhook URL is generated automatically. Click on the **Save** button to confirm the integration settings.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Assignment Group Option

* If you choose the Assignment Group option, you will see a section where you can select an Assignment Group from the available External Projects in ServiceNow.

<figure><img src="../../.gitbook/assets/image (650).png" alt=""><figcaption></figcaption></figure>

* These groups correspond to different teams or categories in ServiceNow, such as:
* Incident Management
* Application Development
* Problem Analyzers, etc.

<figure><img src="../../.gitbook/assets/image (651).png" alt=""><figcaption></figcaption></figure>

### Syncing User Stories

Select the project. Any changes made in ServiceNow will be reflected in the User Stories when you click on Sync User Stories

<figure><img src="../../.gitbook/assets/image (652).png" alt=""><figcaption></figcaption></figure>

### Filters Option

* If you choose the Filters option, you will access the Filters Section.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Add New Filters

* Click on the +ADD button.
* A pop-up window will appear, displaying three filter types:
* Task
* Incident
* Change Request

<figure><img src="../../.gitbook/assets/image (654).png" alt=""><figcaption></figcaption></figure>

### Select and Add a Filter

* Choose the appropriate filter type based on your requirements.
* Click Add to apply the selected filter.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Sync User Stories with Applied Filters

* Once the filters are added, click on Sync User Stories to fetch the relevant user stories from ServiceNow based on the selected filters.
* Any updates made in ServiceNow will now reflect in the synced User Stories within ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (1597).png" alt=""><figcaption></figcaption></figure>

### Project Section

* The **Project** section allows users to select the project associated with a particular task.&#x20;

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Configure Webhook URL in ServiceNow

Follow the steps below to configure a webhook in ServiceNow:&#x20;

1. Log in to your **ServiceNow** account.
2. In the left navigation pane, select **All**.
3. Type **Business Rules** in the filter box and open it.

<figure><img src="../../.gitbook/assets/image (1471).png" alt=""><figcaption></figcaption></figure>

4. Click the **New** button on the right-hand side.

<figure><img src="../../.gitbook/assets/image (1477).png" alt=""><figcaption></figcaption></figure>

5. Enter a **Name** for your record.
6. In the **Table** field, select the table you want to trigger the webhook from (for example, **Incident**, **Change Request , Task** etc.).
7. Check the **Active** and **Advanced** options.
8. In the **When to run** section:

* From the **When** drop-down, select **After**.
* Select **Insert** and **Update** so the webhook triggers on both record creation and updates.

<figure><img src="../../.gitbook/assets/image (1473).png" alt=""><figcaption></figcaption></figure>



8. In the **Advanced** section, paste the following script:

```javascript
(function executeRule(current, previous /*null when async*/) {
    var request = new sn_ws.RESTMessageV2();
    request.setEndpoint("<copy the Webhook URL from the PMS integration tab in ReleaseOwl Project settings>");
    request.setHttpMethod('POST');
    //request.setBasicAuth(user,password);
    request.setRequestHeader("Accept", "application/json");
    request.setRequestHeader("Content-Type", "application/json");
    
    request.setRequestBody(
        JSON.stringify({
            "sys_id": current.sys_id.toString(),
            "product": current.product.toString()
        })
    );
    
    var response = request.execute();
    gs.log(response.getBody());
})(current, previous);
```

<figure><img src="../../.gitbook/assets/image (1474).png" alt=""><figcaption></figcaption></figure>

#### Note

* Replace the placeholder `<copy the Webhook URL…>` in the script with the actual **Webhook URL** generated in **ReleaseOwl** under: **Project Settings → PMS Integration tab**.
*   The webhook URL in ReleaseOwl follows this pattern:

    ```
    https://na3.releaseowl.com/ratesaptms/webhook/tenant/{tenant}/project/{projectId}/{tableName}/sync?secretKey={secretKey}
    ```
* **{tableName}** must match the table selected in the Business Rule Record (e.g., `incident`, `task`, `change_request,`). This means the table name is not only used to determine which records trigger the webhook—it also appears explicitly in the webhook URL path.

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
