# Build pipeline support for onPrem Fiori

SAP Fiori applications traditionally require **manual transport management** via **SAP TMS (Transport Management System)**. However, **ReleaseOwl** provides an **automated pipeline-based approach** for deploying Fiori apps on **on-premise SAP systems** using transport requests. This guide explains how ReleaseOwl streamlines the **build, transport, and deployment process** for Fiori applications.

### Prerequisites <a href="#pdf-page-o5nrf0ske61dolpfer3i-prerequisites" id="pdf-page-o5nrf0ske61dolpfer3i-prerequisites"></a>

Before setting up the UI5 ABAP build pipeline in ReleaseOwl, ensure the following prerequisites are met:

1. **SAP System Access**: You need access to an on-premise SAP system with proper authorizations for transport requests.
2. **SAP Git Repository**: The source code for the UI5 application must be stored in an SAP Git repository.
3. **Node.js Environment**: Ensure that Node.js (preferably version 16 or later) is installed for UI5 build tools.
4. **Transport Package**: A valid SAP transport package must be created to deploy the UI5 application.
5. **ReleaseOwl Access**: Users must have valid login credentials and required permissions in ReleaseOwl to configure build pipelines.

### Setting Up the Build pipeline support for onPrem Fiori <a href="#pdf-page-o5nrf0ske61dolpfer3i-setting-up-the-build-pipeline-support-for-onprem-fiori" id="pdf-page-o5nrf0ske61dolpfer3i-setting-up-the-build-pipeline-support-for-onprem-fiori"></a>

#### **Step 1: Navigate to Build Pipelines**

1. Log in to **ReleaseOwl**.
2. In the left-side navigation panel, go to **Build** and then select the **Build Pipelines**.
3. Click on **Create New Build Pipeline.**

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Step 2: Define Pipeline Details**

1. Enter a descriptive **Pipeline Name**.
2. Click **Next**.

**Step 3: Connect to Repository**

1. Enter the **Repository URL** where the UI5 project is stored.
2. Select the SCM credentials, which are your version control credentials registered in the credential manager.
3. Select the appropriate **Branch** containing the UI5 project.
4. Choose the **Version Control Platform**.
5. Click **Next** to proceed.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Step 4: Configure Build Parameters**

1. In the **Builder** section, specify the following:

* **Build Type**: It is automatically populated eg: `UI5 ABAP`
* **Build Tool Version**: Select the build tool version of it
* **Discard Old Builds**: Define the number of previous builds to remove.
* **Max Builds to Keep**: Set a limit for retained builds.

The **App Details** in the **Build Section** need to be manually entered based on the information provided in the `ui5-deploy.yaml` file. Attributes such as **App Id, App Name, Description and Package Name** should be extracted from the configuration file and entered into the respective fields to ensure accurate deployment.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Step 5: Scheduler and Notifications**

1. **Scheduler**: Choose **Manual**, **Schedule**, or **Webhook** for pipeline execution.
2. **Notifications**: Enter email IDs to receive build alerts.
3. **Tool Integrations**: Enable **SonarQube** and select credentials if needed.
4. Click **Save** button.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Step 6: Triggering and Monitoring a Build**

1. After creating the build pipeline, navigate to the **Build Pipelines** section.
2. Click the **Build Now** button to trigger a new build process.
3. Once the build starts, view its progress and details inside the pipeline.

<figure><img src="../../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

4. Clicking on a pipeline name opens a detailed build history, where each triggered build is listed with:

* **Build Number**: The sequential number assigned to each build.
* **Java/Node Version**: The versions used for the build.
* **Repository & Branch**: The source code details.
* **Triggered By**: The user who initiated the build.
* **Triggered Time**: The timestamp when the build started.
* **Status**: Indicates whether the build was **successful or failed.**&#x20;

<figure><img src="../../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

5. Clicking the arrow (**>**) button next to a build allows you to view detailed logs, status, timestamp, and deployment insights.

<figure><img src="../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

**Upload Build**

6. In the top right, click the **Upload Build** button to start the upload process.
7. A popup titled **"Upload To SAPUI5 ABAP Repository"** will appear.
8. Click the **clipboard icon** to **select an existing transport request** from the list.

<figure><img src="../../../.gitbook/assets/image (1370).png" alt=""><figcaption></figcaption></figure>

9. Alternatively, click the **Create** button next to the dropdown to open the **"Create Workbench Transport"** dialog

<figure><img src="../../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

10. When the **"Create Workbench Transport"** popup appears:
    * **Name**: Enter a meaningful name for the transport request.
    * **Description** (optional): Provide a short description of the transport’s purpose.
    * **Target System**: Select the appropriate target system from the dropdown.
11. Click **Create** to generate the transport request. Once created, the transport will be automatically selected in the **Upload To SAPUI5 ABAP Repository** dialog.

<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

12. After selecting or creating the transport request, click the **Upload** button.

    * The **SAPUI5 (Fiori) application** will be deployed to the **SAP on-premise ABAP repository** using the selected transport.



<figure><img src="../../../.gitbook/assets/image (1372).png" alt=""><figcaption></figcaption></figure>

13. You can monitor the deployment status in the **Upload Logs** section, which provides real-time updates and logs for each step of the upload process.

<figure><img src="../../../.gitbook/assets/image (1373).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The **Upload Log** provides real-time updates on the execution of the upload process.
{% endhint %}
