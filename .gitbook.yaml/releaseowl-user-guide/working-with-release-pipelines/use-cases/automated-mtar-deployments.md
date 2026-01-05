# Automated MTAR Deployments

### Release Pipeline

Release Pipelines enable you to orchestrate deployments into SAP environments with right approvals in place. It can be created with one or more stages. Each stage will correspond to automated deployment of mtar application to SAP BTP subaccount with a sequence of activities such as tasks related to approvals, manual changes, deployments, callouts and tests execution

{% hint style="info" %}
**Note:** You can create a multi-stage pipeline for continuous deployment across various environments one after the other towards continuous delivery of application all through Dev - QA - Staging - Production.
{% endhint %}

### Creating a Release Pipeline

Creating a Release Pipeline is a guided **five-step process**, designed to help you define and configure all necessary stages and parameters for end-to-end deployment automation.

| Step1- Release Pipeline Name  | Enter a name in Release Pipeline Name                                                                                                                             |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Step2 - Artifact Source       |  The dropdown contains all the build pipelines of type MTAR. Choose the build pipeline whose mtar artifact must be deployed.                                      |
| Step3 - Add Stages            | Click on _**Add Stages**_ and add the required stages. Based on your needs, you can add different types of pre-deployment, deployment, and post-deployment tasks. |
| Step4 - Triggers              | Choose to schedule the pipeline execution or run manually.                                                                                                        |
| Step5 - Notification Email(s) | Specify the email ids to receive notifications about release pipeline execution status.                                                                           |

**To create a release pipeline:**

1. In **Release**, go to **Release Pipelines.**
2. Click **Create New Release Pipeline.**<br>

<figure><img src="../../../.gitbook/assets/image (1230).png" alt=""><figcaption></figcaption></figure>

3. **Release Pipeline Name:** Give a name for the release pipeline.<br>

<figure><img src="../../../.gitbook/assets/image (1229).png" alt=""><figcaption></figcaption></figure>

4. **Artifact Source:** The dropdown contains all the build pipelines of type **MTAR**. Choose the build pipeline with the necessary artifacts to be deployed in the environment.<br>

<figure><img src="../../../.gitbook/assets/image (1231).png" alt=""><figcaption></figcaption></figure>

5. **Add Stages:** Click **Add Stage** and enter the stage name say for e.g., UAT or QA where the deployment has to be carried out and click **OK.**

<figure><img src="../../../.gitbook/assets/image (1237).png" alt=""><figcaption></figcaption></figure>

The newly added stage appears as follows:

<figure><img src="../../../.gitbook/assets/image (1238).png" alt=""><figcaption></figcaption></figure>

**Note:** To remove any stage, click **Remove Stage** button.

**Tasks:** Click Add to enter any tasks that are to be performed as desired. (Deployment, Approvals, Manual Task, Callout, Test Execution and User Story Status Update)

<figure><img src="../../../.gitbook/assets/image (1239).png" alt=""><figcaption></figcaption></figure>

**Note:** Deployment Task varies for different project types.

### **Deployment Task** –&#x20;

All the details pertaining to the deployment of the artifact is specified in deployment task. The following screen is displayed on adding a deployment task.

<figure><img src="../../../.gitbook/assets/image (1240).png" alt=""><figcaption></figcaption></figure>

**Cloud Transport Management**

* SAP Cloud Transport Management service allows you to manage the transport of development artifacts and application-specific content between different SAP BTP accounts.

{% hint style="info" %}
**Note:** Further information on Cloud Transport Management System can be found at [https://help.sap.com/docs/TRANSPORT\_MANAGEMENT\_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/5fef9d6b1cb047b2b18d9eb57aa15352.html](https://help.sap.com/docs/TRANSPORT_MANAGEMENT_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/5fef9d6b1cb047b2b18d9eb57aa15352.html)
{% endhint %}

* Select the option **Upload Artifact** to Cloud Transport Management if the artifact has to be uploaded to any other BTP environment.

The following screen is displayed.<br>

<figure><img src="../../../.gitbook/assets/image (1241).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Select Environment** | Select an environment from the available list of registered SAP BTP environments where the deployment has to take place.                   |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Service Instance**   | Select the Service Instance from the available service instances listed in the dropdown.                                                   |
| **Service Key**        | Select the Service Key from the available service keys listed in the dropdown.                                                             |
| **Node Name**          | Enter a node name added in the Cloud Transport Management System corresponding to the environment to which the artifact is to be uploaded. |

6. **Trigger:** You can trigger a Release Pipeline either **Manually** or on **Successful Build** it to get triggered automatically once its reference build pipeline gets executed successfully.

<figure><img src="../../../.gitbook/assets/image (1242).png" alt=""><figcaption></figcaption></figure>

7. **Notification Emails:** You can specify an email distribution list separated by comma who you want to notify the result of the Release Pipeline Execution – either **Success** or **Failure**. <br>

{% hint style="info" %}
**Note:** If the Release Pipeline fails, the logs are also attached in the notification email. By default, the user who creates the Release Pipeline is notified and specifying the distribution list is optional.
{% endhint %}



8. On clicking Save, the release pipeline gets created and is shown in the Release Pipelines screen.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Multi-Stage Release Pipeline**

Any number of stages can be added while creating a release pipeline. An existing release pipeline can also be edited to include various stages. This is required when we want the deployments to take place in multiple environments one after the other continuously which is a part of Continuous Delivery. For each stage, the tasks are to be added separately. This corresponds to the tasks that are to be performed in that particular environment for the deployment to take place and the required actions that are to be taken.<br>

<figure><img src="../../../.gitbook/assets/image (1243).png" alt=""><figcaption></figcaption></figure>

**Running a Release Pipeline**

Once a release pipeline is created, you can run multiple iterations to deploy MTAR artifacts.

To run a release pipeline:

1\. Once you create a release package, go to **Release**, and click **Release Pipeline.**

2\. Choose the required release pipeline to be run and click **Run.**

<figure><img src="../../../.gitbook/assets/image (1245).png" alt=""><figcaption></figcaption></figure>

3\. A pop-up appears. Enter a **Cycle Name** and **Select build** from the drop down.

<figure><img src="../../../.gitbook/assets/image (1246).png" alt=""><figcaption></figcaption></figure>

4\. Click **Trigger Pipeline.** A message is displayed, about successful creation of a release pipeline. Click OK. The following screen is displayed:

<figure><img src="../../../.gitbook/assets/image (1440).png" alt=""><figcaption></figcaption></figure>

5\. Click **Refresh.** Click on the required build to view a list of the triggered cycle.

<figure><img src="../../../.gitbook/assets/image (1441).png" alt=""><figcaption></figcaption></figure>

6. Click on the arrow button to expand the required cycle and view its details.

<figure><img src="../../../.gitbook/assets/image (1443).png" alt=""><figcaption></figcaption></figure>

7. Click **Logs¸** to view the logs of this cycle. You can even download the logs by clicking the **Download Dmol Log link.**

<figure><img src="../../../.gitbook/assets/image (1444).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1446).png" alt=""><figcaption></figcaption></figure>

8. Click **Errors**, to view the errors that resulted in the deployment failure.

<figure><img src="../../../.gitbook/assets/image (1251).png" alt=""><figcaption></figcaption></figure>

9. To view more error details, click **View Details**.<br>

<figure><img src="../../../.gitbook/assets/image (1252).png" alt=""><figcaption></figcaption></figure>

10. For a multi-stage Release Pipeline, the execution details of a test cycle in each environment will be shown one after the other in the order of their addition while creating the release pipeline.<br>

<figure><img src="../../../.gitbook/assets/image (1253).png" alt=""><figcaption></figcaption></figure>

11. Click **Deployment Changes** to know which user story is associated with a Release Pipeline and which artifacts are a part of it.<br>

<figure><img src="../../../.gitbook/assets/image (1254).png" alt=""><figcaption></figcaption></figure>

**Editing a Release Pipeline**

Go to the required pipeline in **Release Pipeline** page and click **Edit** to edit the pipeline.&#x20;

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
