# Types of Tasks

While creating a release pipeline of any type, click **Add** under Tasks section to enter any tasks that are to be performed.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-1.jpg" alt=""><figcaption></figcaption></figure>

Different tasks that can be added are as follows:

<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-2.jpg" alt=""><figcaption></figcaption></figure>

**Note:**

1. Certain **tasks** are common for **any project type – Approvals, Manual Task, Callout, Test Execution, User Story Status Update.**
2. **Wait for Promotion** and **Validation** tasks are **available only** for **On-Prem** and **CPI** projects.
3. **Deployment** tasks **vary** for **every project type**.

### 1) Approval Task

If the deployment needs any prior approval, then add an approval task.\


<figure><img src="../../.gitbook/assets/image (816).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**                       | Enter any name of your choice for the approval task being created.                                                                                                                                                                  |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Assign To**                  | <p><strong>User</strong> – The approver (user) can be selected from the available list of users for approving the task.<br><br><strong>Role</strong> - The task can be approved by any user with the user role that is selected</p> |
| **Message**                    | Any message that is to be conveyed to the task approver can be mentioned here.                                                                                                                                                      |
| **Custom**                     | Used to assign a set of components and a specific role to the users for approving the task.                                                                                                                                         |
| **Story Assignee**             | The task will be assigned to the user who is the assignee of the related story in the pipeline                                                                                                                                      |
| **Disable Email Notification** | Users will not receive the approval email link but will get a notification only about the final status (approved/rejected).                                                                                                         |

{% hint style="info" %}
**Note:** The Approval Tasks assigned to a user appear under his/her **My Tasks** section upon logging in to **ReleaseOwl**. The user can either **accept** or **reject**.
{% endhint %}

### **2) Callout Task**

A callout task can be added if a third-party REST API has to be called from ReleaseOwl.

The following screen is displayed on adding a Callout task:\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-4.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**               | Enter any name of your choice for the approval task being created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Callouts**           | Choose the required callout from the drop down.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Config Params**      | Parameters specified in the Payload JSON can be passed during run-time through the Config Params option.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Pipeline Execution** | <p><strong>Continue on Failure</strong> – If selected, the Release Pipeline Execution will continue even if the callout fails.<br><br>If the option is left <strong>unchecked</strong>, then the pipeline execution fails if it encounters any error in calling out the external API.<br><br><strong>Wait on Task</strong> – If selected, then approval task will be created after the callout execution even if callout fails or succeeds. Users can open the task and retry callout execution in case of callout failure.<br><br>If the option is left <strong>unchecked</strong>, it will act as a normal web service call which calls out external API and continues based on the response of the external API.<br><br><strong>User</strong> – The approver (user) can be selected from the available list of users for approving the pending task in order to complete the Release Pipeline execution when Wait on Task option is chosen.<br><br><strong>Role</strong> - The pending task can be approved by any user with the user role that is selected in order to complete the Release Pipeline execution when Wait on Task option is chosen.</p> |
| **Message**            | Any message that is to be conveyed to the task approver can be mentioned here.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

On clicking the **Config Params** button, the following screen is displayed. Enter the variable parameter names specified in the Payload JSON along with their values that are to be passed run-time during the execution of the Release Pipeline and save the changes.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-5.jpg" alt=""><figcaption></figcaption></figure>

#### **System Defined Parameters for a Callout Task - Generic**

Below are the variables available for using as values in the configure parameters for a callout Task.

| **${jobins.jobCycleName}**   | Cycle name given while triggering the Release Pipeline.                                   |
| ---------------------------- | ----------------------------------------------------------------------------------------- |
| **${jobins.instantiatedBy}** | Email ID of the person who triggered the Release Pipeline                                 |
| **${jobins.label}**          | Release Pipeline Name                                                                     |
| **${jobins.status}**         | Status of the instance/cycle                                                              |
| **${jobins.endTime}**        | <p>End time when instance is completed.<br>(YYYY-MM-DDTHH24:MM:SS.000+0000)</p>           |
| **${jobins.createTime}**     | <p>Represents the time when instance was created.<br>(YYYY-MM-DDTHH24:MM:SS.000+0000)</p> |
| **${jobins.startTime}**      | <p>Represents the time when instance was started<br>(YYYY-MM-DDTHH24:MM:SS.000+0000)</p>  |

\


#### **System Defined Parameters specific to the Release Pipelines of type SAP BTP**

| **${jobins.inputs.buildJobName}** | Name of the build pipeline used as an input for the Release Pipeline.                                                                |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **${jobins.inputs.buildNumber}**  | Build number of the build pipeline (given as input in the Release pipeline), artifact is used for deploying in the Release Pipeline. |

### 3) Manual Task

If after the deployment is done and any post deployment changes such as changing the configuration files manually or manual test execution etc. are to be done, then add a manual task.

The following screen is displayed on adding a manual task.

<figure><img src="../../.gitbook/assets/image (817).png" alt=""><figcaption></figcaption></figure>

**Fill in the required details:**

| **Name**                       | Enter any name of your choice for the manual task being created.                                                                                                                                       |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Assign To**                  | <p><strong>User</strong> – The user can be selected from the available list of users for completing the task.<br>Role - The task can be completed by any user with the user role that is selected.</p> |
| **Message**                    | Any message that is to be conveyed to the task performer can be mentioned here.                                                                                                                        |
| **Custom**                     | Used to assign a set of components and a specific role to the users for completing the task.                                                                                                           |
| **Story Assignee**             | The task will be assigned to the user who is the assignee of the related story in the pipeline                                                                                                         |
| **Disable Email Notification** | Users will not receive the approval email link but will get a notification only about the final status (approved/rejected).                                                                            |



{% hint style="info" %}
**Note:** The Manual Tasks assigned to a user appear under his/her **My Tasks** section upon logging in to **ReleaseOwl**. The user has to click **Complete** after executing the task manually.
{% endhint %}

### **4) User Story Status Task**&#x20;

The status of a user story can be set to a specific value once the deployment takes place in an environment.

The following screen is displayed on adding a user story status task.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-7.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**              | Enter any name of your choice for the user story status task being created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User Story Status** | <p>Select appropriate status to which the current status of the user story has to be changed once the deployment to specific environment is done.<br><br>The available status options are:<br><br>To Do – The user story status can be reset to - To Do once the deployment is done in any specific environment. For e.g., the same user story can be deployed to multiple environments one after the other and in each stage the status has to be reset to - To Do as the process has to be repeated.<br><br>In Progress – The user story status can be set to In Progress when the implementation of user story is still work in progress or done in a phased manner .<br><br>Ready for QA – The user story status can be set to Ready for QA once the deployment is done in QA and is available for testing.<br><br>Done - The user story status can be set to done once working with the user story is complete after deploying the changes to the specific environment.</p> |

### **5)Test Execution Task**&#x20;

ReleaseOwl can be integrated with HCL OneTest UI using which functional and web tests can be executed in any specific environment once the deployment is complete to check if the functionality is as desired.

The following screen is displayed on adding a test execution task.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-8.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**                      | Enter any name of your choice for the test execution task being created.                                                 |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Select Test Configuration** | Select appropriate test configuration from the list available that you have registered in the Test Configuration screen. |

{% hint style="info" %}


**Note:**

1. **Any** task added can be deleted by clicking Remove
2. Please refer to **Automated CPI Deployments** and **Automated Transport Import** for information on **Deployment (CPI), Waiting for Promotion** and **Validation** tasks.
3. Please refer to **Automated MTAR Deployments, Automated CPI Deployments, Automated Transport Import** documents for their **respective Deployment** tasks.
{% endhint %}

### 6) Message Listener

The **Message Listener Task** is designed to wait for specific message events and acts upon receiving them during the pipeline execution. Fill in the required details:

| **Field**            | **Description**                                                                             |
| -------------------- | ------------------------------------------------------------------------------------------- |
| **Task Name**        | Auto-filled with the task name, e.g., `Message_Listener_INTEGRATION`.                       |
| **Wait for Message** | Specify the event or message that the task should listen for before proceeding.             |
| **Assign Variables** | Allows assigning variables that will be utilized or populated when the message is received. |
| **Message Template** | Defines the structure or format of the expected message event.                              |

<figure><img src="../../.gitbook/assets/image (688).png" alt=""><figcaption></figcaption></figure>

### 7) GCTS Merge Task

This Task is used when a hotfix changes need to be merged to other development branches. After a major release of a project, the changes from the master branch can be merged to other development branches.

Fill in the required details:

| **Field** | **Details** |
| --------- | ----------- |

| **Name**             | Enter a unique name for the GCTS Merge task of your choice.                                                          |
| -------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **GCTS Environment** | Select the source and target GCTS environments from the dropdown menu . This defines the environments for the merge. |

| **Domain Controller** | Automatically populated based on the selected GCTS environment. It indicates the transport controller responsible for managing the process. |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |

| **System ID (SID)** | Auto-filled field that uniquely identifies the systems involved (e.g., `S4D.100`). Ensures proper linkage between environments. |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------- |

| **GCTS Repository (Repo)** | Select the repository from the dropdown menu  in the source environment. The corresponding repository in the target environment is automatically displayed. |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |

| **Branch**        | The source branch (e.g., `dev`) must be selected manually from the dropdown menu, and the target branch (e.g., `qa`) must also be selected to ensure proper branch mapping. |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Notify Users**  | Sends notifications to relevant stakeholders when the merge is complete. This ensures transparency and keeps teams informed of changes.                                     |
| **Forward Merge** | Automatically propagates the merged changes according to the system landscape hierarchy, such as **dev → QA → preprod → prod**.                                             |

<figure><img src="../../.gitbook/assets/image (168).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (169).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note** : If you are moving from dev to prod directly without going through quality, you don't need to check the forward merge.
{% endhint %}

### 8) GCTS Activate Task&#x20;

This Task is used when a system needs to be updated to latest commit of the associated branch.

Fill in the required details:

| **Field**            | **Description**                                                                                              |
| -------------------- | ------------------------------------------------------------------------------------------------------------ |
| **Task Name**        | Auto-populated with the name from the GCTS Merge task.                                                       |
| **GCTS Environment** | Select the target environment (e.g., development, quality, or production) where the activation should occur. |
| **GCTS Repository**  | Choose the appropriate Git repository that contains the changes to be activated.                             |



<figure><img src="../../.gitbook/assets/image (687).png" alt=""><figcaption></figcaption></figure>

### 9) GCTS Switch Task

This task is used when a branch associated to the system needs to be changed to another branch for e.g. if a UAT system is pointing to “**QA**” branch and a hotfix needs to be verified then this task can used to switch to “**Hotfix**” branch.

**Fill in the required details:**

| **Field** | **Description** |
| --------- | --------------- |

| **Task Name** | Auto-populated with the name related to the GCTS Switch task. |
| ------------- | ------------------------------------------------------------- |

| **GCTS Environment** | Select the target environment (e.g., development, quality, or production) where the switch should occur. |
| -------------------- | -------------------------------------------------------------------------------------------------------- |

| **GCTS Repository** | Choose the appropriate Git repository for which the switching of branches or configurations is to be done. |
| ------------------- | ---------------------------------------------------------------------------------------------------------- |

<figure><img src="../../.gitbook/assets/image (170).png" alt=""><figcaption></figcaption></figure>

### 10) Import via Toc Task&#x20;

Once a transport is released, no further changes can be made to it. If a fix is required, a new transport must be created. However, a more efficient alternative is **Transport of Copies (TOC)**.

**Fill in the required details:**

| **Field**                  | **Description**                                                                                  |
| -------------------------- | ------------------------------------------------------------------------------------------------ |
| **Task Name**              | Auto-filled with the task name, e.g., `Import_via_TOC_INTEGRATION`.                              |
| **Domain Controller**      | Specifies the domain controller managing the transport landscape, e.g., `IntegrationSystemTest`. |
| **Target System**          | Select the system where the transport copy will be imported, e.g., `DMO`.                        |
| **Schedule Time**          | Allows scheduling the import at a specific date and time in the format `yyyy-MM-ddTHH:mm:ss`.    |
| **Notify Users**           | Enables notifications to users upon task completion or failure.                                  |
| **Notify Transport Users** | Sends notifications specifically to transport users involved in the task.                        |

<figure><img src="../../.gitbook/assets/image (689).png" alt=""><figcaption></figcaption></figure>

### 11) Transport Retrofit Task&#x20;

The **Transport Retrofit Task** is used to **apply the same changes** across **parallel landscapes.**

**Fill in the required details:**

| **Field** | **Description** |
| --------- | --------------- |

| **Task Name** | Auto-filled with the task name, e.g., `Transport_Retrofit_INTEGRATION`. |
| ------------- | ----------------------------------------------------------------------- |

| **Notify Users** | Option to notify specific users about the task's progress or completion. |
| ---------------- | ------------------------------------------------------------------------ |

| **Notify Transport Users** | Option to notify transport-specific users involved in the retrofit process. |
| -------------------------- | --------------------------------------------------------------------------- |

<figure><img src="../../.gitbook/assets/image (690).png" alt=""><figcaption></figcaption></figure>

### 12) Release Transport Task

The **Release Transport Task** is responsible for automating the **manual transport release** process that typically occurs before deployment. Instead of manually releasing transports in the **Transport Management System (TMS)**, this task ensures that transports are released within the pipeline itself before they are imported into the target system.

**Fill in the required details:**

| **Field** | **Description** |
| --------- | --------------- |

| **Task Name** | Predefined task name, such as `Release_Transport_INTEGRATION`, which identifies the specific task in the pipeline. |
| ------------- | ------------------------------------------------------------------------------------------------------------------ |

| **Notify Users** | Checkbox option to notify selected users about the status or completion of the release transport task. |
| ---------------- | ------------------------------------------------------------------------------------------------------ |

| **Notify Transport Users** | Checkbox option to notify transport-specific users directly involved in the release process. |
| -------------------------- | -------------------------------------------------------------------------------------------- |

