# Automated CPI Deployments

### **Release Pipelines**

Release Pipelines in ReleaseOwl facilitate orchestrated deployments to SAP environments with structured approval workflows. A pipeline can consist of one or more stages, each representing a deployment phase (e.g., Dev, QA, Prod). Within each stage, users can define a sequence of actions including approval tasks, manual interventions, deployment steps, external callouts, and automated test executions—ensuring controlled and auditable releases across the landscape.

{% hint style="info" %}
**Note:** You can create a multi-stage pipeline for continuous deployment across various environments one after the other towards continuous delivery of application all through Dev - QA - Staging - Production.
{% endhint %}

### **Creating a Release Pipeline**

Creating a Release Pipeline is a six-step process.

| Step1 | Enter a name in Release Pipeline Name                                                                |
| ----- | ---------------------------------------------------------------------------------------------------- |
| Step2 | Choose Pipeline Type – SAP CPI from the drop down                                                    |
| Step3 | Click Add Stages, add the stages. Add various types of pre, post and deployment tasks on need basis. |
| Step4 | Choose to schedule the pipeline execution or run manually                                            |
| Step5 | Specify the email ids to receive notifications about release pipeline execution status.              |

#### **For creating release pipeline:**

1. Select the required CPI Project.
2. Navigate to **Release and** click on the **Release Pipelines.**

<figure><img src="../../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Enter a **Pipeline Name**.
4. Click **Create New Release Pipeline**.

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

5. Click **Add Stage**.

<figure><img src="../../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

6. Enter the stage name say for e.g., UAT or QA where the deployment has to be carried out and click OK.\


<figure><img src="../../../.gitbook/assets/image (382).png" alt=""><figcaption></figcaption></figure>

7. **Tasks:** Click Add to enter any tasks that are to be performed

<figure><img src="../../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** To remove any stage, click Remove stage button.
{% endhint %}

8. Different tasks that can be added are as follows:\


<figure><img src="../../../.gitbook/assets/image (14) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** All the tasks except Deployment Task are similar for any project type. For CPI projects, Wait for Promotion and Validation tasks are the two extra tasks available other than the ones available for every project type.
{% endhint %}

### **Deployment Task**

All the details pertaining to the deployment of the artifact is specified in the deployment task. The following screen is displayed on adding a deployment task. The various Deployment Actions that can be performed are as follows:

<figure><img src="../../../.gitbook/assets/image (1024).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th></th><th width="502"></th></tr></thead><tbody><tr><td>Name </td><td>Enter any name of your choice for the approval task being created.</td></tr><tr><td>Description</td><td>Any message that is to be conveyed for the deployment.</td></tr><tr><td>Upload and Deploy</td><td>CPI Artifacts are uploaded to design time of the destination environment and published to runtime</td></tr><tr><td>Upload Only</td><td>CPI Artifacts are uploaded to design time of the destination environment.</td></tr><tr><td>Enable Rollback</td><td>This will create a backup version of the destination artifact so that you can rollback later.</td></tr><tr><td>Notify Users</td><td>This option sends an email notification to <strong>all users involved</strong> in the pipeline when the pipeline is triggered or when specific events occur</td></tr><tr><td>Notify Promotion User</td><td><p>This option specifically <strong>notifies the user who triggered the promotion</strong> (from user story or release package).</p><p></p></td></tr><tr><td><strong>Schedule Time</strong></td><td>You can execute a Release Pipeline either manually or can schedule it to get executed automatically once its reference build pipeline gets executed successfully.</td></tr></tbody></table>

<figure><img src="../../../.gitbook/assets/image (1027).png" alt=""><figcaption></figcaption></figure>

### **Wait For Promotion Task**

In general, pipeline will execute the configured tasks sequentially one after the other. **Wait For Promotion task** will be used to stop the execution of the task automatically in the next stage and wait for manual promotion once the user is ready to promote it to the next stage. Tasks waiting for promotion at the same stage of the pipeline can be packaged together as a **Release Package** and can be promoted to the next stage in the Release Pipeline.

### **Promotion**

Promotion is the process of Moving/Deploying CPI Artifacts to various environments using a Release pipeline associated with the project.\


<figure><img src="../../../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>

Pre-requisite for the promotion to work is that every stage in the Release pipeline should end with “**Promotion Task**”. Promotion can be performed in two ways – via User Story and via Release Package.

**a) Promotion by User story**

1\. From Actions Menu of the User story, promotion can be done.\


<figure><img src="../../../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure>

2\. Clicking Promote will Trigger the Release pipeline associated with the project.

3\. The column “**Pipeline Stage**” shows the current stage in the Release Pipeline execution and status of the Release Pipeline.

4\. The column “**Pipeline Status**” shows the current task in the stage or overall status of the Release Pipeline.

5\. Runtime view of the pipeline can be viewed using “**Pipeline Activity**” menu option in the Actions Menu.\


<figure><img src="../../../.gitbook/assets/image (21) (1).png" alt=""><figcaption></figcaption></figure>

6\. The pipeline activity screen shows all the stages of the Release Pipeline. Clicking on the stage shows the tasks and it’s execution status.

7\. Once Pipeline execution reaches the “**Promotion Task**” Pipeline will continue to wait until further promotion from the User Story or Release Package.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-31.jpg" alt=""><figcaption></figcaption></figure>

8\. User Story can be promoted to next stage (in this case, Prod) or a new Release Package can be created with all the User Stories waiting in QA stage for getting promoted to Prod.\
\


<figure><img src="../../../.gitbook/assets/image (1026).png" alt=""><figcaption></figcaption></figure>

#### **b) Promotion by Release Package**

* If a **Start Stage** is defined, only user stories currently in that stage are eligible for promotion.
* The promotion process uses the **Release Pipeline** associated with the project.

A **Release Package** is a logical grouping of user stories that are promoted together as a single unit, rather than promoting each story individually.

<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-14.jpg" alt=""><figcaption></figcaption></figure>

1\. Clicking on “**Add stories for promotion**” will add all the user stories eligible for promotion.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-15.jpg" alt=""><figcaption></figcaption></figure>

2\. From the Action Menu of the Release package, click on “**Promote**”.\


<figure><img src="../../../.gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>

3\. Execution of the Release package can be seen using the option “**Pipeline Activity**”\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-17.jpg" alt=""><figcaption></figcaption></figure>

4\. Once Promotion for Release package starts then the Release Package will be locked and no changes are possible like addition of more user stories.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-18.jpg" alt=""><figcaption></figcaption></figure>

5\. User has to unlock Release Package to backout any of the user stories after promotion. In role permissions, user should have Unlock Release Package permission.

### **Validation Task**

Validation task is added to perform Static Code Analysis checks and generate the validation report to view the errors encountered. You can continue the execution of the pipeline even upon failure by checking the checkbox – Continue On Failure by fixing the errors seen in the log and re-running the release pipeline.\
\


<figure><img src="../../../.gitbook/assets/image (1029).png" alt=""><figcaption></figcaption></figure>

The validation report gets generated irrespective of the pipeline execution status - whether success or a failure.\
\
\
Note: If the Release Pipeline fails, the logs are also attached in the notification email.

<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-21.jpg" alt=""><figcaption></figcaption></figure>

By default, the user who creates the Release Pipeline is notified and specifying the distribution list is optional.

**Multi-Stage Release Pipeline**

Any number of stages can be added while creating a release pipeline. An existing release pipeline can also be edited to include various stages.

This is required when we want the deployments to take place in multiple environments one after the other continuously which is a part of Continuous Delivery.

For each stage, the tasks are to be added separately. This corresponds to the tasks that are to be performed in that particular environment for the deployment to take place and the required actions that are to be taken.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-22.jpg" alt=""><figcaption></figcaption></figure>

**Editing/ Deleting Pipeline**

Go to the required pipeline and click Edit to edit the pipeline or Delete to delete the pipeline.

**Running a Release Pipeline**

Once a release pipeline is created, you can run multiple iterations to deploy MTAR artifacts.

To run a release pipeline:

1\. Once you create a release package, go to Release and click Release Pipeline.

2\. Choose the required release pipeline to be run and click Run.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-23.jpg" alt=""><figcaption></figcaption></figure>

3\. A pop-up appears. Enter a Cycle Name and Select Release Package from the drop down.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-24.jpg" alt=""><figcaption></figcaption></figure>

4\. Click Trigger Pipeline. A message is displayed, about successful triggering of a release pipeline. Click OK. The following screen is displayed:\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-25.jpg" alt=""><figcaption></figcaption></figure>

5\. Click Refresh. Click on the required build to view a list of the triggered cycle.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-26.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-27.jpg" alt=""><figcaption></figcaption></figure>

Click on the required cycle to view its details.

**Rollback**

Rollback is available for CPI artifacts that are deployed to design time in addition to those published to run time. To rollback a build, click Rollback in the status page.

While creating a release pipeline, you must enable the option to rollback as a prerequisite.

Click rollback in the deployment screen to rollback while running release pipelines.

In the confirmation pop-up that appears, click Yes. Rollback process starts.

<figure><img src="../../../.gitbook/assets/image (384).png" alt=""><figcaption></figcaption></figure>

**Rollback Logs**

Rollback Logs are available for CPI artifacts that are deployed to design time in addition to those published to run time. To rollback a build, click Rollback in the status page.

Once rollback is enabled, you can see the rollback= status in the deployment logs.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-29.jpg" alt=""><figcaption></figcaption></figure>

**Display Logs**

Click Display Logs to view the logs of the current release pipeline.

<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-cpi-deployments-30.jpg" alt=""><figcaption></figcaption></figure>
