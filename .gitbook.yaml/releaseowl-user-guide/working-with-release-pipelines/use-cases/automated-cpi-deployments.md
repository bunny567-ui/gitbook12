# Automated CPI Deployments

**Release Pipelines**

Release Pipelines in ReleaseOwl facilitate orchestrated deployments to SAP environments with structured approval workflows. A pipeline can consist of one or more stages, each representing a deployment phase (e.g., Dev, QA, Prod). Within each stage, users can define a sequence of actions including approval tasks, manual interventions, deployment steps, external callouts, and automated test executions—ensuring controlled and auditable releases across the landscape.

{% hint style="info" %}
**Note:** You can create a multi-stage pipeline for continuous deployment across various environments one after the other towards continuous delivery of application all through Dev - QA - Staging - Production.
{% endhint %}

### **Creating a Release Pipeline**

Creating a Release Pipeline is a three-step process.

| Step 1 | Enter a name in Release Pipeline Name                                                                                                    |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Step 2 | Click '**Add Stages**' to add the required stages. Add various types of pre-deployment, deployment, and post-deployment tasks as needed. |
| Step3  | Specify the email ids to receive notifications about release pipeline execution status.                                                  |

#### **For creating release pipeline:**

1. Select the required CPI Project.
2. Navigate to **Release and** click on the **Release Pipelines.**

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Enter a **Pipeline Name**.
4. Click **Create New Release Pipeline**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. Click **Add Stage**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

\


6. **Tasks:** Click Add to enter any tasks that are to be performed

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** To remove any stage, click Remove stage button.
{% endhint %}

7. Different tasks that can be added are as follows:\


<figure><img src="../../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** All the tasks except Deployment Task are similar for any project type. For CPI projects, Wait for Promotion and Validation tasks are the two extra tasks available other than the ones available for every project type.
{% endhint %}

### **Deployment Task**

All the details pertaining to the deployment of the artifact is specified in the deployment task. The following screen is displayed on adding a deployment task. The various Deployment Actions that can be performed are as follows:

<figure><img src="../../../.gitbook/assets/image (1024).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th></th><th width="502"></th></tr></thead><tbody><tr><td>Name </td><td>Enter any name of your choice for the approval task being created.</td></tr><tr><td>Description</td><td>Any message that is to be conveyed for the deployment.</td></tr><tr><td>Upload and Deploy</td><td>CPI Artifacts are uploaded to design time of the destination environment and published to runtime</td></tr><tr><td>Upload Only</td><td>CPI Artifacts are uploaded to design time of the destination environment.</td></tr><tr><td>Enable Rollback</td><td>This will create a backup version of the destination artifact so that you can rollback later.</td></tr><tr><td>Notify Users</td><td>This option sends an email notification to <strong>all users involved</strong> in the pipeline when the pipeline is triggered or when specific events occur</td></tr><tr><td>Notify Promotion User</td><td><p>When enabled, this option sends an email notification to the user who triggered the promotion (from a user story or release package), regardless of whether the task succeeds or fails.</p><p></p></td></tr><tr><td>Schedule Time</td><td>You can execute a Release Pipeline either manually or can schedule it to get executed automatically once its reference build pipeline gets executed successfully.</td></tr></tbody></table>

<figure><img src="../../../.gitbook/assets/image (1027).png" alt=""><figcaption></figcaption></figure>

### **Wait For Promotion Task**

In general, pipeline will execute the configured tasks sequentially one after the other. **Wait For Promotion task** will be used to stop the execution of the task automatically in the next stage and wait for manual promotion once the user is ready to promote it to the next stage. Tasks waiting for promotion at the same stage of the pipeline can be packaged together as a **Release Package** and can be promoted to the next stage in the Release Pipeline.

### **Promotion**

Promotion is the process of Moving/Deploying CPI Artifacts to various environments using a Release pipeline associated with the project.\


<figure><img src="../../../.gitbook/assets/image (19) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Pre-requisite for the promotion to work is that every stage in the Release pipeline should end with “**Promotion Task**”. Promotion can be performed in two ways – via User Story and via Release Package.

**a) Promotion by User story**

1\. From Actions Menu of the User story, promotion can be done.\
2\. Clicking **Promote** will Trigger the Release pipeline associated with the project.

<figure><img src="../../../.gitbook/assets/image (20) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3\. The column “**Pipeline Stage**” shows the current stage in the Release Pipeline execution and status of the Release Pipeline.

4\. The column “**Pipeline Status**” shows the current task in the stage or overall status of the Release Pipeline.

<figure><img src="../../../.gitbook/assets/image (1263).png" alt=""><figcaption></figcaption></figure>

5\. Runtime view of the pipeline can be viewed using “**Pipeline Activity**” menu option in the **Actions Menu**.

<figure><img src="../../../.gitbook/assets/image (1264).png" alt=""><figcaption></figcaption></figure>

6\. The pipeline activity screen shows all the stages of the Release Pipeline. Clicking on the stage shows the tasks and it’s execution status.

<figure><img src="../../../.gitbook/assets/image (1265).png" alt=""><figcaption></figcaption></figure>

7\. Once Pipeline execution reaches the “**Promotion Task**” Pipeline will continue to wait until further promotion from the User Story or Release Package.

8\. User Story can be promoted to next stage (in this case, Prod) or a new Release Package can be created with all the User Stories waiting in QA stage for getting promoted to Prod.\
\


<figure><img src="../../../.gitbook/assets/image (1026).png" alt=""><figcaption></figcaption></figure>

#### **b) Promotion by Release Package**

* If a **Start Stage** is defined, only user stories currently in that stage are eligible for promotion.
* The promotion process uses the **Release Pipeline** associated with the project.

A **Release Package** is a logical grouping of user stories that are promoted together as a single unit, rather than promoting each story individually.

<figure><img src="../../../.gitbook/assets/image (1255).png" alt=""><figcaption></figcaption></figure>

1\. Clicking on “**Add stories for promotion**” will add all the user stories eligible for promotion.\


<figure><img src="../../../.gitbook/assets/image (1256).png" alt=""><figcaption></figcaption></figure>

2\. From the Action Menu of the Release package, click on “**Promote**”.

<figure><img src="../../../.gitbook/assets/image (1257).png" alt=""><figcaption></figcaption></figure>

3\. Execution of the Release package can be seen using the option “**Pipeline Activity**”.\


<figure><img src="../../../.gitbook/assets/image (1259).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1258).png" alt=""><figcaption></figcaption></figure>



4\. Once **Promotion** for Release package starts then the **Release Package** will be locked and no changes are possible like addition of more user stories.

<figure><img src="../../../.gitbook/assets/image (1261).png" alt=""><figcaption></figcaption></figure>

5\. User has to unlock Release Package to backout any of the user stories after promotion. In role permissions, user should have Unlock Release Package permission.

<figure><img src="../../../.gitbook/assets/image (1262).png" alt=""><figcaption></figcaption></figure>

### **Validation Task**

Validation task is added to perform Static Code Analysis checks and generate the validation report to view the errors encountered. You can continue the execution of the pipeline even upon failure by checking the checkbox – Continue On Failure by fixing the errors seen in the log and re-running the release pipeline.

### Validation Task for CPI and API projects:

| **Field / Option**      | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                | Enter any name of your choice for the validation task being created. **Note:** Only letters, numbers, underscores (\_), and periods (.) are permitted.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Description**         | Any message that is to be conveyed to the task approver can be mentioned here.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **CPI**                 | Select the respective target environment where validation is to be performed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Pipeline Execution**  | Section indicating execution preferences for the task.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Continue on Failure** | Checkbox to allow pipeline execution to continue even if validation fails.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Quality Checks**      | <p><strong>CPI Downgrade Check:</strong> The downgrade check evaluates version consistency between deploying artifact version and target environments version for CPI artifacts.  </p><p></p><p> <strong>Unit Tests:</strong>  Executes CPI unit tests to validate business logic.                                                          </p><p></p><p><strong>User  Story Dependencies (Beta):</strong>  Identifies and validates dependent user stories to prevent conflicts or incomplete deployments.   </p><p></p><p><strong>CPI Governance :</strong> Enforces organizational policies by validating artifact metadata, naming standards, and deployment readiness—ensuring controlled and compliant releases.                    </p><p></p><p><strong>Note:</strong> You can select <strong>any one or more</strong> of the following <strong>Quality Checks</strong> when configuring the validation task.</p> |

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1322).png" alt=""><figcaption></figcaption></figure>

The validation report gets generated irrespective of the pipeline execution status - whether success or a failure.

<figure><img src="../../../.gitbook/assets/image (1325).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1324).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:**  If the Release Pipeline fails, the logs are also attached in the notification email.
{% endhint %}

By default, the user who creates the Release Pipeline is notified and specifying the distribution list is optional.

**Multi-Stage Release Pipeline**

Any number of stages can be added while creating a release pipeline. An existing release pipeline can also be edited to include various stages. This is required when we want the deployments to take place in multiple environments one after the other continuously which is a part of Continuous Delivery.

For each stage, the tasks are to be added separately. This corresponds to the tasks that are to be performed in that particular environment for the deployment to take place and the required actions that are to be taken.\
\


<figure><img src="../../../.gitbook/assets/image (1268).png" alt=""><figcaption></figcaption></figure>



**Editing/ Deleting Pipeline**

Go to the required pipeline and click **Edit** to edit the pipeline or **Delete** to delete the pipeline.

<figure><img src="../../../.gitbook/assets/image (1269).png" alt=""><figcaption></figcaption></figure>

**Rollback**

1. Rollback is available for CPI artifacts that are deployed to design time in addition to those published to run time. To rollback a build, click **Rollback** in the status page.
2. While creating a release pipeline, you must enable the option to rollback as a prerequisite.

<figure><img src="../../../.gitbook/assets/image (1270).png" alt=""><figcaption></figcaption></figure>

3. Click rollback in the deployment screen to rollback while running release pipelines.
4. In the confirmation pop-up that appears, click **Yes**. Rollback process starts.

<figure><img src="../../../.gitbook/assets/image (384).png" alt=""><figcaption></figcaption></figure>

**Rollback Logs**

Rollback Logs are available for CPI artifacts that are deployed to design time in addition to those published to run time. To rollback a build, click Rollback in the status page. Once rollback is enabled, you can see the rollback= status in the deployment logs.\


<figure><img src="../../../.gitbook/assets/image (1273).png" alt=""><figcaption></figcaption></figure>

**Deploy Logs**

Click **Deploy Logs** to view the logs of the current release pipeline.

<figure><img src="../../../.gitbook/assets/image (1272).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1271).png" alt=""><figcaption></figcaption></figure>
