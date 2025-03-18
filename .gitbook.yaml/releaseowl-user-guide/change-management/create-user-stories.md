# Create User Stories

1\) You can find User Stories under Change Management section as shown below:\


<figure><img src="../../.gitbook/assets/image (679).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:**

a) If the project that you are working with is associated with any external system say like JIRA, and if it has any user stories, they appear in the User Stories screen upon sync’ing.

b) Always remember to sync the Sprints first and then the User Stories.
{% endhint %}

2\) Click Sync User Stories option from the User Stories screen. The user stories from the external system gets synced to the User Stories screen.

{% hint style="info" %}
**Note:** On clicking Sync User Stories, records of all issue types of the external integrated ALM project will be synced to ReleaseOwl.
{% endhint %}

<figure><img src="https://www.docs.releaseowl.com/assets/img/create-user-stories-2.jpg" alt=""><figcaption></figcaption></figure>

3\) Click **OK**. The user stories created in the external system gets synced to ReleaseOwl and appear in the User Stories screen.

<figure><img src="https://www.docs.releaseowl.com/assets/img/create-user-stories-3.jpg" alt=""><figcaption></figcaption></figure>

4\) You can view the sync actions performed earlier by clicking the Sync History.

<figure><img src="https://www.docs.releaseowl.com/assets/img/create-user-stories-4.jpg" alt=""><figcaption></figcaption></figure>

5\) You can create a new user story by clicking Create New User Story link.

<figure><img src="https://www.docs.releaseowl.com/assets/img/create-user-stories-5.jpg" alt=""><figcaption></figcaption></figure>

6\) Enter the following details and click Save:

| **Summary**     | A summary of the user story being created.                                                                                                                                                                 |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Description** | A detailed description of the user story being created.                                                                                                                                                    |
| **Type**        | <p>Story is the default type shown.<br>Several issue types are available in ReleaseOwl. They are:<br>Story, Task, Sub-task, Bug, Issue, Epic, Incident<br>You can create any issue type in ReleaseOwl.</p> |
| **Assigned To** | Select the user to whom the user story is to be assigned.                                                                                                                                                  |
| **Sprint**      | The sprint in which the user story will be handled.                                                                                                                                                        |
| Release Version | The version of the release in which the user story will get released.                                                                                                                                      |

7\) The user story gets created and gets listed in the User Story grid as follows:

<figure><img src="../../.gitbook/assets/image (681).png" alt=""><figcaption></figcaption></figure>

8\) The following columns are seen for a user story:

<figure><img src="../../.gitbook/assets/image (682).png" alt=""><figcaption></figcaption></figure>

| **User Story**        | User Story ID                                                                                                                                                                                                      |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Summary**           | A brief description of the user story.                                                                                                                                                                             |
| **Status**            | <p>The Status of the User Story.<br>Following are the status options for a user story:<br>To Do<br>In Progress<br>QA Ready<br>Prod Ready<br>Done</p>                                                               |
| **Type**              | Issue Type - Story, Task, Sub-task, Bug, Issue, Epic, Incident                                                                                                                                                     |
| **External ID**       | The User Story ID from the external system is shown if the project is integrated with external systems such as JIRA or ServiceNow.                                                                                 |
| **Assigned To**       | The user to which the issue type is to be assigned.                                                                                                                                                                |
| **Validation Status** | The Validation Status of the User Story – Success or Completed with Errors.                                                                                                                                        |
| **Pipeline Stage**    | The default value is Dev. Once the user story or the corresponding release pipeline is promoted, the first available stage will be seen and thereafter on every promotion, the next subsequent stage will be seen. |
| **Pipeline Status**   | The status of the release pipeline execution.                                                                                                                                                                      |
| **Actions**           | <p>The actions that can be performed on a user story – Edit, Validate, Validation Report, Promote, Pipeline Activity.<br>Note: The promote option is not available for MTAR applications.</p>                      |

9\) The user story gets created and gets listed in the User Story grid as follows:

<figure><img src="https://www.docs.releaseowl.com/assets/img/create-user-stories-8.jpg" alt=""><figcaption></figcaption></figure>

| **Edit**              | To edit a User Story                                                                                                 |
| --------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Validate**          | To validate the user story.                                                                                          |
| **Validation Report** | To view the Validation Report and this option is seen once the validation gets triggered.                            |
| **Promote**           | This option is used to trigger a Release Pipeline that which is associated with the project in the Project Settings. |
| **Pipeline Activity** | The various stages, tasks and the execution status of the release pipeline triggered can viewed.                     |

10\) The Validation Report will look as follows:\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/create-user-stories-9.jpg" alt=""><figcaption></figcaption></figure>

11\) On clicking the Pipeline Activity, you can view the release pipeline execution status as follows:

<figure><img src="../../.gitbook/assets/image (680).png" alt=""><figcaption></figcaption></figure>

#### **Exporting User Story Details as a PDF**

&#x20;You have the option to export the details as a **PDF**. The exported document provides comprehensive information to help track and communicate the progress of the user story.

<figure><img src="../../.gitbook/assets/image (723).png" alt=""><figcaption></figcaption></figure>

The exported PDF provides the following comprehensive information:

1. **Release Summary**
   * A high-level overview of the release associated with the user story.
2. **Stage-by-Stage Deployment Details**
   * Detailed deployment information for each stage of the pipeline.
3. **Code and Artifact Changes Summary**
   * A summary of the changes made to the code and associated artifacts, ensuring clarity on what has been modified.
4. **Traceability Matrix**
   * Links between:
     * Requirements
     * User stories
     * Code changes
     * Deployment stages
   * This ensures end-to-end traceability for audit and review purposes.
5. **Approval and Audit Summary**
   * A comprehensive summary of:
     * Approvals obtained for the user story.
     * Audit trails detailing all actions taken.

<figure><img src="../../.gitbook/assets/image (724).png" alt=""><figcaption></figcaption></figure>

### **Deputy Users**

Deputy users can manage tasks when the primary user is unavailable.

### **Assigning Deputy Users**

1. Click on your **profile icon** in the **top-right corner** and select **Profile**.

<figure><img src="../../.gitbook/assets/image (868).png" alt=""><figcaption></figcaption></figure>

2. Click on the **Deputy Users** tab next to "**Projects**."
3. &#x20;Click the **Add** button, and a **pop-up screen** will appear.

<figure><img src="../../.gitbook/assets/image (869).png" alt=""><figcaption></figcaption></figure>

4. **Select Project & User:**&#x20;

* Select the project for which you want to assign a deputy.
* Search for the **User** in the system and select them.

5. Click the **Create** button to assign deputy permissions to the selected user.

<figure><img src="../../.gitbook/assets/image (867).png" alt=""><figcaption></figcaption></figure>

When a user story is promoted, the assigned Deputy User will receive an approval request. The Deputy User can then navigate to the **My Tasks** section and go to the **Tasks** tab. In the **Action** column, they can choose to **Approve** or **Reject** the request.

<figure><img src="../../.gitbook/assets/image (925).png" alt=""><figcaption></figcaption></figure>

When you click on the **Approve/Reject** button, a detailed view will appear, displaying relevant information about the user story.  The Deputy User can review this information before making a decision to approve or reject the user story promotion.

<figure><img src="../../.gitbook/assets/image (876).png" alt=""><figcaption></figcaption></figure>

When the task is approved, a confirmation message will appear. In the **Pipeline Activity** section, you can see the task marked as **completed**, along with the name of the **Deputy User** who approved it.

<figure><img src="../../.gitbook/assets/image (874).png" alt=""><figcaption></figcaption></figure>

In the **Deputy Tasks** section, the **Deputy User** can view the **task status**, including the **task name, reference ID, stage, task type, delivery time, assigned to, and action**.

<figure><img src="../../.gitbook/assets/image (926).png" alt=""><figcaption></figcaption></figure>

When you check the **History** in the **My Tasks** section, you can see a record of all actions taken, including approvals, rejections, and task completions, along with the corresponding timestamps and the user who performed each action.

<figure><img src="../../.gitbook/assets/image (877).png" alt=""><figcaption></figcaption></figure>

