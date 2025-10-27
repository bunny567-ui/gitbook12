# SAP Cloud ALM

This guide explains how to integrate **SAP Cloud ALM** with **ReleaseOwl** and synchronize artifacts, user stories, and related components between the two systems

#### Prerequisites

Before proceeding, ensure that:

* You have an active subscription to **SAP Cloud ALM**.
* You have the required permissions to create service instances in **SAP BTP Cockpit**.
* You have access to **ReleaseOwl** with administrative privileges.

### **Obtaining the Client ID, Client Secret, and URL**

To connect SAP Cloud ALM to ReleaseOwl, you first need to obtain the client credentials from your SAP BTP environment.

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

<figure><img src="../../.gitbook/assets/image (1601).png" alt=""><figcaption></figcaption></figure>

#### SAP Cloud ALM Project Integration

After registering the credentials, you can link your SAP Cloud ALM project with a ReleaseOwl project.

**Step 1: Navigate to Project Settings**

1. Switch to the desired working project in **ReleaseOwl**.
2. Go to **Project Settings**.
3. In the Project Settings section, navigate to **ALM Integrations** and click **Add**.

**Step 2: Fill in the Required Details**

* **Name:** Enter a unique name for the integration.
* **Description (Optional):** Add a short description for future reference.
* **External System:** Select **SAP Cloud ALM** from the dropdown list.
* **Credential:** Choose the registered **SAP Cloud ALM credential** from the dropdown list.
* **Host URL:** Enter the **SAP Cloud ALM server URL**.
* **Project:** Select the SAP Cloud ALM project you wish to integrate from the dropdown list.
* Once the details are filled in, click **Save** to establish the integration.

<figure><img src="../../.gitbook/assets/image (1602).png" alt=""><figcaption></figcaption></figure>

#### Syncing User Stories and Features

After successful integration, you can start syncing data between SAP Cloud ALM and ReleaseOwl.

1. Go to the **User Stories** section in ReleaseOwl.
2. Click on **Sync User Stories**.
   * This action fetches all the **features** and their associated **user stories** from SAP Cloud ALM into ReleaseOwl.
3. Once synced, you will see the imported user stories listed under their respective features.
4. By clicking the dropdown icon next to a **User Story ID**, you can view detailed information about that specific user story.

<figure><img src="../../.gitbook/assets/image (1603).png" alt=""><figcaption></figcaption></figure>

#### Managing User Stories in ReleaseOwl

Each synced user story can be further enhanced and managed directly within ReleaseOwl:

* Click on the **Actions** button corresponding to a user story.
  * From here, you can **edit** the user story and attach relevant components such as **transports**, **CPI artifacts**, and other related deliverables.
  * This enables seamless linkage between SAP Cloud ALM features and the technical artifacts managed through ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (1604).png" alt=""><figcaption></figcaption></figure>

#### Promoting User Stories

Once your user story is updated and ready for deployment:

1. Click on the **Promote** button for the respective user story.
2. This action triggers the **Release Pipeline** associated with that user story.
3. The pipeline executes all defined stages — such as **build**, **validation**, and **deployment** — ensuring end-to-end automation from SAP Cloud ALM to your target environments

<figure><img src="../../.gitbook/assets/image (1605).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1606).png" alt=""><figcaption></figcaption></figure>
