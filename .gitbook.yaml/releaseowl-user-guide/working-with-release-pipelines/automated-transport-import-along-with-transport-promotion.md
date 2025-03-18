# Automated Transport import along with Transport Promotion

### **Release Pipelines**

Release Pipelines enables you to orchestrate deployments into SAP environments with right approvals in place. It can be created with one or more stages. Each stage will correspond to automated deployment to the required SAP environment with a sequence of activities such as tasks related to approvals, manual changes, deployments, callouts and tests execution.

{% hint style="info" %}
**Note:** You can create a multi-stage pipeline for continuous deployment across various environments one after the other towards continuous delivery of application all through Dev - QA - Staging - Production.
{% endhint %}

### **Creating a Release Pipeline**

Creating a Release Pipeline is a six-step process.

| **Step1** | Enter a name in Release Pipeline Name                                                                |
| --------- | ---------------------------------------------------------------------------------------------------- |
| **Step2** | Pipeline Type – SAP On-Premise is displayed by default as the project is of type SAP On-Premise.     |
| **Step3** | The project that we are currently working on is displayed by default and is non editable.            |
| **Step4** | Click Add Stages, add the stages. Add various types of pre, post and deployment tasks on need basis. |
| **Step5** | Pipeline can be executed only manually for On-Prem projects.                                         |
| **Step6** | Specify the email ids to receive notifications about release pipeline execution status.              |

### For creating release pipeline:

* Select the required On-Prem Project and in Release go to Release Pipelines.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-1.jpg" alt=""><figcaption></figcaption></figure>

1\. Click **Create New Release Pipeline.**

2\. **Release Pipeline Name: Give a name for the release pipeline.**

<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-2.jpg" alt=""><figcaption></figcaption></figure>

3\. **Pipeline Type**: SAP **On-Premise** is shown by default.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-3.jpg" alt=""><figcaption></figcaption></figure>

4\. **Artifact Source**: The project that we are currently working on is displayed by default and is non editable.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-4.jpg" alt=""><figcaption></figcaption></figure>

5\. **Stages**: Click Add Stage.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-5.jpg" alt=""><figcaption></figcaption></figure>

Enter the stage name say for e.g., UAT or QA where the deployment has to be carried out and click OK.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-6.jpg" alt=""><figcaption></figcaption></figure>

**Tasks:** Click Add to enter any tasks that are to be performed\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-7.jpg" alt=""><figcaption></figcaption></figure>

Different tasks that can be added are as follows:\


<figure><img src="../../.gitbook/assets/image (364).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** All the tasks **except Deployment** Task are similar for any project type.
{% endhint %}

For **On-Premise** projects, **Wait for Promotion** and **Validation** tasks are the two extra tasks available other than the ones available for every project type.

### **Deployment Task**

All the details pertaining to the deployment of the artifact is specified in the deployment task.

The following screen is displayed on adding a deployment task.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-9.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**              | Deployment task name                                                                                                                       |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Domain Controller** | Select the appropriate Transport Domain Controller which is the system from which one can make changes to SAP Transport Management System. |
| **Target System**     | Enter the Target System which is to be updated with the changes from the Source System.                                                    |

### **Wait For Promotion Task**

In general, pipeline will execute the configured tasks sequentially one after the other.

Wait For Promotion task will be used to stop the execution of the task automatically in the next stage and wait for manual promotion once the user is ready to promote it to the next stage.

Tasks waiting for promotion at the same stage of the pipeline can be packaged together as a Release Package and can be promoted to the next stage in the Release Pipeline.

### **Validation Task**

Validation task is added to perform Static Code Analysis checks and generate the validation report to view the errors encountered.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-10.jpg" alt=""><figcaption></figcaption></figure>

The execution of the release pipeline halts if the validation fails at any point. You can continue the execution of the release pipeline even upon failure by checking the checkbox – **Continue On Failure**. This feature allows the completion of release pipeline by fixing the errors seen in the log and re-running the release pipeline. The validation report gets generated irrespective of the pipeline execution status - whether success or a failure.

5\. **Schedule:** You can execute a Release Pipeline manually.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-11.jpg" alt=""><figcaption></figcaption></figure>

6\. **Notification Emails:** You can specify an email distribution list separated by comma who you want to notify the result of the Release Pipeline Execution – either Success or Failure.

By default, the user who creates the Release Pipeline is notified and specifying the distribution list is optional.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-12.jpg" alt=""><figcaption></figcaption></figure>

**Promotion**

Promotion is the process of Moving/Deploying/Importing the transports to the target systems using a Release pipeline associated with the project.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-13.jpg" alt=""><figcaption></figcaption></figure>

Pre-requisite for the promotion to work is that every stage in the Release pipeline should end with “**Promotion Task**”. Promotion can be performed in two ways – via User Story and via Release Package.

**a) Promotion by User story**

1\. From Actions Menu of the User story, promotion can be done.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-14.jpg" alt=""><figcaption></figcaption></figure>

2\. Clicking Promote will Trigger the Release pipeline associated with the project.

3\. The column “**Pipeline Stage**” shows the current stage in the Release Pipeline execution and status of the Release Pipeline.

4\. The column “**Pipeline Status**” shows the current task in the stage or overall status of the Release Pipeline.

5\. Runtime view of the pipeline can be viewed using “**Pipeline Activity**” menu option in the Actions Menu.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-15.jpg" alt=""><figcaption></figcaption></figure>

6\. The pipeline activity screen shows all the stages of the Release Pipeline. Clicking on the stage shows the tasks and its execution status.

7\. Once Pipeline execution reaches the “**Promotion Task**”, the pipeline will continue to wait until further promotion from the User Story or Release Package.

{% hint style="info" %}
**Note:** The **Wait for Promotion** task is **needed** for a **multistage** Release Pipeline if the user wants to **wait** or **hold** the promotion of the user story to further stages.
{% endhint %}

8\. User Story can be promoted to the next stage (in this case, Prod) or a new Release Package can be created with all the User Stories waiting in UAT stage (here in this case) for getting promoted to Prod.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-16.jpg" alt=""><figcaption></figcaption></figure>

**b) Promotion by Release Package**

Release Package is a logical grouping of user stories or transports that are to be promoted as a single unit instead of promoting each user story separately. If Start stage is mentioned in the Release package, then only the user stories or transports with the current stage same as the one specified in the Release Package are eligible for promotion. It uses the Release Pipeline associated with the project for promotion.

{% hint style="info" %}
**Note:** Promotion of Release Package can be done either through user stories or by transports.
{% endhint %}

**Promotion of Release Package by User Stories**

1\. Clicking **“Add Stories for Promotion”** will add all the user stories eligible for promotion from the selected **Promoted from (Stage)** as a unit.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-17.jpg" alt=""><figcaption></figcaption></figure>

The following points are to be **noted:**

a) By default, the Promote from Stage will be Dev. If you want to promote all the user stories that are already pushed/promoted to QA, then you can select QA from Promote from Stage options available and all the user stories in QA can be promoted to the next available stage as a single unit instead of promoting them individually.

b) If you add user stories that are at a lower stage than the selected Promote from Stage, then ensure that particular user story is promoted to the required Promote from Stage in order to promote the Release Package.

c) You **cannot** add user stories that are at a higher stage than the selected Promoted from Stage.

d) You can add additional user stories other than the ones available from the Promote from Stage by clicking Add User Stories and ensure to promote them to the required Promote from Stage before promoting the Release Package.

**Promotion of Release Package by Transports**

1\. Clicking **“Add Transports for Promotion”** will add all the transports eligible for promotion from the selected **Promoted from (Stage)** as a unit.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-18.jpg" alt=""><figcaption></figcaption></figure>

The following points are to be **noted:**

e) By default, the Promote from Stage will be Dev. If you want to promote all the transports that are already pushed/promoted to QA, then you can select QA from Promote from Stage options available and all the transports in QA can be promoted to the next available stage as a single unit instead of promoting them individually.

f) If you add transports that are at a lower stage than the selected Promote from Stage, then ensure that particular transport is promoted to the required Promote from Stage in order to promote the Release Package.

g) You **cannot** add transports that are at a higher stage than the selected Promoted from Stage.

h) You can add additional transports other than the ones available from the Promote from Stage by clicking Add Transport and ensure to promote them to the required Promote from Stage before promoting the Release Package.

2\. From the Action Menu of the Release package, click on “**Promote**”.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-19.jpg" alt=""><figcaption></figcaption></figure>

3\. Execution of the Release package can be seen using the option “**Pipeline Activity**”\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-20.jpg" alt=""><figcaption></figcaption></figure>

4\. Once Promotion for Release package starts then the Release Package will be locked and no changes are possible like addition of more user stories or transports.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-21.jpg" alt=""><figcaption></figcaption></figure>

5\. User has to unlock Release Package to backout any of the user stories or transports after promotion. In role permissions, user should have Unlock Release Package permission.

**Multi-Stage Release Pipeline**

Any number of stages can be added while creating a release pipeline. An existing release pipeline can also be edited to include various stages.

This is required when we want the deployments to take place in multiple environments one after the other continuously which is a part of Continuous Delivery.

For each stage, the tasks are to be added separately. This corresponds to the tasks that are to be performed in that particular environment for the deployment to take place and the required actions that are to be taken.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/automated-transport-import-along-with-transport-promotion-22.jpg" alt=""><figcaption></figcaption></figure>

**Editing/ Deleting Pipeline**

Go to the required pipeline and click **Edit** to edit the pipeline or **Delete** to delete the pipeline.
