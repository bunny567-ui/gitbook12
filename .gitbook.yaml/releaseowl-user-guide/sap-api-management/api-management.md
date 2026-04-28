# API Management

The **API Management** module in ReleaseOwl provides a comprehensive set of tools to streamline the management of SAP API artifacts. From synchronizing and configuring API proxies to tracking revisions and managing deployments across environments, this module ensures efficient control over your API landscape. It supports artifact promotion, revision history tracking, deployment validation, and environment-specific configurations.

### Synchronize API Artifacts

To sync API artifacts from SAP API Management:

1. Navigate to the **Project View**.
2. Under the **Build** section, click on **API Management**.

<figure><img src="../../.gitbook/assets/image (1761).png" alt=""><figcaption></figcaption></figure>

3. Click the **Synchronize** button to retrieve the available API artifacts based on the selected tab. The following artifact types are supported:

* **API Proxies**
* **Key Value Maps**
* **API\_Product**
* **API\_Providers**

4. These artifacts are retrieved from the registered SAP API Management environment and reflected within ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Sync History

To track previous synchronizations:

* Click on **Sync History** to view a detailed log of all synchronization activities performed within the project.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Artifact Actions**

Based on the type of artifact, the following actions are available:

* **Sync** – Re-fetch the latest version of the artifact.
* **Configure** – Modify environment-specific configuration parameters.
* **Revisions** – View available revisions of the artifact.
* **Deployment History** – Track deployment activity across stages.
* **Download** –Download the API Proxy as a ZIP file for backup or inspection.

#### **API Proxies**

The **API Proxies** section in ReleaseOwl allows users to view, synchronize, and configure API Proxy artifacts retrieved from the integrated SAP API Management environments.

**Sync**

The **Sync** option is used to fetch the latest version of API Proxy artifacts from the registered SAP API Management environment.

* Click **Sync** to refresh and retrieve the most up-to-date API Proxy definitions.
* This ensures that ReleaseOwl reflects the current state of artifacts across environments.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Configure**&#x20;

**Configure** means **setting up or modifying values** of an artifact so that it works correctly in a specific environment.

To configure an API Proxy artifact in ReleaseOwl:

1. Navigate to the **API Proxies** tab.
2. Locate the required API Proxy.
3. Click the **Actions** button.
4. Select **Configure**.&#x20;

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The **Development (Dev) environment is read-only** and does not allow modification.
{% endhint %}

**Updating Configuration Values**

To modify configuration values for non-Dev environments:

1. Click the **Edit (pencil) icon** next to the desired field.
2. Update the required parameters.
3. Click **Save** to persist changes.

<figure><img src="../../.gitbook/assets/image (1762).png" alt=""><figcaption></figcaption></figure>

**Target EndPoint Configuration**

Use the **Target EndPoint** tab to define and manage backend endpoint values for each named target endpoint.

1. Select the appropriate **Target Endpoint** from the dropdown.
2. Modify fields such as the following by using the **Edit (pencil)** icon next to each field.
3. Click the **Save** button to persist the changes for the selected target endpoint.

<figure><img src="../../.gitbook/assets/image (1763).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Definition:** A _**Target Endpoint**_ is the backend service to which the API Proxy forwards client requests. The client interacts with the proxy URL, and the request is internally routed to the defined target endpoint.
{% endhint %}

**Host Alias Configuration**

The **Host Alias** tab allows you to define environment-agnostic logical mappings for backend hostnames, enhancing flexibility during API deployments.

To configure host aliases:

1. Navigate to the **Host Alias** tab.
2. Click the **Edit** button.

<figure><img src="../../.gitbook/assets/image (1764).png" alt=""><figcaption></figcaption></figure>

3. In your target environment, multiple host aliases may be configured. If you want to deploy your API proxy to a specific host alias, you can specify the desired host alias in the **Configure** section.
4. Save your configuration by clicking the **Save** button.

<figure><img src="../../.gitbook/assets/image (1765).png" alt=""><figcaption></figcaption></figure>

**Revisions**

**Revisions** represent versioned snapshots of API Management artifacts in **ReleaseOw**l. Whenever changes are made such as updating configurations, modifying endpoints, policies, or attribute values and saved, a new revision is automatically created to capture those updates

To perform revisions, follow these steps:

* Click on the "**Revisions**" button.

<figure><img src="../../.gitbook/assets/image (1771).png" alt=""><figcaption></figcaption></figure>

Within the Revisions section, the following options are available:&#x20;

* **Compare Environments**
* **Compare Versions**
* **Assign User Story**
* **Unassign User Story**
* **Additional configuration actions**

**Compare Environments:**

The **Compare Environments** option allows you to compare the source version of an API Proxy in the **Source Environment** with the active version in the **Destination Environment**.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FPdexT8VHEZDfBq2D19UC%252Fimage.png%3Falt%3Dmedia%26token%3D8c5644ae-8a20-40ec-826a-e8052938a392&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=b6bbccfa&#x26;sv=2" alt=""><figcaption></figcaption></figure>

To initiate:

* Click **Compare Environments**
* Select the **Source Environment** and **Destination Environment**
* Click **Submit**

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FoJ3uJHTMEKqJRv5VhmcM%252Fimage.png%3Falt%3Dmedia%26token%3D56fcbae7-0d7c-4545-a403-2988dd5d711f&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=e37e1acd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Compare Versions**

The **Compare Versions** option in ReleaseOwl allows you to compare two different versions of an API Proxy artifact, enabling you to identify changes and analyze differences between versions before proceeding with further actions such as deployment or promotion.

To perform a comparison:

* Ensure that you select **two versions of the same artifact**.
* The system will highlight the differences between the selected versions, enabling you to track configuration changes effectively.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FRkO6GvCiNkKCRemzi7pp%252Fimage.png%3Falt%3Dmedia%26token%3Df181cc80-9f02-4481-948e-59629b7fc17d&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=1c477f81&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Assign User Story**

The **Assign User Story** option allows you to assign one or more user stories to yourself or another team member for better ownership and tracking. To assign, click on the **Assign User Story** button, select the required user stories from the list, and click **Assign User Story** again. In the assignment panel, choose the desired user from the dropdown list to complete the assignment.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FFdHuJFhntSmfW094CY1I%252Fimage.png%3Falt%3Dmedia%26token%3D6f76ec7b-b0c3-4f0d-8d78-6359dcfe9428&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=4f4451a4&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Unassign User Story**&#x20;

The **Unassign User Story** option allows you to remove the current assignment of one or more user stories. To unassign, click on the **Unassign User Story** button, select the required user stories from the list, and click **Unassign User Story** again to release them from their current assignees.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FUGFhKqdGhlEbG3bMhlSN%252Fimage.png%3Falt%3Dmedia%26token%3D3b04fc1b-ce32-4472-8931-a080a576883d&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=da499811&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Additionally, you can perform **configuration actions and download the selected API Proxy artifact as a ZIP file** within the Revisions section.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FIfAAuqDQE8zHewRe3GKa%252Fimage.png%3Falt%3Dmedia%26token%3Da1184e9d-ff65-4b21-9fe0-9d948a54f10d&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=f757838a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### API Provider

The **API Provider** section in **ReleaseOwl** is used to configure provider-specific parameters that define how API artifacts interact with backend services across different environments.

<figure><img src="../../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Sync**

The **Sync** option allows users to fetch the latest API Provider configurations from the registered SAP API Management environment.

* Click **Sync** to retrieve the most recent provider entries.
* This ensures that the configuration in **ReleaseOwl** is up to date with the source environment.

<figure><img src="../../.gitbook/assets/image (7) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Configure**

**Configure** means **setting up or modifying values** of an artifact so that it works correctly in a specific environment

To configure an API Provider in ReleaseOwl:

1. Navigate to the **API Provider** tab.
2. Select the required provider entry.
3. Click the **Actions** button.
4. Select **Configure**.

<figure><img src="../../.gitbook/assets/image (1768).png" alt=""><figcaption></figcaption></figure>

**Configuration Screen**

The configuration screen displays the API Provider entries across multiple environments (e.g., QA, Production) that are part of the deployment landscape. Each provider configuration is represented as **entries**, where environment-specific values can be maintained.

The **Provider Name** can be modified for the target environment during deployment using the **Edit** option, allowing environment-specific customization of the provider configuration.

For example, if the provider name in the **Dev** environment is _NorthWindProvider_, it can be updated for the **QA** environment to _NorthWindProvider\_QA_. During deployment, the provider will be created in the target environment with the updated name.

To modify configuration values for non-Dev environments:

1. Click the **Edit (pencil)** icon next to the desired field.
2. Update the required parameters.
3. Click **Save** to persist the changes.

{% hint style="info" %}
**Note:** If the provider includes authentication settings, these may be overridden in the target environment during deployment. After deployment, it is recommended to manually update the authentication details in the target environment.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (1772).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The **Development (Dev) environment is read-only** and cannot be modified.
{% endhint %}

#### Key Value Maps <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

The **Key Value Maps (KVM)** section in ReleaseOwl is used to manage environment-specific key-value pairs that are consumed by API Proxies at runtime. Each KVM consists of multiple **keys**, with corresponding **values maintained per environment** (e.g., Dev, QA, Prod).

<figure><img src="../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

**Sync**

The **Sync** option retrieves the latest KVM artifacts from the registered SAP API Management environment.

* Click **Sync** to refresh and fetch the most recent KVM definitions.
* Ensures **ReleaseOwl** reflects the current state of KVMs from the source system.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

**Configure**

**Configure** means **setting up or modifying values** of an artifact so that it works correctly in a specific environment.

To configure key Value Maps in ReleaseOwl:

1. Navigate to the **Key Value Map**s tab.
2. Select the required provider entry.
3. Click the **Actions** button.
4. Select **Configure**.

<figure><img src="../../.gitbook/assets/image (1769).png" alt=""><figcaption></figcaption></figure>

**Configuration Screen**

When a KVM is selected, the configuration is displayed under the **Entries** tab.

* Each row represents a **key.**
* Each column represents an **environment**&#x20;
* Values are maintained **per environment** for each key.

**Updating KVM Entries**

To update values:

1. Locate the required **key** in the Entries table.
2. Identify the target **environment column** (e.g., QA, Prod).
3. Click the **Edit (pencil) icon** under **Modify Values**.
4. Update the value directly in the editable field.
5. Click **Save** to persist the changes.

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

#### API Product

An **API Product** in ReleaseOwl represents a collection of API Proxies bundled together and exposed for consumption.

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

**Sync**

The **Sync** option is used to fetch the latest API Product artifacts from the registered SAP API Management environment.

* Click **Sync** to retrieve the most recent API Product definitions.
* Ensures that ReleaseOwl reflects the current state of API Products from the source system.

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

#### Configuring an API Product

To configure an API Product in ReleaseOwl:

1. Navigate to the **API Product** tab.
2. Select the required API Product.
3. Click the **Actions** button.
4. Select **Configure**.

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

#### Configuration

The configuration screen displays the API Product across multiple environments (e.g., Dev, QA, Production) that are part of the deployment landscape.

#### Custom Attributes

Within the **Configure** section, the **Custom Attributes** tab allows you to define and manage environment-specific attribute values.

* Each row represents an **attribute key** (e.g., `aa`, `bb`, `cc`).
* Each column represents an **environment** (e.g., Dev, QA, Prod).
* Values can be maintained independently per environment.

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

#### Updating Custom Attributes

To update attribute values:

1. Navigate to the **Custom Attributes** tab under **Configure**.
2. Locate the required attribute.
3. Click the **Edit (pencil) icon** under **Modify Values**.
4. Update the value in the desired environment column.
5. Click **Save** to persist the changes.

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

#### Revisions <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

**Revisions** represent versioned snapshots of API Management artifacts in ReleaseOwl. Whenever changes are made—such as updating configurations, modifying endpoints, policies, or attribute values—and saved, a new revision is automatically created to capture those updates. This applies to all supported artifacts, including:

* API Providers
* Key Value Maps (KVM)
* API Products

To perform revisions, follow these steps:

* Click on the "**Revisions**"  button.&#x20;

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

The following actions are available:

* **Assign User Story**
* **Unassign User Story**
* **Additional configuration actions**

**Assign User Story**

You can assign a user story to yourself or another team member for better ownership and tracking.\
To assign a user story, click on the **Assign User Story** button. Select the required user stories from the list, then click on **Assign User Story** again. In the assignment panel, choose the desired user from the dropdown list to complete the assignment.

<figure><img src="../../.gitbook/assets/image (1773).png" alt=""><figcaption></figcaption></figure>

**Unassign User Story**\
To remove the assignment of a user story, click on the **Unassign User Story** button. Select the required user stories from the list and click on **Unassign** **User Story** again to release them from their current assignees.

<figure><img src="../../.gitbook/assets/image (1774).png" alt=""><figcaption></figcaption></figure>

* Additionally, within the **Revisions** section, you can perform **configuration actions and download the selected API artifact as a ZIP file**.

<figure><img src="../../.gitbook/assets/image (13) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Deployment History

* Displays the recent deployment history of API Management artifacts in ReleaseOwl, including the artifact name, artifact type (API Proxy, API Provider, Key Value Map, API Product), associated user story, target environment, deployment timestamp, and deployment status, providing a consolidated and traceable view of deployment activities across all supported artifact types.

<figure><img src="../../.gitbook/assets/image (15) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Deploy Logs

* **Deploy Status**: Reflects the final deployment status of the API artifact to the target environment.
* **Already Deployed**: Indicates that the API artifact was previously deployed, either as part of a retry or through manual completion. This status helps avoid redundant deployments and ensures clarity during re-runs.

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

* **Manual Completion**: If a deployment fails in **ReleaseOwl**, but the artifact has been successfully deployed or addressed directly in the backend system (e.g., **SAP API Management**) through manual intervention, users can use the **Manual Completion** option in **ReleaseOwl** to mark the deployment step as completed.

**To perform manual completion:**

1. Click the **Mark as Complete** button to proceed with the pipeline.

<figure><img src="../../.gitbook/assets/image (19) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. After marking as complete, click the **Continue** button to resume the previously failed deployment stage.

<figure><img src="../../.gitbook/assets/image (20) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. You will see a confirmation that the **deployment has resumed successfully**.&#x20;

<figure><img src="../../.gitbook/assets/image (21) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. The **deployment status** will then update to **Completed**, indicating that the process finished successfully.&#x20;

<figure><img src="../../.gitbook/assets/image (22) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Retry Button**\
Allows users to retry a failed deployment or re-execute a failed stage of the pipeline.

<figure><img src="../../.gitbook/assets/image (23) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Deployment Notification

* After deploying the artifacts, you will receive a notification email containing the deployment details, including the user story ID, artifact type, version ID, and deployment status.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
