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

<figure><img src="../../../.gitbook/assets/image (1991).png" alt=""><figcaption></figcaption></figure>

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

**Advance Settings :** The **Advanced Settings** section provides additional configuration options for the release pipeline to help enforce governance and notification requirements.

**Prevent Same Approver Across Tasks**

Enable the **Prevent same approver across tasks** option to enforce segregation of duties within the release pipeline.

When this option is enabled, the same user cannot approve multiple **Human Tasks** within the same release pipeline. This ensures that different approval stages are handled by different individuals, maintaining proper checks and balances throughout the release process.

**Behavior:**

For example, a user who approves a **Peer Review** task cannot also approve subsequent tasks such as **QA Approval** or **UAT Testing** in the same pipeline.

* The system validates approvers across all Human Tasks in the pipeline.
* If the same user attempts to approve more than one Human Task, the approval action is blocked.
* An error message is displayed, indicating that the approver has already been used for another task in the pipeline.

**Notification Email(s)**

Use the **Notification Email(s)** field to specify email addresses that should receive notifications related to the release pipeline.

* Enter one or more email addresses separated by commas.
* Notifications will be sent to the specified recipients based on pipeline events and task activities.

<figure><img src="../../../.gitbook/assets/image (1975).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** If the Release Pipeline fails, the logs are also attached in the notification email. By default, the user who creates the Release Pipeline is notified and specifying the distribution list is optional.
{% endhint %}

### CAP Application Build Task

The **CAP Application Build Task** is used to build an SAP Cloud Application Programming (CAP) application as part of the release pipeline. This task compiles the application source code, resolves dependencies, and generates the deployment artifacts required for subsequent deployment stages.

**Configuration**

* **Name**: Enter a unique name for the build task.
* **Description**: Provide a brief description of the task.
* **Select Environment(s)**: Choose the environment(s) where the build should be executed. The available environments are those that have been registered and configured in the **Project Settings** section.
* **Notify Users**: Enable this option to send notifications to users when the task starts, completes, or fails.

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

After configuring the required settings, click **Save** to apply the changes. The **Release Pipeline** will be created successfully and will be available in the **Release Pipelines** list.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Post-Creation Options**

Once the Release Pipeline is created, you can use the **Actions** button for the following options:

**Save As**:  Opens a popup where you can enter a new name and create a copy of the pipeline.

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

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

**Multi-Stage Release Pipeline**

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

<figure><img src="../../../.gitbook/assets/image (1977).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :**  Users can now promote builds directly from the **User Story** and **Release Package** sections without navigating to the Build Pipelines module.
{% endhint %}

### **Assigning Artifacts to User Stories** <a href="#assigning-artifacts-to-user-stories" id="assigning-artifacts-to-user-stories"></a>

1. Navigate to **Change Management** and click on **User Stories**.

<figure><img src="../../../.gitbook/assets/image (1978).png" alt=""><figcaption></figcaption></figure>

2. Click **Create New User Story**.
3. Enter the required details in the user story creation form.
4. Click **Create** to save the user story.

<figure><img src="../../../.gitbook/assets/image (1979).png" alt=""><figcaption></figcaption></figure>

5. Click on the **Action** button and select **Edit**.

<figure><img src="../../../.gitbook/assets/image (1980).png" alt=""><figcaption></figcaption></figure>

6. Go to the BTP Applications and click on the "Add " button&#x20;

<figure><img src="../../../.gitbook/assets/image (1981).png" alt=""><figcaption></figcaption></figure>

6. Select the required **BTP Application** and click **Next**.
7. &#x20;Configure the **Source Reference**:
   * **Feature Branch**: If **Feature Branch** was selected as the **Transport Mode** during the creation of the BTP Application, the feature branch option will be available while adding the application to the user story. Select the required feature branch as the source reference.
   * **Cherry Pick**: If **Cherry Pick** was selected as the transport mode, the **Source Reference** field will display the available commits. Select the required commit(s) to be included in the build.
8. Review the selected configuration and verify that all details are correct.
9. Click **Finish** to add the build application.

<div><figure><img src="../../../.gitbook/assets/image (1983).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (1982).png" alt=""><figcaption></figcaption></figure></div>

<figure><img src="../../../.gitbook/assets/image (1984).png" alt=""><figcaption></figcaption></figure>

10. Users can select and promote multiple builds simultaneously from a User Story, making the promotion process more efficient when managing multiple build logs.

* Select one or more builds from the User Story.
* Click **Promote** to initiate the deployment process.
* Click **Deploy** **Logs** to view the deployment details.

<div><figure><img src="../../../.gitbook/assets/image (1988).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (1987).png" alt=""><figcaption></figcaption></figure></div>

<figure><img src="../../../.gitbook/assets/image (1989).png" alt=""><figcaption></figcaption></figure>

**Build Logs**

The **Build Logs** page displays the execution details of the **CAP Application Build Task** configured in the Release Pipeline. These logs help users monitor the build process, verify successful execution, and troubleshoot any build failures.

<div><figure><img src="../../../.gitbook/assets/image (1994).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (1994).png" alt=""><figcaption></figcaption></figure></div>
