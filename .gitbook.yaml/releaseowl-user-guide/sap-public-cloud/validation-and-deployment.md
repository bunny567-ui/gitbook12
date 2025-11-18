# Validation and Deployment

#### **1. Validation Report**

The Validation Report is generated when a Validation Task is executed in the pipeline. It provides insights into whether the S/4HANA Public Cloud artifacts (Transports or Software Collections) meet the required conditions before deployment.

* Click on the **Validation Report**  to open it.&#x20;

<figure><img src="../../.gitbook/assets/image (1557).png" alt=""><figcaption></figcaption></figure>

* The report shows the overall validation status as either **Success** or **Failed**. Along with the status, the report also displays important artifact details such as:
  * **Artifact ID**
  * **Description**
  * **Version**
  * **Import Status**
* **Checking Details**
  * If the status is _Failed_, you can find out why it failed by hovering over the failed status.

<figure><img src="../../.gitbook/assets/image (1531).png" alt=""><figcaption></figcaption></figure>

**Public Cloud Dependency Report**

* The report displays the Artifact ID along with its dependent user stories, where the artifact is assigned to a user story.&#x20;

<figure><img src="../../.gitbook/assets/image (1559).png" alt=""><figcaption></figcaption></figure>

#### **2. Deployment Logs**

The Deployment Logs are generated during the execution of a Deployment Task and provide full traceability of the deployment process.

* Click on the _**Deploy Logs**_ to open it .

<figure><img src="../../.gitbook/assets/image (1558).png" alt=""><figcaption></figcaption></figure>

*   **The report includes the following sections:**

    * **Already Deployed** → Provides details of the artifacts that were previously deployed and skipped during execution.
    * **Manual Completion** → Provides details of the deployments that were marked as completed manually instead of through automated execution.

    <figure><img src="../../.gitbook/assets/image (1612).png" alt=""><figcaption></figcaption></figure>
