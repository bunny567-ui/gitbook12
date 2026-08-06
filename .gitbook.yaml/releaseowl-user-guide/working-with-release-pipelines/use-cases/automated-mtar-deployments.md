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
2. Click **New Release Pipeline.**

<figure><img src="../../../.gitbook/assets/image (1974).png" alt=""><figcaption></figcaption></figure>

3. A pop-up window will appear where you can choose either **New Build Pipeline** or **Import Build Pipeline**.
4.  If **Import Build Pipeline** is selected:

    * Click **Browse** under **Select JSON File** and upload the exported pipeline configuration file.
    * Enter a name in the **Build Pipeline Name** field.
    * Click **Create** to import the configuration and create the build pipeline.

    <figure><img src="../../../.gitbook/assets/image (1976).png" alt=""><figcaption></figcaption></figure>
5. If **Create New Build Pipeline** is selecte&#x64;**:**
   * You will be redirected to the **Build Pipeline** configuration page, where you can define and configure the pipeline stages and tasks.
6. **Release Pipeline Name:** Give a name for the release pipeline.
7. **Labels:** Labels act as tags for your release pipeline, helping you categorize, organize, and easily search for pipelines. Multiple labels can be added as needed.

<figure><img src="../../../.gitbook/assets/image (1229).png" alt=""><figcaption></figcaption></figure>

8. **Artifact Source:** The dropdown contains all the build pipelines of type **MTAR**. Choose the build pipeline with the necessary artifacts to be deployed in the environment.<br>

<figure><img src="../../../.gitbook/assets/image (1231).png" alt=""><figcaption></figcaption></figure>

9. **Add Stages:** Click **Add Stage** and enter the stage name say for e.g., UAT or QA where the deployment has to be carried out and click **OK.**

<figure><img src="../../../.gitbook/assets/image (1237).png" alt=""><figcaption></figcaption></figure>

10. The newly added stage appears as follows:

<figure><img src="../../../.gitbook/assets/image (1238).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** To remove any stage, click **Remove Stage** button.
{% endhint %}

**Tasks:** Click **Add** to enter any tasks that are to be performed as desired. (Deployment, Approvals, Manual Task, Callout, Test Execution and User Story Status Update)

<figure><img src="../../../.gitbook/assets/image (1239).png" alt=""><figcaption></figcaption></figure>

### **Deployment Task** &#x20;

All the details pertaining to the deployment of the artifact is specified in deployment task. The following screen is displayed on adding a deployment task.

<figure><img src="../../../.gitbook/assets/image (2135).png" alt=""><figcaption></figcaption></figure>

**Cloud Transport Management**

* SAP Cloud Transport Management service allows you to manage the transport of development artifacts and application-specific content between different SAP BTP accounts.

{% hint style="info" %}
**Note:** Further information on Cloud Transport Management System can be found at [https://help.sap.com/docs/TRANSPORT\_MANAGEMENT\_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/5fef9d6b1cb047b2b18d9eb57aa15352.html](https://help.sap.com/docs/TRANSPORT_MANAGEMENT_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/5fef9d6b1cb047b2b18d9eb57aa15352.html)
{% endhint %}

* Select the option **Upload Artifact** to Cloud Transport Management if the artifact has to be uploaded to any other BTP environment.

The following screen is displayed.<br>

<figure><img src="../../../.gitbook/assets/image (1241).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Select Environment**                       | Select an environment from the available list of registered SAP BTP environments where the deployment has to take place.                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Service Instance**                         | Select the Service Instance from the available service instances listed in the dropdown.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Service Key**                              | Select the Service Key from the available service keys listed in the dropdown.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Node Name**                                | Enter a node name added in the Cloud Transport Management System corresponding to the environment to which the artifact is to be uploaded.                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Discard old builds**                       | <p>Enable <strong>Discard Old Builds</strong> to automatically remove older build records and artifacts based on the retention criteria specified below.</p><ul><li><strong>Max # of Builds to Keep</strong>: Specifies the maximum number of recent builds to retain. When this limit is exceeded, older builds are automatically removed.</li><li><strong>Keep Builds for (Days)</strong>: Specifies the number of days build records and artifacts should be retained. Builds older than the specified number of days will be automatically deleted.</li></ul><p><br></p> |
| <p></p><p><strong>Notify Users</strong> </p> | <p></p><p>Enable this option to send notifications to the users associated with the task or pipeline. Notifications are triggered based on configured events, such as task creation, approval requests, build completion, deployment status, or task failures.</p><p></p><p></p>                                                                                                                                                                                                                                                                                             |
| **Notify Promotion User**                    | Enable this option to notify the user who initiated the promotion whenever the promotion process starts, completes, succeeds, or fails.                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Schedule Time**                            | Specify the date and time at which the task, build, deployment, or promotion should be executed. The configured schedule allows the process to run automatically at the designated time without requiring manual intervention.                                                                                                                                                                                                                                                                                                                                               |

<figure><img src="../../../.gitbook/assets/image (1992).png" alt=""><figcaption></figcaption></figure>

**Trigger:** You can trigger a Release Pipeline either **Manually** or on **Successful Build** it to get triggered automatically once its reference build pipeline gets executed successfully.

<figure><img src="../../../.gitbook/assets/image (1242).png" alt=""><figcaption></figcaption></figure>

### CAP Application Build Task

The **CAP Application Build Task** is used to build an SAP Cloud Application Programming (CAP) application as part of the release pipeline. This task compiles the application source code, resolves dependencies, and generates the deployment artifacts required for subsequent deployment stages.

**Configuration**

* **Name**: Enter a unique name for the build task.
* **Description**: Provide a brief description of the task.
* **Select Environment(s)**: Choose the environment(s) where the build should be executed. The available environments are those that have been registered and configured in the **Project Settings** section.
* **Notify Users**: Enable this option to send notifications to users when the task starts, completes, or fails.

<figure><img src="../../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

## MTAR Pull Request Task

The **MTAR Pull Request Task** creates a Pull Request between the configured source and target branches during Release Pipeline execution. It enables code review and approval before changes are promoted to the next environment.

#### Configure the MTAR Pull Request Task

1. Navigate to **Release** and click **Release Pipelines**.
2. Open the required Release Pipeline.
3. Add or edit the **MTAR Pull Request Task**.
4. Provide the following information:

| **Field**              | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**               | Enter a name for the task.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Description**        | Enter a brief description of the task.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Change Source**      | <p>Select the source branch for the Pull Request.<br><br><strong>Available options:</strong><br>• <strong>Branch from User Story</strong> – Uses the <strong>Feature Branch</strong> or <strong>Hot Fix Branch</strong> associated with the User Story.<br>• <strong>Branch from Environment</strong> – Uses the branch configured for the selected source environment in the MTAR Application.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Target Environment** | Select the target environment. ReleaseOwl uses the branch configured for the selected environment as the target branch for the Pull Request.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Assign To**          | <p>Specifies who is responsible for reviewing and approving the Pull Request. The following options are available:<br><br><strong>User</strong> – Select a specific user from the available list. The selected user is assigned the Pull Request approval task.<br><br><strong>Role</strong> – Select a role. Any user assigned to the selected role can review and approve the Pull Request.<br><br><strong>Custom</strong> – Assign different roles to specific components. Users assigned to the configured roles for each component can review and approve the Pull Request for their respective components.<br><br><strong>Note:</strong> The following options are available only when <strong>Custom</strong> is selected:<br><br>• <strong>Export Roles</strong> – Downloads the configured component-to-role mappings. The exported file can be reused in another Release Pipeline.<br>• <strong>Import Roles</strong> – Uploads a previously exported component-to-role mapping file.<br>• <strong>Add Component and Role (+)</strong> – Click <strong>+</strong> to add a component-to-role mapping. Select the required <strong>Component</strong>, specify one or more <strong>Roles</strong> (comma-separated), and click <strong>Add</strong> to save the mapping.<br><strong>Promoter</strong> </p> |

5. Click **Save** to save the task.

{% hint style="info" %}
**Note :** During pipeline execution, ReleaseOwl creates the Pull Request, assigns the approval task to the configured reviewer, and resumes the Release Pipeline after the Pull Request is approved.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (2130).png" alt=""><figcaption></figcaption></figure>

## MTAR Application Merge Task

The **MTAR Application Merge Task** merges the source branch into the target branch after the Pull Request is approved.

#### Configure the MTAR Application Merge Task

1. Add or edit the **MTAR Application Merge Task**.
2. Provide the following information:

| **Field**                      | **Description**                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                       | Enter a name for the task.                                                                                                                                                                                                                                                                                                                            |
| **Description**                | Enter a brief description of the task.                                                                                                                                                                                                                                                                                                                |
| **Merge Source**               | <p>Select the source branch to merge.<br><br><strong>Available options:</strong><br>• <strong>Branch from User Story</strong> – Uses the Feature Branch or Hot Fix Branch associated with the User Story.<br>• <strong>Branch from Environment</strong> – Uses the branch configured for the selected source environment in the MTAR Application.</p> |
| **Staging Branch**             | Enable this option to create a temporary staging branch and perform the merge operation through the staging branch.                                                                                                                                                                                                                                   |
| **Target Environment**         | Select the target environment. ReleaseOwl uses the branch configured for the selected environment as the merge target.                                                                                                                                                                                                                                |
| **Notify Users**               | Enable this option to send email notifications after the merge operation is completed.                                                                                                                                                                                                                                                                |
| **Create Staging Branch For**  | <p>Specifies when a staging branch should be created.<br><br><strong>Available options:</strong><br>• <strong>User Story</strong><br>• <strong>Release Package</strong><br>• <strong>Both</strong></p>                                                                                                                                                |
| **Execute This Task Only For** | <p>Specifies when the Merge Task should execute.<br><br><strong>Available options:</strong><br>• <strong>User Story</strong><br>• <strong>Release Package</strong><br>• <strong>Both</strong></p>                                                                                                                                                     |

3. Click **Save** to save the task.

<div><figure><img src="../../../.gitbook/assets/image (2131).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (2132).png" alt=""><figcaption></figcaption></figure></div>

## MTAR Application Build Task

The **MTAR Application Build Task** executes the configured Build Pipeline and generates deployable MTAR artifacts.

**Configure the MTAR Application Build Task**

1. Add or edit the **MTAR Application Build Task**.
2. Provide the following information:

| **Field**                                                 | **Description**                                                                                                                                                                                                                                                                                                                                                                                           |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                                                  | Enter a name for the task.                                                                                                                                                                                                                                                                                                                                                                                |
| **Description**                                           | Enter a brief description of the task.                                                                                                                                                                                                                                                                                                                                                                    |
| **Build Source**                                          | <p>Select the source used for the build.<br><br><strong>Available options:</strong><br>• <strong>Branch from User Story</strong> – Builds the Feature Branch or Hot Fix Branch associated with the User Story.<br>• <strong>Branch from Environment</strong> – Builds the branch configured for the selected environment.<br>• <strong>Staging Branch</strong> – Builds the temporary staging branch.</p> |
| **Use Different Settings for Build from Release Package** | Enable this option to use a different build strategy for Release Package executions.                                                                                                                                                                                                                                                                                                                      |
| **Build Source for Release Package**                      | <p>Select the build source for Release Package execution.<br><br><strong>Available options:</strong><br>• <strong>Branch from Environment</strong><br>• <strong>Staging Branch</strong></p>                                                                                                                                                                                                               |
| **Notify Users**                                          | Enable this option to send email notifications after the build execution is completed.                                                                                                                                                                                                                                                                                                                    |

3. Click **Save** to save the task.

{% hint style="info" %}
**Note** : If multiple MTAR applications are associated with a User Story, ReleaseOwl builds each application independently and generates separate MTAR artifacts.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (2133).png" alt=""><figcaption></figcaption></figure>

## MTAR Validation Task

The **MTAR Validation Task** validates the generated MTAR artifacts before deployment.

**Configure the MTAR Validation Task**

1. Add or edit the **MTAR Validation Task**.
2. Provide the following information:

| **Field**               | **Description**                                                                                                                                     |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                | Enter a name for the task.                                                                                                                          |
| **Description**         | Enter a brief description of the task.                                                                                                              |
| **Select Build Task**   | Select the Build Task whose generated MTAR artifacts will be validated.                                                                             |
| **Target Environment**  | Select the target environment used for dependency analysis, impact analysis, and environment compatibility validation.                              |
| **Continue on Failure** | Enable this option to continue the Release Pipeline even if validation reports failures. When disabled, the pipeline stops if the validation fails. |

3. Click **Save** to save the task.

{% hint style="info" %}
**Note :** Validation may include **SonarQube analysis**, **ESLint validation**, **OPA5 test execution**, **static code analysis**, **build verification**, and **artifact validation**, depending on the Build Pipeline configuration.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (2134).png" alt=""><figcaption></figcaption></figure>

#### **Triggers**&#x20;

The **Triggers** option specifies when the task is executed in the Release Pipeline.

The following trigger options are available:

* **Manual** – Executes the task only when it is manually triggered by a user during the Release Pipeline execution.
* **On Successful Build** – Automatically executes the task after the associated Build Pipeline completes successfully. This ensures that the task is performed only when the build is successful.

#### **Advance Settings**&#x20;

The **Advanced Settings** section provides additional configuration options for the release pipeline to help enforce governance and notification requirements.

1. **Prevent Same Approver Across Tasks**

Enable the **Prevent same approver across tasks** option to enforce segregation of duties within the release pipeline.

When this option is enabled, the same user cannot approve multiple **Human Tasks** within the same release pipeline. This ensures that different approval stages are handled by different individuals, maintaining proper checks and balances throughout the release process.

**Behavior:**

For example, a user who approves a **Peer Review** task cannot also approve subsequent tasks such as **QA Approval** or **UAT Testing** in the same pipeline.

* The system validates approvers across all Human Tasks in the pipeline.
* If the same user attempts to approve more than one Human Task, the approval action is blocked.
* An error message is displayed, indicating that the approver has already been used for another task in the pipeline.

2. **Notification Email(s)**

Use the **Notification Email(s)** field to specify email addresses that should receive notifications related to the release pipeline.

* Enter one or more email addresses separated by commas.
* Notifications will be sent to the specified recipients based on pipeline events and task activities.

<figure><img src="../../../.gitbook/assets/image (1975).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** If the Release Pipeline fails, the logs are also attached in the notification email. By default, the user who creates the Release Pipeline is notified and specifying the distribution list is optional.
{% endhint %}

### **Post-Creation Options**

Once the Release Pipeline is created, you can use the **Actions** button for the following options:

**Save As**:  Opens a popup where you can enter a new name and create a copy of the pipeline.

<figure><img src="../../../.gitbook/assets/image (14) (1).png" alt=""><figcaption></figcaption></figure>

**Versions**: Displays all versions for the selected Release Pipeline. This option helps users track generated versions of the **Release Pipeline**. Versions are displayed only after the **Release Pipeline** has been promoted for the corresponding user story.

To view a specific version:

1. Select the required version from the created Release Pipeline list.

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

2. Click the **Actions (⋯)** button for that version.
3. Select **View**.

This allows you to view the details of the selected version of the release pipeline.

**Delete:** Deletes an existing release pipeline from the system.

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

**Archive** : The **Archive** option is available, which archives the project instead of deleting it.

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

**Export Release Pipeline:** It is the process of downloading the complete configuration of an existing release pipeline as a file (usually in **JSON format**) so it can be reused, shared, or backed up.

1. Navigate to the **Release Pipelines** section.
2. Select the existing pipeline you want to reuse.
3. Click **Export Release Pipeline**.
4. The pipeline configuration is downloaded as a **JSON file** to your local system.

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

### **Multi-Stage Release Pipeline**

Any number of stages can be added while creating a release pipeline. An existing release pipeline can also be edited to include various stages. This is required when we want the deployments to take place in multiple environments one after the other continuously which is a part of Continuous Delivery.&#x20;

For each stage, the tasks are to be added separately. This corresponds to the tasks that are to be performed in that particular environment for the deployment to take place and the required actions that are to be taken.<br>

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

**Editing a Release Pipeline**

* Navigate to the **Release Pipelines** page.
* Open the required Release Pipeline.
* Click **Edit** to modify the pipeline configuration.

<figure><img src="../../../.gitbook/assets/image (1977).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :**  Users can now promote builds directly from the **User Story** and **Release Package** sections without navigating to the Build Pipelines module.
{% endhint %}

