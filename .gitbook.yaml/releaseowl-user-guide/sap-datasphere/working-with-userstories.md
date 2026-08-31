# Working with UserStories

User Stories allow you to group and manage artifacts that are deployed together through a [Release Pipeline.](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/working-with-release-pipelines/use-cases/automated-cpi-deployments#creating-a-release-pipeline)

#### Creating a User Story

1. Navigate to the **Change Management** section.
2. Go to **User Stories**, click on the **Create New User Story**.

<figure><img src="../../.gitbook/assets/image (1383).png" alt=""><figcaption></figcaption></figure>

3. Enter the required details in the user story creation form.
4. Click **Create** to save the user story.

<figure><img src="../../.gitbook/assets/image (1379).png" alt=""><figcaption></figcaption></figure>

5. Once the User Story is created, it will appear in the list/grid view.
6. Click on the **Edit** next to the User Story entry.

<figure><img src="../../.gitbook/assets/image (2261).png" alt=""><figcaption></figcaption></figure>

#### SAP Datasphere Artifacts <a href="#cpi-artifacts" id="cpi-artifacts"></a>

Use this tab to add SAP Datasphere artifacts to the User Story.

**Adding SAP Datasphere Artifacts**

1. Open the required User Story.
2. Select the SAP Datasphere tab.
3. Click **Add**.

<figure><img src="../../.gitbook/assets/image (2259).png" alt=""><figcaption></figcaption></figure>

4. Select the required SAP Datasphere Packages.
5. Click **ADD** to add the selected packages to the User Story.

<figure><img src="../../.gitbook/assets/image (2260).png" alt=""><figcaption></figcaption></figure>

#### Import Settings <a href="#import-settings-cpi" id="import-settings-cpi"></a>

1. Click the **three-dot (More Actions)** menu.
2. Select **Import Settings**.

<figure><img src="../../.gitbook/assets/image (2262).png" alt=""><figcaption></figcaption></figure>

3. A pop-up message will appear, where you can enable the **Force Deploy** option. Click **Save** to apply the changes.

<figure><img src="../../.gitbook/assets/image (2258).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :  Force Deploy** — lets you redeploy the packages/artifacts again even if it was already deployed.

* When _Force Deploy_ is enabled, version validation checks do not block the deployment.
* If the target environment version is higher than the source environment version, a warning message is displayed.
{% endhint %}

### Deployment-Datasphere

1. Click **Promote** to start the deployment process.

<figure><img src="../../.gitbook/assets/image (1356).png" alt=""><figcaption></figcaption></figure>

2. If the Release Pipeline includes a **Deployment** task, monitor the deployment status of the User Story.
3. Click **Deploy Logs** to view the deployment details.

<figure><img src="../../.gitbook/assets/image (2265).png" alt=""><figcaption></figcaption></figure>

4. The deployment details are displayed in the **SAP Datasphere Deploy Logs** window with the following columns:

* **Deploy Status** – Reflects the final deployment status of the package. Click the status link to view the status details, including the Datasphere import job result and the error message in case of failure.

<div><figure><img src="../../.gitbook/assets/image (2267).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (2266).png" alt=""><figcaption></figcaption></figure></div>

* **Already Deployed** – Indicates that the package version was previously deployed, either during a retry operation or through manual completion. This status helps avoid duplicate deployments and provides clarity during re-runs.
* **Deployment Time  -** Date and time the deployment executed.
* **Version** - The package version that was deployed.
* **Manual Completion** – If a deployment fails or times out, users can use the Manual Completion option in ReleaseOwl to resolve the issue manually and continue the pipeline execution. Selecting **Mark as Complete** indicates that the package has been manually deployed in the target environment. ReleaseOwl records the deployment as completed — along with who completed it, when, and the reason — and continues the pipeline execution.
* **Refresh Button** – Fetches the latest Datasphere import job status from the target environment and updates the deployment status in the log.
* **Icon in Package Name** – An icon is displayed next to the package name to indicate that Force Deployment was applied, keeping version-validation overrides visible in the deployment history.

<figure><img src="../../.gitbook/assets/image (2266).png" alt=""><figcaption></figcaption></figure>

