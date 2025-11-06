# Tosca Server

This guide explains how to integrate **Tosca Server** with **ReleaseOwl** to run automated functional and web tests as part of your release pipelines. It describes the end-to-end steps required to register Tosca credentials, create Test Configurations (direct and via SAP Cloud Connector), trigger test executions from ReleaseOwl, and view results, logs and reports inside ReleaseOwl.

### 1. Prerequisites

Before proceeding, ensure the following:

1. A **local Tosca server** is installed and running.
2. You have administrative access to both the **Tosca server** and **ReleaseOwl**.
3. You have access to the **network** where the Tosca server is hosted to ensure connectivity from ReleaseOwl.

### 2. Credential Manager Setup

The Credential Manager in ReleaseOwl allows you to securely register Tosca server credentials. Follow the steps below:

**Access Credential Manager**

1. Log in to **ReleaseOwl**.
2. Navigate to **Credential Manager**.
3. Click on **Register Credential** to create a new credential.

<figure><img src="../../../.gitbook/assets/image (1541).png" alt=""><figcaption></figcaption></figure>

**2: Enter Credential Details**

Fill in the required fields:

* **Credential Name:** Enter a descriptive name for this credential (e.g., `Tosca_Local`).
* **Credential Type:** Select **Tosca Server**.
* **Scope:**
  * **Global:** Credential is accessible to all ReleaseOwl users.
  * **Private:** Credential is accessible only to the user who created it.
* **Token URL:** Enter the URL to your Tosca server token endpoint in the format: http(s)://\<Tosca\_Server\_IP\_or\_Hostname>:/tua/connect/token

<figure><img src="../../../.gitbook/assets/image (1542).png" alt=""><figcaption></figcaption></figure>

#### 3: Generate Client ID and Client Secret

1. Open your **local Tosca server** and go to **User Administration** → **My Account**.

<figure><img src="../../../.gitbook/assets/image (1544).png" alt=""><figcaption></figcaption></figure>

2. Click **Add New** to create a new user token.

<figure><img src="../../../.gitbook/assets/image (1543).png" alt=""><figcaption></figcaption></figure>

3. Enter a name of your choice and click **Generate Token**.

<figure><img src="../../../.gitbook/assets/image (1545).png" alt=""><figcaption></figcaption></figure>

4. Copy the generated **Client ID** and **Client Secret**.
5. Paste these values into the corresponding fields in ReleaseOwl’s Credential Manager.
6. Click **Save** to register the credential.

<figure><img src="../../../.gitbook/assets/image (1546).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1549).png" alt=""><figcaption></figcaption></figure>

### 3. Test Configuration with Proxy Type: None

This option is used when ReleaseOwl connects directly to the Tosca server without using a cloud connector.

#### 1: Create Test Configuration

1. Navigate to **Project View** in ReleaseOwl.
2. Under **Test Automation**, click **Test Configuration**.
3. Click **Create Test Configuration** to start.

<figure><img src="../../../.gitbook/assets/image (1550).png" alt=""><figcaption></figcaption></figure>

#### 2: Fill Test Configuration Details

* **Name:** Enter a name for this configuration (e.g., `Tosca_UAT_Integration`).
* **Test System:** Select the Tosca server.&#x20;
* **Proxy Type:** Select **None.**&#x20;
* **Credentials:** Select the credential you registered earlier.
* **Tosca Server URL:** Enter the URL of your Tosca server.
* **Project Name:** Enter the project name which is nothing but the workspace in the tosca commander.
* **Events:** Enter the Tosca test events name sets that need to be executed.&#x20;

#### 3: Save and Verify

1. Click **Submit** to store the Test Configuration.

<figure><img src="../../../.gitbook/assets/image (1548).png" alt=""><figcaption></figcaption></figure>

### 4. Test Configuration with SAP Cloud Connector

In addition to connecting directly, ReleaseOwl allows you to configure Tosca test execution via the **SAP Cloud Connector**. This enables secure connectivity between ReleaseOwl, Tosca Server, and your SAP BTP environment.

#### 1: Create Test Configuration with Cloud Connector

1. Navigate to **Project View** → **Test Configuration** under **Test Automation**.
2. Click **Create Test Configuration**.

#### 2: Fill Test Configuration Details

* **Name:** Enter a name for this configuration (e.g., `Tosca_UAT_Integration`).
* **Test System:** Select the Tosca server.
* **Proxy Type:** Select **SAP Cloud Connector**.
* **Proxy URL:** This will be automatically populated once the connector is selected.
* **SAP Cloud Credentials:** Select your **SAP BTP credentials** that you have already registered in the **Credential Manager**.
* **Destination:** Enter the destination that you have already created in your SAP BTP cockpit. This ensures ReleaseOwl routes requests securely through the connector.
* **Project Name:** Enter the Tosca workspace name (as created in Tosca Commander).
* **Events:** Enter the Tosca test event names that need to be executed during the pipeline run.

#### 3: Save and Verify

1. Click **Submit** to save the Test Configuration.

<figure><img src="../../../.gitbook/assets/image (1551).png" alt=""><figcaption></figcaption></figure>

### Executing Test Runs via Tosca Server

1. To start the execution, click the **Run** button in ReleaseOwl.
2. To view the test runs, click **View Test Runs** against the desired **Test Configuration**.
3. The executed test runs along with their results, logs, and reports will be displayed.

<figure><img src="../../../.gitbook/assets/image (1552).png" alt=""><figcaption></figcaption></figure>

4. **Reports and Logs**
   * When you click **Reports**, you will see details such as:
     * The executed test cases and their status.
   * When you click **Logs**, you will get the **SAP Test Logs**, which provide detailed execution information useful for troubleshooting and validation.
