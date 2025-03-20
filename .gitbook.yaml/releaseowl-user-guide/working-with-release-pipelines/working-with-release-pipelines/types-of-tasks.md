# Types of Tasks

While creating a release pipeline of any type, click Add under Tasks section to enter any tasks that are to be performed.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-1.jpg" alt=""><figcaption></figcaption></figure>

Different tasks that can be added are as follows:\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-2.jpg" alt=""><figcaption></figcaption></figure>

**Note:**

1. Certain **tasks** are common for **any project type – Approvals, Manual Task, Callout, Test Execution, User Story Status Update.**
2. **Wait for Promotion** and **Validation** tasks are **available only** for **On-Prem** and **CPI** projects.
3. **Deployment** tasks **vary** for **every project type**.

i) **Approval Task** – If the deployment needs any prior approval, then add an approval task.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-3.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**      | Enter any name of your choice for the approval task being created.                                                                                                                                                                  |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Assign To** | <p><strong>User</strong> – The approver (user) can be selected from the available list of users for approving the task.<br><br><strong>Role</strong> - The task can be approved by any user with the user role that is selected</p> |
| **Message**   | Any message that is to be conveyed to the task approver can be mentioned here.                                                                                                                                                      |

\


**Note:** The Approval Tasks assigned to a user appear under his/her **My Tasks** section upon logging in to **ReleaseOwl**. The user can either **accept** or **reject**.

ii) **Callout Task** – A callout task can be added if a third-party REST API has to be called from ReleaseOwl.

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

\


On clicking the **Config Params** button, the following screen is displayed. Enter the variable parameter names specified in the Payload JSON along with their values that are to be passed run-time during the execution of the Release Pipeline and save the changes.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-5.jpg" alt=""><figcaption></figcaption></figure>

**System Defined Parameters for a Callout Task - Generic**

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


**System Defined Parameters specific to the Release Pipelines of type SAP BTP**

| **${jobins.inputs.buildJobName}** | Name of the build pipeline used as an input for the Release Pipeline.                                                                |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **${jobins.inputs.buildNumber}**  | Build number of the build pipeline (given as input in the Release pipeline), artifact is used for deploying in the Release Pipeline. |

\


iii) **Manual Task** - If after the deployment is done and any post deployment changes such as changing the configuration files manually or manual test execution etc. are to be done, then add a manual task.

The following screen is displayed on adding a manual task.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-6.jpg" alt=""><figcaption></figcaption></figure>

**Fill in the required details:**

| **Name**      | Enter any name of your choice for the manual task being created.                                                                                                                                      |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Assign To** | <p><strong>User</strong> – The user can be selected from the available list of users for completing the task.<br>Role - The task can be completed by any user with the user role that is selected</p> |
| **Message**   | Any message that is to be conveyed to the task performer can be mentioned here.                                                                                                                       |

\


**Note:** The Manual Tasks assigned to a user appear under his/her **My Tasks** section upon logging in to **ReleaseOwl**. The user has to click **Complete** after executing the task manually.

iv) **User Story Status Task** – The status of a user story can be set to a specific value once the deployment takes place in an environment.

The following screen is displayed on adding a user story status task.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-7.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**              | Enter any name of your choice for the user story status task being created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User Story Status** | <p>Select appropriate status to which the current status of the user story has to be changed once the deployment to specific environment is done.<br><br>The available status options are:<br><br>To Do – The user story status can be reset to - To Do once the deployment is done in any specific environment. For e.g., the same user story can be deployed to multiple environments one after the other and in each stage the status has to be reset to - To Do as the process has to be repeated.<br><br>In Progress – The user story status can be set to In Progress when the implementation of user story is still work in progress or done in a phased manner .<br><br>Ready for QA – The user story status can be set to Ready for QA once the deployment is done in QA and is available for testing.<br><br>Done - The user story status can be set to done once working with the user story is complete after deploying the changes to the specific environment.</p> |

\


v) **Test Execution Task** – ReleaseOwl can be integrated with HCL OneTest UI using which functional and web tests can be executed in any specific environment once the deployment is complete to check if the functionality is as desired.

The following screen is displayed on adding a test execution task.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/types-of-tasks-8.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**                      | Enter any name of your choice for the test execution task being created.                                                 |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Select Test Configuration** | Select appropriate test configuration from the list available that you have registered in the Test Configuration screen. |

\


**Note:**

1. **Any** task added can be deleted by clicking Remove
2. Please refer to **Automated CPI Deployments** and **Automated Transport Import** for information on **Deployment (CPI), Waiting for Promotion** and **Validation** tasks.
3. Please refer to **Automated MTAR Deployments, Automated CPI Deployments, Automated Transport Import** documents for their **respective Deployment** tasks.
