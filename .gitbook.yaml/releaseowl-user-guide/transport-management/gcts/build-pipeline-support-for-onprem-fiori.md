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
3. Click on **Create New Build Pipeline**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FmK0PW2vwN6enjypO58id%252Fimage.png%3Falt%3Dmedia%26token%3D2a8b4e49-9c7d-4261-888b-ddc9a9f12458&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4f5a8962&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Step 2: Define Pipeline Details**

1. Enter a descriptive **Pipeline Name**.
2. Click **Next**.

**Step 3: Connect to Repository**

1. Enter the **Repository URL** where the UI5 project is stored.
2. Select the SCM credentials, which are your version control credentials registered in the credential manager.
3. Select the appropriate **Branch** containing the UI5 project.
4. Choose the **Version Control Platform**.
5. Click **Next** to proceed.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FqQJj48TnNK2RwrhGTXEY%252Fimage.png%3Falt%3Dmedia%26token%3D80a8655d-6282-43ab-a8ca-a7d67e66965f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a4df28ed&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Step 4: Configure Build Parameters**

1. In the **Builder** section, specify the following:

* **Build Type**: It is automatically populated eg: `UI5 ABAP`
* **Build Tool Version**: Select the build tool version of it
* **Discard Old Builds**: Define the number of previous builds to remove.
* **Max Builds to Keep**: Set a limit for retained builds.

The **App Details** in the **Build Section** need to be manually entered based on the information provided in the `ui5-deploy.yaml` file. Attributes such as **App Id, App Name, Description and Package Name** should be extracted from the configuration file and entered into the respective fields to ensure accurate deployment.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F6Vdhftm5otEREZOf9Oc0%252Fimage.png%3Falt%3Dmedia%26token%3D062037d9-7ff8-48f3-8b9c-63e50fb02cfa&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=96c25827&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Step 5: Scheduler and Notifications**

1. **Scheduler**: Choose **Manual**, **Schedule**, or **Webhook** for pipeline execution.
2. **Notifications**: Enter email IDs to receive build alerts.
3. **Tool Integrations**: Enable **SonarQube** and select credentials if needed.
4. Click **Save** button.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F73QzPbbLU3kMZwUtyRnv%252Fimage.png%3Falt%3Dmedia%26token%3D4f5f0015-5980-4370-a60e-9521a69dc998&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a4c50645&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Step 6: Triggering and Monitoring a Build**

1. After creating the build pipeline, navigate to the **Build Pipelines** section.
2. Click the **Build Now** button to trigger a new build process.
3. Once the build starts, view its progress and details inside the pipeline.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FuivghEShhyGTnudyliAl%252Fimage.png%3Falt%3Dmedia%26token%3De0d09e04-4343-43da-9ba5-d1fee1c5f8d4&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=8ce271f9&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Clicking on a pipeline name opens a detailed build history, where each triggered build is listed with:

* **Build Number**: The sequential number assigned to each build.
* **Java/Node Version**: The versions used for the build.
* **Repository & Branch**: The source code details.
* **Triggered By**: The user who initiated the build.
* **Triggered Time**: The timestamp when the build started.
* **Status**: Indicates whether the build was **successful, failed, o**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FWDE3inNwCYOuUXAtPZPs%252Fimage.png%3Falt%3Dmedia%26token%3Dfc5bee4b-7cff-4672-91ca-744053b15e2f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b45b4299&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. Clicking the arrow (**>**) button next to a build allows you to view detailed logs, status, timestamp, and deployment insights.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fz6vKruon6ne21L47DnQG%252Fimage.png%3Falt%3Dmedia%26token%3Db69f4c30-eced-4858-9371-5499b6765d20&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=45364836&#x26;sv=2" alt=""><figcaption></figcaption></figure>

6. After a successful build, click the dropdown button to enter a **Transport ID**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FNQcy8Lc6p4eR3qLTVMwD%252Fimage.png%3Falt%3Dmedia%26token%3D2c64fd4e-3c44-431c-856f-96173fd15a04&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=38deb0dc&#x26;sv=2" alt=""><figcaption></figcaption></figure>

7. Select a **Transport ID** from the list before proceeding with the upload.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FuPIDWE8oDyvRvGwl90QQ%252Fimage.png%3Falt%3Dmedia%26token%3D86a2f616-b1fd-42c4-959c-ce8ceb876fe8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3126043f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

8. Click the **Transport** button next to the dropdown field in the "**Upload to SAPUI5 ABAP Repository"** popup.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FBKN6fY6oiv3Dym0gW1FH%252Fimage.png%3Falt%3Dmedia%26token%3D0319d0f8-ce55-4e9b-bc25-2ef251c9a977&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ed77d388&#x26;sv=2" alt=""><figcaption></figcaption></figure>

9. The "**Create WorkBench Transport**" dialog appears.

* Enter the necessary details to create a WorkBench transport.
* Confirm the settings and complete the transport process.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FHglpwsVHYZDzSJg0uV79%252Fimage.png%3Falt%3Dmedia%26token%3D5ec206c4-d6d6-4198-8cdc-c1c7f0ab6187&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ea3796da&#x26;sv=2" alt=""><figcaption></figcaption></figure>

10. After uploading the build, you can check the **Upload Logs**, which provide real-time updates on the status of the deployment process.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FyKUtSc3N1TCeOWmAQZ2j%252Fimage.png%3Falt%3Dmedia%26token%3Dcb766dfa-c990-40ee-b061-f24062203b2c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=874f62b5&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The **Upload Log** provides real-time updates on the execution of the upload process.
{% endhint %}
