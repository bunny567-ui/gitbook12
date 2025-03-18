# Automated MTAR Deployments

**Release Pipeline**

Release Pipelines enable you to orchestrate deployments into SAP environments with right approvals in place.

Release Pipeline can be created with one or more stages.

Each stage will correspond to automated deployment of mtar application to SAP BTP subaccount with a sequence of activities such as tasks related to approvals, manual changes, deployments, callouts and tests execution

{% hint style="info" %}
**Note:** You can create a multi-stage pipeline for continuous deployment across various environments one after the other towards continuous delivery of application all through Dev - QA - Staging - Production.
{% endhint %}

**Creating a Release Pipeline**

Creating a Release Pipeline is a six-step process.

| Step1 | Enter a name in Release Pipeline Name                                                                                       |
| ----- | --------------------------------------------------------------------------------------------------------------------------- |
| Step2 | Choose Pipeline Type – SAP BTP or SAP HANA XSA (MTAR) from the drop down                                                    |
| Step3 | The dropdown contains all the build pipelines of type MTAR. Choose the build pipeline whose mtar artifact must be deployed. |
| Step4 | Click Add Stages, add the stages. Add various types of pre, post and deployment tasks on need basis.                        |
| Step5 | Choose to schedule the pipeline execution or run manually                                                                   |
| Step6 | Specify the email ids to receive notifications about release pipeline execution status.                                     |

### To create a release pipeline:

In **Release**, go to **Release Pipelines.**\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-1.jpg" alt=""><figcaption></figcaption></figure>

Click **Create New Release Pipeline.**

1\. **Release Pipeline Name:** Give a name for the release pipeline.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-2.jpg" alt=""><figcaption></figcaption></figure>

2\. **Pipeline Type:** For **SAP Cloud (MTAR)** project, the Pipeline Type appears SAP BTP **(MTAR)** by default and is read-only.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-3.jpg" alt=""><figcaption></figcaption></figure>

For **SAP HANA XSA (MTAR)** project, the Pipeline Type appears **SAP HANA XSA (MTAR)** by default and is read-only.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-4.jpg" alt=""><figcaption></figcaption></figure>

3\. **Artifact Source:** The dropdown contains all the build pipelines of type MTAR. Choose the build pipeline with the necessary artifacts to be deployed in the environment.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-5.jpg" alt=""><figcaption></figcaption></figure>

4\. **Add Stages:** Click Add Stage and enter the stage name say for e.g., UAT or QA where the deployement has to be carried out and click OK.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-6.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-7.jpg" alt=""><figcaption></figcaption></figure>

The newly added stage appears as follows:

<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-8.jpg" alt=""><figcaption></figcaption></figure>

**Note:** To remove any stage, click Remove Stage button.

**Tasks:** Click Add to enter any tasks that are to be performed as desired. (Deployment, Approvals, Manual Task, Callout, Test Execution and User Story Status Update)

**Note:** Deployment Task varies for different project types.

**Deployment Task** – All the details pertaining to the deployment of the artifact is specified in deployment task.

The following screen is displayed on adding a deployment task.\


<figure><img src="../../.gitbook/assets/image (365).png" alt=""><figcaption></figcaption></figure>

**Cloud Transport Management**

SAP Cloud Transport Management service allows you to manage the transport of development artifacts and application-specific content between different SAP BTP accounts.

Further information on Cloud Transport Management System can be found at [https://help.sap.com/docs/TRANSPORT\_MANAGEMENT\_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/5fef9d6b1cb047b2b18d9eb57aa15352.html](https://help.sap.com/docs/TRANSPORT_MANAGEMENT_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/5fef9d6b1cb047b2b18d9eb57aa15352.html)

Select the option Upload Artifact to Cloud Transport Management if the artifact has to be uploaded to any other BTP environment.

The following screen is displayed.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-10.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Select Environment** | Select an environment from the available list of registered SAP BTP environments where the deployment has to take place.                   |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Service Instance**   | Select the Service Instance from the available service instances listed in the dropdown.                                                   |
| **Service Key**        | Select the Service Key from the available service keys listed in the dropdown.                                                             |
| **Node Name**          | Enter a node name added in the Cloud Transport Management System corresponding to the environment to which the artifact is to be uploaded. |

\


5\. **Schedule:** You can execute a Release Pipeline either manually or can schedule it to get executed automatically once its reference build pipeline gets executed successfully.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-11.jpg" alt=""><figcaption></figcaption></figure>

6\. **Notification Emails:** You can specify an email distribution list separated by comma who you want to notify the result of the Release Pipeline Execution – either Success or Failure.

**Note:** If the Release Pipeline fails, the logs are also attached in the notification email. By default, the user who creates the Release Pipeline is notified and specifying the distribution list is optional.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-12.jpg" alt=""><figcaption></figcaption></figure>

On clicking Save, the release pipeline gets created and is shown in the Release Pipelines screen.

**Multi-Stage Release Pipeline**

Any number of stages can be added while creating a release pipeline. An existing release pipeline can also be edited to include various stages.

This is required when we want the deployments to take place in multiple environments one after the other continuously which is a part of Continuous Delivery.

For each stage, the tasks are to be added separately. This corresponds to the tasks that are to be performed in that particular environment for the deployment to take place and the required actions that are to be taken.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-13.jpg" alt=""><figcaption></figcaption></figure>

**Editing/ Deleting Pipeline**

Go to the required pipeline and click **Edit** to edit the pipeline or **Delete** to delete the pipeline.

**Running a Release Pipeline**

Once a release pipeline is created, you can run multiple iterations to deploy MTAR artifacts.

To run a release pipeline:

1\. Once you create a release package, go to **Release**, and click **Release Pipeline.**

2\. Choose the required release pipeline to be run and click **Run.**\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-14.jpg" alt=""><figcaption></figcaption></figure>

3\. A pop-up appears. Enter a **Cycle Name** and **Select build** from the drop down.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-15.jpg" alt=""><figcaption></figcaption></figure>

4\. Click **Trigger Pipeline.** A message is displayed, about successful creation of a release pipeline. Click OK.

The following screen is displayed:\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-16.jpg" alt=""><figcaption></figcaption></figure>

5\. Click **Refresh.** Click on the required build to view a list of the triggered cycle.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-17.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-18.jpg" alt=""><figcaption></figcaption></figure>

Click on the required cycle to view its details.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-19.jpg" alt=""><figcaption></figcaption></figure>

Click **Logs¸** to view the logs of this cycle. You can even download the logs by clicking the Download Dmol Log link.\


<figure><img src="../../.gitbook/assets/image (366).png" alt=""><figcaption></figcaption></figure>

Click Errors, to view the errors that resulted in the deployment failure.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-21.jpg" alt=""><figcaption></figcaption></figure>

To view more error details, click View Details.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-22.jpg" alt=""><figcaption></figcaption></figure>

For a multi-stage Release Pipeline, the execution details of a test cycle in each environment will be shown one after the other in the order of their addition while creating the release pipeline.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-23.jpg" alt=""><figcaption></figcaption></figure>

Click Deployment Changes to know which user story is associated with a Release Pipeline and which artifacts are a part of it.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-mtar-deployments-24.jpg" alt=""><figcaption></figcaption></figure>

**Editing/ Deleting a Release Pipeline**

Go to the required pipeline in **Release Pipeline** page and click **Edit** to edit the pipeline or **Delete** to delete the pipeline.
