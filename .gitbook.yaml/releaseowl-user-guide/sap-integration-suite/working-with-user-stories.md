# Working with User Stories

User Stories allow you to group and manage artifacts that are deployed together through a [Release Pipeline](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/working-with-release-pipelines/use-cases/automated-cpi-deployments). You can associate artifacts from different SAP Integration Suite services, such as Cloud Integration (CPI), Integration Advisor, API Management, and B2B Scenarios, with a single User Story.

### Creating a User Story

1. Navigate to **Change Management** and click on **User Stories**.

<figure><img src="../../.gitbook/assets/image (2071).png" alt=""><figcaption></figcaption></figure>

2. Click **Create New User Story**.
3. Enter the required details in the user story creation form.
4. Click **Create** to save the user story.

<figure><img src="../../.gitbook/assets/image (2072).png" alt=""><figcaption></figcaption></figure>

5. Click the **Actions** button and select **Edit**.

<figure><img src="../../.gitbook/assets/image (2081).png" alt=""><figcaption></figcaption></figure>

### CPI Artifacts

Use this tab to add SAP Cloud Integration (CPI) artifacts to the User Story.

#### Adding CPI Artifacts

1. Open the required User Story.
2. Select the **CPI Artifacts** tab.
3. Click **Add**.

<figure><img src="../../.gitbook/assets/image (2082).png" alt=""><figcaption></figcaption></figure>

4. Select the required CPI artifacts.
5. Click **OK** to add the selected CPI Artifacts to the User Story.

<figure><img src="../../.gitbook/assets/image (2083).png" alt=""><figcaption></figcaption></figure>

### Integration Advisor Artifacts

Use this tab to associate **Integration Advisor** artifacts with the User Story. These artifacts are promoted through the Release Pipeline along with other integration artifacts.

#### Adding Integration Advisor Artifacts

1. Open the required User Story.
2. Select the **Integration Advisor Artifacts** tab.
3. Click **Add**.

<figure><img src="../../.gitbook/assets/image (2086).png" alt=""><figcaption></figcaption></figure>

4. From the **Artifact Type** dropdown, select the required artifact type:
   * **MAGs**
   * **MIGs**
5. Select the required artifacts from the available list.
6. The selected artifacts are displayed in the **Selected Artifacts** section.

<figure><img src="../../.gitbook/assets/image (2092).png" alt=""><figcaption></figcaption></figure>

7. Click **OK** to add the selected Integration Advisor Artifacts to the User Story.

<figure><img src="../../.gitbook/assets/image (2087).png" alt=""><figcaption></figcaption></figure>

### API Management Artifacts

Use this tab to associate **API Management** artifacts with the User Story. The selected API Management artifacts are deployed through the configured Release Pipeline.

#### Adding API Management Artifacts

1. Open the required User Story.
2. Select the **API Management Artifacts** tab.
3. Click **Add**.
4. From the **Artifact Type** dropdown, select the required artifact type:
   * **API Proxies**
   * **API Providers**
   * **Key Value Maps**
   * **Products**
5. Select the required artifacts from the available list.
6. The selected artifacts are displayed in the **Selected Artifacts** section.

<figure><img src="../../.gitbook/assets/image (2090).png" alt=""><figcaption></figcaption></figure>

7. Click **OK** to add the selected API Management artifacts to the User Story.

<figure><img src="../../.gitbook/assets/image (2091).png" alt=""><figcaption></figcaption></figure>



### B2B Scenarios Artifacts

Use this tab to add the agreements/partner directory configuration with the User Story. The selected artifacts are deployed through the configured Release Pipeline.

#### Adding  Artifacts

1. Open the required User Story.
2. Select the **B2B Scenarios** tab.
3. Click **Add**.
4. From the **Artifact Type** dropdown, select the required artifact type:
   * **Agreements**
   * **Partner Directory Configuration**
5. Select the required artifacts from the available list.
6. The selected artifacts are displayed in the **Selected Artifacts** section.

<figure><img src="../../.gitbook/assets/image (2093).png" alt=""><figcaption></figcaption></figure>

Click **OK** to add the selected B2B Scenarios to the User Story.

<figure><img src="../../.gitbook/assets/image (2094).png" alt=""><figcaption></figcaption></figure>

### Attachments

The **Attachments** section allows you to add supporting files or external links to the User Story.

* Click **Browse File**.
* Upload the required file or provide the external link.
* Click **Upload File** to attach the file or link to the User Story.

<figure><img src="../../.gitbook/assets/image (2102).png" alt=""><figcaption></figcaption></figure>

### Import Settings- CPI

1. Click the **three-dot (More Actions)** menu.
2. Select **Import Settings**.

<figure><img src="../../.gitbook/assets/image (2074).png" alt=""><figcaption></figcaption></figure>

3. A pop-up message will appear, where you can enable the **Force Deploy** option. Click **Save** to apply the changes.

<figure><img src="../../.gitbook/assets/image (2076).png" alt=""><figcaption></figcaption></figure>

### Import Settings- Integration Advisor

1. Click the **three-dot (More Actions)** menu.
2. Select **Import Settings**.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

3. A pop-up message will appear, where you can enable the **Force Deploy** option. Click **Save** to apply the changes.

<figure><img src="../../.gitbook/assets/image (2155).png" alt=""><figcaption></figcaption></figure>

### Import Settings- API

1. Click the **three-dot (More Actions)** menu.
2. Select **Import Settings**.

<figure><img src="../../.gitbook/assets/image (2157).png" alt=""><figcaption></figcaption></figure>

3. A pop-up message will appear, where you can enable the **Force Deploy** option. Click **Save** to apply the changes.

<figure><img src="../../.gitbook/assets/image (2156).png" alt=""><figcaption></figcaption></figure>

### Import Settings- B2B Scenarios&#x20;

1. Click the **three-dot (More Actions)** menu.
2. Select **Import Settings**.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

3.  **Agreements:** A pop-up window appears where you can enable the **Force Deploy** option and configure the **Import Options** according to the target environment. Click **Save** to apply the configured settings.

    **Partner Directory Configuration:** A pop-up window appears where you can enable the **Force Deploy** option. Configure Import Options are not available for Partner Directory Configuration. Click **Save** to apply the configured settings.

<div><figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (2158).png" alt=""><figcaption></figcaption></figure></div>

{% hint style="info" %}
Note : **Force Deploy** — lets you redeploy the artifacts/agreements again even if it was already deployed.

* When _Force Deploy_ is enabled, version validation checks do not block the deployment.
* If the target environment version is higher than the source environment version, a warning message is displayed.
{% endhint %}

### Deployment -CPI

1. Click **Promote** to start the deployment process.

<figure><img src="../../.gitbook/assets/image (2084).png" alt=""><figcaption></figcaption></figure>

2. If the Release Pipeline includes a **Deployment** task, monitor the deployment status of the User Story.
3. Click **Deploy Logs** to view the deployment details.

<figure><img src="../../.gitbook/assets/image (2080).png" alt=""><figcaption></figcaption></figure>

4. The deployment details are displayed in the **SAP CPI Deploy Logs** window with the following columns:

* **Upload Status** – Indicates whether the artifact was successfully uploaded.
* **Config Status** – Confirms whether the configuration for new or updated artifacts was completed successfully.
* **Deploy Status** – Reflects the final deployment status of the artifact.
* **Already Deployed** – Indicates that the artifact was previously deployed, either during a retry operation or through manual completion. This status helps avoid duplicate deployments and provides clarity during re-runs.
* **Manual Completion** – If a deployment fails or times out, users can use the Manual Completion option in ReleaseOwl to resolve the issue manually and continue the pipeline execution. Selecting **Mark as Complete** indicates that the artifact has been manually completed in the target environment. ReleaseOwl records the deployment as completed and continues the pipeline execution.
* **Refresh Button** – Fetches the CPI runtime artifact deployment status and updates the runtime status in the deployment log.
* **Icon in Artifact Name** - An icon is displayed in the Deployment Logs section next to the artifact name to indicate that **Force Deployment** was applied.

<figure><img src="../../.gitbook/assets/image (2079).png" alt=""><figcaption></figcaption></figure>

### **Deployment-Integration Advisor**

The deployment details are displayed in the **SAP Integration Advisor Deploy Logs** window with the following columns:

* **Integration Artifact Name** – Displays the name of the Integration Advisor artifact selected for deployment.
* **Version** – Indicates the version of the Integration Advisor artifact being deployed.
* **Deploy Status** – Reflects the current deployment status of the Integration Advisor artifact.
* **Icon in Artifact Name** - An icon is displayed in the Deployment Logs section next to the artifact name to indicate that **Force Deployment** was applied.
* **Info** – Displays additional information about the deployed artifact.
  * **For MAG :** Displays the **Message Type** details and **Administrative Data**.
  * **For MIG :** Displays the **Source MIG**, **Target MIG**, and **Administrative Data**.

<figure><img src="../../.gitbook/assets/image (2097).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (2098).png" alt=""><figcaption></figcaption></figure>

* **Already Deployed** – Indicates that the artifact was previously deployed, either during a retry operation or through manual completion. This status helps avoid duplicate deployments and provides clarity during deployment re-runs.
* **Manual Completion** – If a deployment fails or times out, users can use the **Manual Completion** option in ReleaseOwl to manually update the deployment status and continue the pipeline execution. Selecting **Mark as Complete** indicates that the artifact has been manually completed in the target environment. ReleaseOwl records the deployment as completed and continues the pipeline execution.

<figure><img src="../../.gitbook/assets/image (2096).png" alt=""><figcaption></figcaption></figure>

### **Deployment-API Management**

The deployment details are displayed in the **API Management** window with the following columns:

* **Version** – Indicates the version of the API Management artifact being deployed.
* **Deploy Status** – Reflects the current deployment status of the API Management artifact.
* **Icon in Artifact Name** - An icon is displayed in the Deployment Logs section next to the artifact name to indicate that **Force Deployment** was applied.
* **Already Deployed** – Indicates that the artifact was previously deployed, either during a retry operation or through manual completion. This status helps avoid duplicate deployments and provides clarity during re-runs.
* **Manual Completion** – If a deployment fails or times out, users can use the Manual Completion option in ReleaseOwl to resolve the issue manually and continue the pipeline execution. Selecting **Mark as Complete** indicates that the artifact has been manually completed in the target environment. ReleaseOwl records the deployment as completed and continues the pipeline execution.
* **Refresh Button** – Fetches the CPI runtime artifact deployment status and updates the runtime status in the deployment log.
* **User Story -** Displays the ID of the User Story associated with the deployment.

<figure><img src="../../.gitbook/assets/image (2099).png" alt=""><figcaption></figcaption></figure>

### **Deployment-B2B Scenarios**&#x20;

The deployment details are displayed in the **B2B Scenarios Deploy Logs** window with the following columns:

* **Artifact Name** – Displays the name of the B2B scenario artifact being deployed.
* **Type** – Indicates the type of B2B scenario artifact, such as **Agreements** or **Partner Directory Configuration**.
* **Version** – Displays the version of the artifact being deployed.
* **Import Status** – Indicates the import status of the artifact in the target tenant. Click the **Import Status** icon to view the corresponding **deployment logs** and review the details of the import operation.

<div><figure><img src="../../.gitbook/assets/image (2151).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (2150).png" alt=""><figcaption></figcaption></figure></div>

* **Activate Agreement Status** – Indicates the activation status of the Agreement in the target environment. This field is applicable only to **Agreement** artifacts. For **Partner Directory Configuration** artifacts, the value is displayed as **N/A**.

<div><figure><img src="../../.gitbook/assets/image (2152).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (2153).png" alt=""><figcaption></figcaption></figure></div>

* **Deployment Time** – Displays the date and time when the deployment was completed.
* **Already Deployed** – Indicates that the artifact was previously deployed, either during a retry operation or through manual completion. This status helps avoid duplicate deployments and provides clarity during deployment re-runs.
* **Manual Completion** – If a deployment fails or times out, use the **Manual Completion** option to manually mark the deployment as completed and continue the pipeline execution.

{% hint style="info" %}
**Note:** Selecting **Mark as Complete** indicates that the artifact has been manually completed in the target environment. ReleaseOwl records the deployment as completed and continues the pipeline execution.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (2100).png" alt=""><figcaption></figcaption></figure>
