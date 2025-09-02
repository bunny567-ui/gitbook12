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

1. In Administration, go to Credential Manager.
2. On the displayed page, click Register Credential.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### Step 3: OAuth2 Authentication (For Client ID and Client Secret):

1. Log in to the **ServiceNow** website.
2. Go to **ALL** and search for **Application Registry.**
3. Click on **Application Registry.**

<figure><img src="../../.gitbook/assets/image (639).png" alt=""><figcaption></figcaption></figure>

4. Click the **New** button.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

5. Select **Create an OAuth API endpoint for external clients**.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

6. ServiceNow will generate a **Client ID** and **Client Secret** automatically.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

7. Copy these credentials and paste them into the appropriate fields in the **Register Credential** form in ReleaseOwl under OAuth2 Authentication.
8. Click the **Save** button.

<figure><img src="../../.gitbook/assets/image (641).png" alt=""><figcaption></figcaption></figure>

7. &#x20;Click on **Generate Token.** A popup screen will appear prompting you to enter a username and password.
8. Enter your **ServiceNow** username and password.
9. Click the **Generate** button.

<figure><img src="../../.gitbook/assets/image (642).png" alt=""><figcaption></figcaption></figure>

10. The generated token will be available in the **Manage Tokens** section under **ALL** in the ServiceNow website.

<figure><img src="../../.gitbook/assets/image (643).png" alt=""><figcaption></figcaption></figure>

### Step4: Configure Basic Authentication (For Basic Authentication)

1\.  After logging into your ServiceNow instance, click the Request Instance button.

<figure><img src="../../.gitbook/assets/image (644).png" alt=""><figcaption></figcaption></figure>

2. &#x20;You will receive an email containing the instance details.
3. In the email, find the section containing your username and password details.

<figure><img src="../../.gitbook/assets/image (645).png" alt=""><figcaption></figcaption></figure>

4. Copy these credentials and paste them into the appropriate fields in the Register Credential form in ReleaseOwl under Basic Authentication.

<figure><img src="../../.gitbook/assets/image (646).png" alt=""><figcaption></figcaption></figure>

## Integrating User Stories from ServiceNow to ReleaseOwl

#### &#x20;1. Open Project Settings

* Navigate to the top-right corner of the ReleaseOwl environment and click on Project Settings.

<figure><img src="../../.gitbook/assets/image (647).png" alt=""><figcaption></figcaption></figure>

#### 2. Go to ALM Integrations

1. In Project Settings, go to the ALM Integrations section and click on the +Add button.
2. Fill in the necessary fields:

* Name: Enter a name of your choice.
* External System: Select ServiceNow for integration.
* Credential: The registered credential will be auto-populated.

<figure><img src="../../.gitbook/assets/image (648).png" alt=""><figcaption></figcaption></figure>

#### 3. Access Filters Option

* Under the Host URL, you will find options for Assignment Group or Filters.

#### 4. Webhook URL & Save

* The Webhook URL is generated automatically. Click on the Save button to confirm the integration settings.

<figure><img src="../../.gitbook/assets/image (649).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/image (653).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/image (655).png" alt=""><figcaption></figcaption></figure>

### Sync User Stories with Applied Filters

* Once the filters are added, click on Sync User Stories to fetch the relevant user stories from ServiceNow based on the selected filters.
* Any updates made in ServiceNow will now reflect in the synced User Stories within ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (656).png" alt=""><figcaption></figcaption></figure>

