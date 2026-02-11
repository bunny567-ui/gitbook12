# SAP Cloud ALM

This guide explains how to integrate **SAP Cloud ALM** with **ReleaseOwl** and synchronize artifacts, user stories, and related components between the two systems. Cloud ALM is providing the API'S for updating the status of the feature.

## Overview

SAP Cloud ALM provides centralized management for requirements and features, serving as the single source of truth throughout the product lifecycle. ReleaseOwl, on the other hand, focuses on automating the technical delivery process—including managing transports, CPI artifacts, pipelines, and deployments.&#x20;

Through this connection, Cloud ALM can initiate implementation phases, monitor progress, and enforce approvals, while ReleaseOwl updates Cloud ALM with transport information, pipeline execution results, and deployment status, allowing Cloud ALM to maintain complete traceability from requirement definition to final production deployment.&#x20;

## Prerequisites

Before proceeding, ensure that:

* You have an active subscription to **SAP Cloud ALM**.
* You have the required permissions to create service instances in **SAP BTP Cockpit**.
* You have access to **ReleaseOwl** with administrative privileges.

## Connect SAP Cloud ALM with ReleaseOwl

To connect SAP Cloud ALM to ReleaseOwl, you first need to obtain the client credentials from your SAP BTP environment.

### Fetch Cloud ALM Client Credentials from SAP BTP

1. Navigate to **Instances and Subscriptions** in your SAP BTP Cockpit.
2. Click **Create**, select the service **SAP Cloud ALM API**, and provide the required details.
3. Click **Next**, then choose **Create Instance** to complete the setup.

<figure><img src="../../.gitbook/assets/image (1599).png" alt=""><figcaption></figcaption></figure>

4. Once the instance is created, open it and select **View Credentials**.
5. Copy the **Client ID**, **Client Secret**, and **URL** from the credentials section.
6. These credentials will be used to authenticate and establish a secure connection between ReleaseOwl and SAP Cloud ALM.

<figure><img src="../../.gitbook/assets/image (1600).png" alt=""><figcaption></figcaption></figure>

### Register SAP Cloud ALM in ReleaseOwl

Once you have the credentials, register them in ReleaseOwl to enable integration.

1. Open the **Credential Manager** in **ReleaseOwl**.
2. Click **Register Credential**.

<figure><img src="../../.gitbook/assets/image (1598).png" alt=""><figcaption></figcaption></figure>

3. Paste the copied **Client ID**, **Client Secret**, and **URL** into the respective fields.
4. Click **Save** to register the credentials successfully.

{% hint style="info" %}
**Note :** For the **Token URL**, append "**/oauth/token**" to the **URL** obtained from the service key.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (1601).png" alt=""><figcaption></figcaption></figure>

## SAP Cloud ALM Project Integration

After registering the credentials, you can link your SAP Cloud ALM project with a ReleaseOwl project.

### **Step 1: Navigate to Project Settings**

1. Switch to the desired working project in **ReleaseOwl**.
2. Go to **Project Settings**.
3. In the Project Settings section, navigate to **ALM Integrations** and click **Add**.

### **Step 2: Fill in the Required Details**

* **Name:** Enter a unique name for the integration.
* **Description (Optional):** Add a short description for future reference.
* **External System:** Select **SAP Cloud ALM** from the dropdown list.
* **Credential:** Choose the registered **SAP Cloud ALM credential** from the dropdown list.
* **Host URL:** Enter the **SAP Cloud ALM server URL**.
* **Project:** Select the SAP Cloud ALM project you wish to integrate from the dropdown list.
* Once the details are filled in, click **Save** to establish the integration.

<figure><img src="../../.gitbook/assets/image (1602).png" alt=""><figcaption></figcaption></figure>

## Syncing  Features and  User Stories

After successful integration, you can start syncing data between SAP Cloud ALM and ReleaseOwl.

1. Go to the **User Stories** section in ReleaseOwl.
2. Click on **Sync User Stories**.
   * This action fetches all the **features** and their associated **user stories** from SAP Cloud ALM into ReleaseOwl.
3. Once synced, you will see the imported user stories listed under their respective features.
4. By clicking the dropdown icon next to a **User Story ID**, you can view detailed information about that specific user story.

<figure><img src="../../.gitbook/assets/image (1603).png" alt=""><figcaption></figcaption></figure>

## Managing User Stories in ReleaseOwl&#x20;

Each synced user story can be further enhanced and managed directly within ReleaseOwl:&#x20;

* Click on the **Actions** button corresponding to a user story.&#x20;
* From here, you can edit the user story and attach relevant components such as transports, CPI artifacts, and other related deliverables.&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* This enables seamless linkage between SAP Cloud ALM features and the technical artifacts managed through ReleaseOwl.&#x20;

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Promoting User Stories from ReleaseOwl&#x20;

Once your user story is updated and ready for deployment:&#x20;

1. Click on the Promote button for the respective user story.&#x20;
2. This action triggers the Release Pipeline associated with that user story.&#x20;
3. The pipeline executes all defined stages — such as build, validation, and deployment — ensuring end-to-end automation from SAP Cloud ALM to your target environments&#x20;

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Promoting User Stories from SAP Cloud ALM&#x20;

&#x20;You can promote user stories directly from SAP Cloud ALM, and the corresponding execution continues in ReleaseOwl based on the lifecycle actions performed in Cloud ALM.&#x20;

### Accessing the User Story in Cloud ALM&#x20;

1. In ReleaseOwl, open the required user story.&#x20;
2. Click the External ID, which redirects you to the user story/features in SAP Cloud ALM

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Bidirectional Synchronization&#x20;

SAP Cloud ALM and ReleaseOwl maintain a bidirectional connection:&#x20;

* Any Cloud ALM lifecycle action (Start Implementation, Handover to Test, etc.) is sent to ReleaseOwl via webhook events.&#x20;
* Any technical action performed in ReleaseOwl (adding a transport, deployment updates) is written back to Cloud ALM as comments in the description of the user story.&#x20;
* This ensures both systems stay aligned throughout the implementation lifecycle.&#x20;

<figure><img src="../../.gitbook/assets/image (1622).png" alt=""><figcaption></figcaption></figure>

### Start Implementation&#x20;

When you click Start Implementation in SAP Cloud ALM:&#x20;

1. A confirmation dialog appears.&#x20;
2. Before performing this action, the user must attach and release the transport in ReleaseOwl.&#x20;
3. After confirmation, Cloud ALM sends the updated status event to ReleaseOwl.&#x20;
4. ReleaseOwl updates the user story and records the change back in Cloud ALM as a comment.&#x20;

<figure><img src="../../.gitbook/assets/image (1623).png" alt=""><figcaption></figcaption></figure>

### Handover to Test&#x20;

When the user selects Handover to Test in SAP Cloud ALM:&#x20;

1. Cloud ALM emits a status change event through the configured webhook.&#x20;

<figure><img src="../../.gitbook/assets/image (1624).png" alt=""><figcaption></figcaption></figure>

2. ReleaseOwl receives the event and triggers the corresponding pipeline stage.&#x20;
3. On refreshing the user story in Cloud ALM, you will see a comment added under the description indicating that the change was processed by the webhook event.  &#x20;

<figure><img src="../../.gitbook/assets/image (1625).png" alt=""><figcaption></figcaption></figure>

### Pipeline Status in ReleaseOwl&#x20;

You can verify execution progress in ReleaseOwl:&#x20;

* Navigate to the User Stories dashboard.&#x20;
* As the Cloud ALM status changes are processed, the corresponding user story will automatically move to the next pipeline stage in ReleaseOwl.&#x20;

<figure><img src="../../.gitbook/assets/image (1626).png" alt=""><figcaption></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (1627).png" alt=""><figcaption></figcaption></figure>

#### Managing User Stories in ReleaseOwl

Each synced user story can be further enhanced and managed directly within ReleaseOwl:

* Click on the **Actions** button corresponding to a user story.
  * From here, you can **edit** the user story and attach relevant components such as **transports**, **CPI artifacts**, and other related deliverables.
  * This enables seamless linkage between SAP Cloud ALM features and the technical artifacts managed through ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (1604).png" alt=""><figcaption></figcaption></figure>

## Webhook Configuration in Cloud ALM&#x20;

To ensure ReleaseOwl stays updated with changes made in Cloud, you must configure webhooks in Cloud ALM.&#x20;

### Configure Destination in SAP BTP&#x20;

1. Log in to your SAP BTP subaccount.&#x20;
2. Go to Connectivity from the left-side navigation pane.&#x20;
3. Select Destinations and click on the Create button.&#x20;
4. Provide the required destination details:&#x20;

* Name: Enter a destination name of your choice.&#x20;
* Type: Select HTTP.&#x20;
* Proxy Type: Set to Internet.&#x20;
* URL: Enter the webhook URL provided during the ReleaseOwl solution implementation.&#x20;
* Click Save to complete the configuration.

<figure><img src="../../.gitbook/assets/image (1630).png" alt=""><figcaption></figcaption></figure>

### Configure Webhooks in SAP Cloud ALM&#x20;

1. Navigate to SAP Cloud ALM → Administration → External API Management.&#x20;

<figure><img src="../../.gitbook/assets/image (1631).png" alt=""><figcaption></figcaption></figure>

2. In the external Management, click on the Webhooks Management. &#x20;

<figure><img src="../../.gitbook/assets/image (1632).png" alt=""><figcaption></figcaption></figure>

3. Click the “+” icon to create a new webhook and fill in the required details:&#x20;

* Name: Provide a meaningful webhook name.&#x20;
* Resource Type: Select the desired resource type (any applicable option can be chosen).&#x20;
* Destination ID: Choose the destination you created in SAP BTP.&#x20;

4. Click Save.&#x20;

<figure><img src="../../.gitbook/assets/image (1633).png" alt=""><figcaption></figcaption></figure>

### Enter the Webhook Path&#x20;

In the **Path** field, enter the ReleaseOwl webhook endpoint using the following general structure:

```
ratesaptms/webhook/tenant/<tenant_id>/project/<project_id>/calm/pmsint/<integration_id>/sync?secretKey=<secret_key>
```

#### Parameter Details

* **tenant\_id**:\
  The unique identifier assigned to your ReleaseOwl tenant.
* **project\_id**:\
  The ID of the specific ReleaseOwl project where the integration is configured.
* **integration\_id**:\
  The reference ID of the Cloud ALM integration you created in ReleaseOwl.
* **secret\_key**:\
  The authentication key automatically generated during the ReleaseOwl webhook setup, used to securely validate incoming requests.

<figure><img src="../../.gitbook/assets/image (1634).png" alt=""><figcaption></figcaption></figure>

### Add External API Management to Subscription Management&#x20;

1. Navigate to **Subscription Management** within SAP Cloud ALM.&#x20;

<figure><img src="../../.gitbook/assets/image (1635).png" alt=""><figcaption></figcaption></figure>

2\. Click the “+” icon to add a new subscription.&#x20;

3\. Provide the following details:&#x20;

* Resource Type: Select Feature.&#x20;
* Type: Choose External.&#x20;
* Webhook: Select the webhook created &#x20;

4\. Click Save to complete the subscription setup.&#x20;

<figure><img src="../../.gitbook/assets/image (1636).png" alt=""><figcaption></figcaption></figure>

* In SAP cloud ALM, post creation of subscription and webhook in external API management, opt the same subscription in your project in the subscriptions tab for the feature item type.&#x20;
* Once your SAP Cloud ALM feature is moved to "**In Testing**" status, then only RO user story will be automatically promoted through release pipeline with the help of webhook.
