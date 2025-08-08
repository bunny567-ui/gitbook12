# Automated Transport import along with Transport Promotion

### **Release Pipelines**

Release Pipelines orchestrate automated deployments into SAP environments with the right approvals in place. Each pipeline can contain **one or more stages**, corresponding to SAP environments like Dev, QA, Staging, and Production.

{% hint style="info" %}
**Note:** You can create a multi-stage pipeline for continuous deployment across various environments one after the other towards continuous delivery of application all through Dev - QA - Staging - Production.
{% endhint %}

### **Creating a Release Pipeline**

Creating a Release Pipeline is a three-step process.

| **Step1** | Enter a name in Release Pipeline Name                                                                                                    |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Step2** | Click '**Add Stages**' to add the required stages. Add various types of pre-deployment, deployment, and post-deployment tasks as needed. |
| **Step3** | Specify the email ids to receive notifications about release pipeline execution status.                                                  |

#### For creating release pipeline:

1.  Select the required On-Prem Project and in Release go to Release Pipelines.\


    <figure><img src="../../../.gitbook/assets/image (15) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
2. Click **Create New Release Pipeline.**
3. **Release Pipeline Name:** Give a name for the release pipeline.\


<figure><img src="../../../.gitbook/assets/image (13) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4.  **Add Stages:**

    * Click **Add Stage**
    * Name the stage (e.g., `Dev`, `QA`, `UAT`, `Prod`)
    * Click **OK**\


    <figure><img src="../../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
5. **Add Tasks in Each Stage:** Click **Add** to configure tasks within the stage.\


<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** All the tasks **except Deployment** Task are similar for any project type.
{% endhint %}

6. Once all tasks are added, click the **Save** button to finalize the pipeline configuration.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Post-Creation Options**

Once the Release Pipeline is created, you can use the **Actions** button for the following options:

* **Delete**: Permanently removes the pipeline from the project.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* **Save As**: Opens a popup where you can enter a new name and create a copy of the pipeline.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Monitoring Release Pipeline Execution**

*   When you **click the navigation button**, you can view the **complete status** of the release pipeline execution. This includes:

    * **Who triggered** the pipeline
    * The **trigger time**&#x20;
    * The **current execution status** of each stage

    <figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

    <figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

    When you **click the Details tab**, you can view:

    * **Stage-wise release logs**
    * **Task-level results**
    * &#x20;**Validation reports**

    <figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

    <figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



**Skip and Continue Option in the Validation Task**

In the **Release Pipeline > Details** section, during pipeline execution, you will find **Skip and Continue** button available for the **Validation Task**. This button allow you to bypass the validation step under specific conditions—typically used in exception scenarios where validations are not mandatory or have been reviewed externally. When you click on the **Skip and Continue** button:

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

1. A **popup dialog** will appear prompting you to provide a **justification** or **reason** for skipping the validation task (e.g., "Validation not required for this transport", "Approved via external review", or "Urgent fix deployment").
2. Enter the **required reason** in the text field.
3. Click **Skip and Continue** within the popup to proceed.

<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. The pipeline will then skip the validation step and continue with the next task in the stage .

<figure><img src="../../../.gitbook/assets/image (15) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Supported Task Types

| Task Type              | Description                          |
| ---------------------- | ------------------------------------ |
| **Deployment Task**    | Define artifact deployment steps     |
| **Wait for Promotion** | Pauses pipeline for manual promotion |
| **Validation Task**    | Performs static code analysis        |

### **Deployment Task**

The **Deployment Task** defines how an SAP transport request (TR) is deployed to the specified SAP target system during pipeline execution. When you add a Deployment Task to a pipeline stage, a configuration screen appears where you can provide the necessary transport deployment details.\


<figure><img src="../../../.gitbook/assets/image (16) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (17) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**                   | Deployment task name                                                                                                                                           |
| -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Domain Controller**      | Select the appropriate Transport Domain Controller which is the system from which one can make changes to SAP Transport Management System.                     |
| **Target System**          | Enter the Target System which is to be updated with the changes from the Source System.                                                                        |
| **Schedule Time**          | Allows you to specify a future time and date for when the deployment task should be executed automatically.                                                    |
| **Notify Users**           | Sends deployment status notifications (Success/Failure) to all users associated with the pipeline stage.                                                       |
| **Notify Transport Users** | Notifies only those users who are linked to the transports being deployed, providing more targeted communication.                                              |
| **Notify Promotion User**  | Sends notifications to the user who promoted the user story or release package that triggered this deployment.                                                 |
| **Description**            | A free-text area where you can enter notes or additional information about the deployment task. This is useful for providing context or specific instructions. |

### **Wait For Promotion Task**

By default, a pipeline executes the configured tasks sequentially, one after the other. The **Wait for Promotion** task is used to pause the execution at a specific stage, preventing the pipeline from automatically proceeding to the next stage. It holds the process until a manual promotion is triggered by the user. Multiple tasks waiting at the same stage can be grouped into a **Release Package**, allowing them to be promoted together to the next stage in the Release Pipeline.

<figure><img src="../../../.gitbook/assets/image (18) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Validation Task**

Validation task is added to perform Static Code Analysis checks and generate the validation report to view the errors encountered.

| **Field / Option**      | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Domain Controller**   | Dropdown to select the domain controller for the transport landscape.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Source**              | Source system from where transports will be validated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Target**              | Target system where the transport is expected to move.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Pipeline Execution**  | Section indicating execution preferences for the task.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Continue on Failure** | Checkbox to allow pipeline execution to continue even if validation fails.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Quality Checks**      | <p><strong>ATC Checks:</strong> Executes <strong>ABAP Test Cockpit (ATC)</strong> checks to analyze code quality, syntax errors, performance, and security compliance.                                                                     </p><p></p><p><strong>Impact Analysis:</strong> Checks how the changes in the transport affect other dependent or referencing objects across systems.                                                                      </p><p></p><p><strong>Unit Tests:</strong> Runs <strong>ABAP Unit Tests</strong> to verify the functional correctness of the objects in the transport.                                                                    </p><p></p><p><strong>User  Story Dependencies (Beta):</strong>  Identifies and validates dependent user stories to prevent conflicts or incomplete deployments.                       </p><p></p><p><strong>Note:</strong> You can select <strong>any one or more</strong> of the following <strong>Quality Checks</strong> when configuring the validation task.</p> |

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Promotion**

Promotion is the process of Moving/Deploying/Importing the transports to the target systems using a Release pipeline associated with the project.\


<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Pre-requisite for the promotion to work is that every stage in the Release pipeline should end with “**Promotion Task”**. Promotion can be performed in two ways – via User Story and via Release Package.

#### **a) Promotion by User story**

1\. From Actions Menu of the User story, promotion can be done.\


<figure><img src="../../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2\. Clicking Promote will Trigger the Release pipeline associated with the project.

3\. The column “**Pipeline Stage**” shows the current stage in the Release Pipeline execution and status of the Release Pipeline.

4\. The column “**Pipeline Status**” shows the current task in the stage or overall status of the Release Pipeline.

<figure><img src="../../../.gitbook/assets/image (21) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5\. Runtime view of the pipeline can be viewed using “**Pipeline Activity**” menu option in the Actions Menu.\


<figure><img src="../../../.gitbook/assets/image (22) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

6\. The pipeline activity screen shows all the stages of the Release Pipeline. Clicking on the stage shows the tasks and its execution status.

<figure><img src="../../../.gitbook/assets/image (23) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

7\. Once Pipeline execution reaches the “**Promotion Task**”, the pipeline will continue to wait until further promotion from the User Story or Release Package.

{% hint style="info" %}
**Note:** The **Wait for Promotion** task is **needed** for a **multistage** Release Pipeline if the user wants to **wait** or **hold** the promotion of the user story to further stages.
{% endhint %}

8\. User Story can be promoted to the next stage (in this case, Prod) or a new Release Package can be created with all the User Stories waiting in UAT stage (here in this case) for getting promoted to Prod.\


<figure><img src="../../../.gitbook/assets/image (24) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **b) Promotion by Release Package**

Release Package is a logical grouping of user stories or transports that are to be promoted as a single unit instead of promoting each user story separately. If Start stage is mentioned in the Release package, then only the user stories or transports with the current stage same as the one specified in the Release Package are eligible for promotion. It uses the Release Pipeline associated with the project for promotion.

{% hint style="info" %}
**Note:** Promotion of Release Package can be done either through user stories or by transports.
{% endhint %}

### **Promotion of Release Package by User Stories**

1\. Clicking **“Add Stories for Promotion”** will add all the user stories eligible for promotion from the selected **Promoted from (Stage)** as a unit.\


**Key Points to Note:**

* **(a)** By default, the **Promote from Stage** is set to **Dev**. If you want to promote stories already pushed to **QA**, simply select **QA** as the source stage. This allows you to promote all eligible QA stories to the next stage as a single unit instead of doing it individually.
* **(b)** If a user story is at a **lower stage** than the selected **Promote from Stage**, you must first promote that story to the required stage before including it in the Release Package.
* **(c)** User stories that are already at a **higher stage** than the selected **Promote from Stage** **cannot** be added to the Release Package.
* **(d)** You may add other user stories manually using the **“Add User Stories”** option, but ensure those are also promoted to the selected stage before promoting the entire package.

### **Promotion of Release Package by Transports**

1\. Clicking **“Add Stories for Promotion”** will add all the transports eligible for promotion from the selected **Promoted from (Stage)** as a unit.\


<figure><img src="../../../.gitbook/assets/image (1282).png" alt=""><figcaption></figcaption></figure>

The following points apply when promoting a Release Package based on transports:

* **(e)** By default, the **Promote from Stage** is set to **Dev**. If you wish to promote all transports already pushed to **QA**, select **QA** from the available options. This allows all transports in QA to be promoted to the next stage as a single unit rather than promoting them individually.
* **(f)** If you add transports that are currently at a **lower stage** than the selected **Promote from Stage**, ensure those transports are promoted to the appropriate stage before including them in the Release Package.
* **(g)** You **cannot** add transports that are already at a **higher stage** than the selected **Promote from Stage**.
* **(h)** You can manually add additional transports using the **“Add Transport”** option. However, make sure these transports are also promoted to the selected stage before attempting to promote the entire Release Package.

2\. From the Action Menu of the Release package, click on “**Promote**”.

<figure><img src="../../../.gitbook/assets/image (1142).png" alt=""><figcaption></figcaption></figure>

3\. Execution of the Release package can be seen using the option “**Pipeline Activity**.”\


<figure><img src="../../../.gitbook/assets/image (1143).png" alt=""><figcaption></figcaption></figure>

4\. Once Promotion for **Release package** starts then the **Release Package** will be locked and no changes are possible like addition of more user stories or transports.\


<figure><img src="../../../.gitbook/assets/image (1144).png" alt=""><figcaption></figcaption></figure>

5\. User has to unlock **Release Package** to backout any of the user stories or transports after promotion. In role permissions, user should have **Unlock Release Package permission**.

<figure><img src="../../../.gitbook/assets/image (1145).png" alt=""><figcaption></figcaption></figure>

### **Multi-Stage Release Pipeline**

Any number of stages can be added while creating a release pipeline. An existing release pipeline can also be edited to include various stages.

This is required when we want the deployments to take place in multiple environments one after the other continuously which is a part of Continuous Delivery.

For each stage, the tasks are to be added separately. This corresponds to the tasks that are to be performed in that particular environment for the deployment to take place and the required actions that are to be taken.\


<figure><img src="../../../.gitbook/assets/image (13) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
