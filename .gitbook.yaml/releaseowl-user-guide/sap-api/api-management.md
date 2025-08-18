# API Management

The **API Management** module in ReleaseOwl provides a comprehensive set of tools to streamline the management of SAP API artifacts. From synchronizing and configuring API proxies to tracking revisions and managing deployments across environments, this module ensures efficient control over your API landscape. It supports artifact promotion, revision history tracking, deployment validation, and environment-specific configurations.

### Synchronize API Artifacts

To sync API artifacts from SAP API Management:

1. Navigate to the **Project View**.
2. Under the **Build** section, click on **API Management (Beta)**.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Click the **Synchronize** button to fetch available API artifacts such as:

* **API Proxies**
* **Key Value Maps**

4. These artifacts are retrieved from the registered SAP API Management environment and reflected within ReleaseOwl.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fr4KtoIO20ImCAGwcK6au%252Fimage.png%3Falt%3Dmedia%26token%3D43630a07-dc32-4c99-a409-0317f552685d&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=22d3c421&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### Sync History

To track previous synchronizations:

* Click on **Sync History** to view a detailed log of all synchronization activities performed within the project.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Artifact Actions**

Based on the type of artifact, the following actions are available:

* **Sync** – Re-fetch the latest version of the artifact.
* **Configure** – Modify environment-specific configuration parameters.
* **Revisions** – View available revisions of the artifact.
* **Deployment History** – Track deployment activity across stages.
* **Download** –Download the API Proxy as a ZIP file for backup or inspection.

#### **Configure API Artifact Parameters**

You can define configuration parameters separately for each environment, and ReleaseOwl applies these automatically during deployment.

**To configure an API artifact:**

1. Navigate to the required artifact, click the **Actions** button, and select **Configure**.

<figure><img src="../../.gitbook/assets/image (1086).png" alt=""><figcaption></figcaption></figure>

2. The configuration screen displays the same API Proxy across different SAP API Management environments (such as QA, Prod, etc.) that are part of the deployment landscape.
3. **Note:** No changes can be made to the **Dev** environment.
4. To update parameters for other environments:
   * Click the **Edit (pencil)** icon next to each field.
   * Make the necessary changes.
   * Click **Save**.

<figure><img src="../../.gitbook/assets/image (1285).png" alt=""><figcaption></figcaption></figure>

#### Target EndPoints Configuration

Use the **Target EndPoint** tab to define and manage backend endpoint values for each named target endpoint.

1. Select the appropriate **Target Endpoint** from the dropdown.
2. Modify fields such as the following by using the **Edit (pencil)** icon next to each field:
   * `url`
   * `provider_id`
   * `relativePath`
   * `targetAPIProxyName`
3. Click the **Save** button to persist the changes for the selected target endpoint.

This configuration is deployed during the API Proxy deployment.

<figure><img src="../../.gitbook/assets/image (1286).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Definition:** A _**Target Endpoint**_ is the backend service to which the API Proxy forwards client requests. The client interacts with the proxy URL, and the request is internally routed to the defined target endpoint.
{% endhint %}

#### Host Alias Configuration <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

The **Host Alias** tab allows you to define environment-agnostic logical mappings for backend hostnames, enhancing flexibility during API deployments.

To configure host aliases:

1. Navigate to the **Host Alias** tab.
2. Click the **Edit** button.

<figure><img src="../../.gitbook/assets/image (16) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. In your target environment, multiple host aliases may be configured. If you want to deploy your API proxy to a specific host alias, you can specify the desired host alias in the **Configure** section.
4. Save your configuration by clicking the **Save** button.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Revisions <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

**Revisions** refer to versioned snapshots of an API Proxy. Every time you make changes—such as modifying endpoints, policies, or configurations—and save them, a new revision is automatically created to capture those updates.

To perform revisions, follow these steps:

* Click on the "**Revisions**"  button.&#x20;

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

The following actions are available:

* **Compare Environments**
* **Compare Versions**
* **Assign User Story**
* **Unassign User Story**
* **Additional configuration actions**

#### Compare Environments:&#x20;

The **Compare Environments** option allows you to compare the source version of an API Proxy or Product in the **Source Environment** with the active version in the **Destination Environment**.

<figure><img src="../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

To initiate:

* Click **Compare Environments**
* Select the **Source Environment** and **Destination Environment**
* Click **Submit**

<figure><img src="../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Compare Versions:&#x20;

The **Compare Versions** option allows you to compare two different versions of an API Proxy or Product. Ensure that you select **two versions** of the same artifact to perform the comparison.

<figure><img src="../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Assign User Story:&#x20;

You can assign a user story to yourself or another team member for better ownership and tracking.\
To assign a user story, click on the **Assign User Story** button. Select the required user stories from the list, then click on **Assign User Story** again. In the assignment panel, choose the desired user from the dropdown list to complete the assignment.

<figure><img src="../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Unassign User Story**:\
To remove the assignment of a user story, click on the **Unassign User Story** button. Select the required user stories from the list and click on **Unassign** **User Story** again to release them from their current assignees.

<figure><img src="../../.gitbook/assets/image (12) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Additionally, you can perform configuration actions within the **Revisions** section.

<figure><img src="../../.gitbook/assets/image (13) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Download <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

* You can download the API artifact as a ZIP file. The selected API artifact will be packaged and downloaded to your system.

<figure><img src="../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Deployment History

* Displays the recent deployments of API Proxy artifacts, including the artifact name, associated user story, target environment, deployment timestamp, and deployment status.

<figure><img src="../../.gitbook/assets/image (15) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Creating a Release Pipeline <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

**1. Create a New Release Pipeline**

* Navigate to **Release Pipelines**.
* Click **Create New Release Pipeline**.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Provide a **Pipeline Name**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F02Nu3sYI7jhLWH36mwUk%252Fimage.png%3Falt%3Dmedia%26token%3Db0546bb3-8bb9-4902-889b-4ac5022d1e6c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=18908539&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Add stages (e.g., QA, Prod) and assign tasks to each stage.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fp9bYnD6MU10rrjza1IzY%252Fimage.png%3Falt%3Dmedia%26token%3D7e30a12a-4061-483e-a9a2-06d82b9f2caf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3549c696&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**2. Add Deployment Tasks**

* Click the **Add** button in a task stage to include deployment tasks.
* Fill in the required details:
  * **Name:** Enter a preferred name for the deployment task.
  * **Deploy Type:** Select **API**.
  * **API Management:** Select the target API environment.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fqfn1WVRDYayxAzHAcdYs%252Fimage.png%3Falt%3Dmedia%26token%3D7c13f154-42df-4ac1-986f-0ebd12fb0d60&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ec530eef&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**3. Add Approval Tasks**

* Click the **Add** button in a task stage to include approval tasks.
* Fill in the required details:
  * **Name:** Enter a preferred name for the approval task.
  * **Assign To:** Select the user responsible for approval.
* Click **Save**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F9qsSsahluL3mHYz2eBGN%252Fimage.png%3Falt%3Dmedia%26token%3D626877d4-54bd-471b-a1c0-eccc21f0b96f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=13a93698&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Managing Sprints and User Stories <a href="#managing-sprints-and-user-stories" id="managing-sprints-and-user-stories"></a>

**1. Create a Sprint**

* In the **Project View**, navigate to **Change Management**.
* Click **Create Sprint**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F3CVWW53nDb3soqZIqCrY%252Fimage.png%3Falt%3Dmedia%26token%3D7e838dbf-d632-4afc-886a-eb43ca4d839f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2a39c1cd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Enter the **Sprint Name** and click **Save**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FI2BzhgyQLZNVN006mB9I%252Fimage.png%3Falt%3Dmedia%26token%3D85a9ddb4-d5e9-425b-9990-bbc8dbcffcef&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2e585e27&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click the **Actions button** and select **Start Sprint**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FGbN4NTGx6aVqmo7GXwEi%252Fimage.png%3Falt%3Dmedia%26token%3D776ccadc-9f28-4b62-bf6f-c7e842991a58&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=484b2198&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**2. Create a User Story**

* Go to **User Stories** and click **Create New User Story**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FHm3czXRNXBFSZcx6ys5U%252Fimage.png%3Falt%3Dmedia%26token%3D1023c3ec-4556-410d-8786-cd811d8c5211&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6adc500c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Fill in the required details:
  * **Summary:** Provide a summary of the user story.
  * **Type:** Select the type of story.
* Click **Save.**

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FBvxTjv7XdldRSJJBHnby%252Fimage.png%3Falt%3Dmedia%26token%3D68a7944e-0314-4b03-a671-fd9df56f77c2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b39208ce&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click the **Action button**, then select **Edit**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fz17Xyqtz5J6UIKiyIxTb%252Fimage.png%3Falt%3Dmedia%26token%3D821d067c-0253-44a5-b4bb-92baa2d72daa&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=18aa2e4e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**3. Manage API Management Artifacts**

* Go to **API Management Artifacts**.
* Click **+ Add** to add API Management artifacts.
* Select the **Release Pipeline and Component**.
* Click **Save**.

<figure><img src="../../.gitbook/assets/image (16) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FuFb66wSumGYiUFhTQUgY%252Fimage.png%3Falt%3Dmedia%26token%3D6b5f39c5-6af9-4aed-bf63-159cda51daf6&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d69ffe7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** You can **promote a user story** directly from the **Edit User Story** screen in ReleaseOwl.
{% endhint %}

* Click the Action **button**, then select **Promote**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FKkGYShxDsN9OOn3BmFFo%252Fimage.png%3Falt%3Dmedia%26token%3D2189903a-b0d7-40dd-b602-538814dc6f8f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1e7ba85a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* **Activity log:** The activity log helps track the progress of deployment tasks, identify any issues or failures, and maintain a record of who performed each action.

<figure><img src="../../.gitbook/assets/image (17) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**4. Approval Process**

* Before deployment, an **Approval Section** appears.
* The assigned user must approve/reject the task.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FeduWLKFqG2PRFJbl37rH%252Fimage.png%3Falt%3Dmedia%26token%3D8ab36408-58de-4741-8cc4-91dc3c21838f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=70a726b1&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Navigate to **My Tasks**.
* Click **Approve/Reject** in the **Actions** column.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FCOkGkJYxl0OQQdcNoDrD%252Fimage.png%3Falt%3Dmedia%26token%3D809ed910-948b-404c-ab6b-8bd747e4f574&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=16098f71&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**5. Deployment Monitoring**

* After approval, go to **Pipeline Activity**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fzc5Uiu3G65ApYmscGwW4%252Fimage.png%3Falt%3Dmedia%26token%3D7341562d-2449-4a4f-9eec-948a1da6d5e0&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=813b8eca&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Once the **Deployment Tasks** are marked as **Approved**, the deployment process begins. After completing the deployment, you can review the detailed **Deploy Logs.**

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FeEtLCYXQ1rREFPZyMOaW%252Fimage.png%3Falt%3Dmedia%26token%3Dc2cb8fcc-1c07-474b-85d2-e4e046e16343&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=62fc6563&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Deploy Logs

* **Deploy Status**: Reflects the final deployment status of the API artifact to the target environment.
* **Already Deployed**: Indicates that the API artifact was previously deployed, either as part of a retry or through manual completion. This status helps avoid redundant deployments and ensures clarity during re-runs.

<figure><img src="../../.gitbook/assets/image (18) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* **Manual Completion**: If a deployment fails in **ReleaseOwl**, but the artifact has been successfully deployed or addressed directly in the backend system (e.g., **SAP API Management**) through manual intervention, users can use the **Manual Completion** option in **ReleaseOwl** to mark the deployment step as completed.

**To perform manual completion:**

1. Click the **Mark as Complete** button to proceed with the pipeline.

<figure><img src="../../.gitbook/assets/image (19) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. After marking as complete, click the **Continue** button to resume the previously failed deployment stage.

<figure><img src="../../.gitbook/assets/image (20) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. You will see a confirmation that the **deployment has resumed successfully**.&#x20;

<figure><img src="../../.gitbook/assets/image (21) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. The **deployment status** will then update to **Completed**, indicating that the process finished successfully.&#x20;

<figure><img src="../../.gitbook/assets/image (22) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Retry Button**\
Allows users to retry a failed deployment or re-execute a failed stage of the pipeline.

<figure><img src="../../.gitbook/assets/image (23) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Deployment Notification

* After deploying the artifacts, you will receive a notification email containing the deployment details, including the user story ID, artifact type, version ID, and deployment status.

<figure><img src="../../.gitbook/assets/image (24) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
