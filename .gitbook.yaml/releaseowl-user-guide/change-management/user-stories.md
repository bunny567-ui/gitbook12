# User Stories

To  Sync user stories using an ALM integration (e.g., JIRA), follow these steps:

1\) Navigate to the **User Stories** section under **Change Management**.

2\) Click the **Sync User Stories** option from the User Stories screen. The user stories from the external system will be synced and displayed in the **User Stories** screen.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
&#x20;**Note:** Clicking **Sync User Stories** will synchronize records of all issue types from the externally integrated ALM project into ReleaseOwl.

a) If the project you are working on is associated with an external system (e.g., JIRA), any user stories from that system will appear in the **User Stories** screen after syncing.

b) Always ensure to **sync the Sprints first** before syncing the User Stories.
{% endhint %}

3\) Click **OK**. The user stories created in the external system will be synced to ReleaseOwl and will appear on the **User Stories** screen.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4\) To view previously performed sync actions, click on **Sync History**.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note : Column widths** for **User Story ID, Status, Type, and Assigned To** now auto-adjust based on content.

* **Summary** and **Pipeline Status** columns have a fixed maximum width, capped at **20% of the table**.
{% endhint %}

### Creating User Stories Without ALM Integration

To create user stories manually for systems not integrated through ALM , follow these steps:

1\) To create a new user story manually, click the **Create New User Story** button.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2\) Enter the following details and click **Save**:

| **Field**           | **Description**                                                                                                                                                               |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**         | A summary of the user story being created.                                                                                                                                    |
| **Description**     | A detailed description of the user story being created.                                                                                                                       |
| **Type**            | Default type is **Story**. Available issue types: **Story**, **Task**, **Sub-task**, **Bug**, **Issue**, **Epic**, **Incident**. Any issue type can be created in ReleaseOwl. |
| **Assigned To**     | Select the user to whom the user story is to be assigned.                                                                                                                     |
| **Sprint**          | The sprint in which the user story will be handled.                                                                                                                           |
| **Release Version** | The version of the release in which the user story will get released.                                                                                                         |

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3\) The user story gets created and gets listed in the **User Story** grid.

4\) You can delete user stories by clicking the **Delete** button.

<figure><img src="../../.gitbook/assets/image (1093).png" alt=""><figcaption></figcaption></figure>

5\) The following columns are seen for a user story:

<figure><img src="../../.gitbook/assets/image (1092).png" alt=""><figcaption></figcaption></figure>

| **Field**                    | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User Story**               | Represents the user story being tracked.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **User Story ID**            | Unique identifier for the user story.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Summary**                  | A brief description of the user story.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Status**                   | Current status of the user story. **Status options**: To Do, In Progress, QA Ready, Prod Ready, Done                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Type**                     | Issue type of the user story. Available types: **Story**, **Task**, **Sub-task**, **Bug**, **Issue**, **Epic**, **Incident**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **External ID**              | ID of the user story from an external system (e.g., JIRA or ServiceNow), shown if the project is integrated with external systems.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Assigned To**              | The user to whom the issue type is assigned.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Validation Status Filter** | <p>The <strong>Validation Status</strong> shows the current stage of the user story validation process. The possible statuses are:</p><ul><li><strong>Not Validated</strong>: Validation has not yet started for this user story.</li><li><strong>Started</strong>: The validation process has been initiated.</li><li><strong>In Progress</strong>: Validation is actively running and not yet completed.</li><li><strong>Success</strong>: Validation is completed successfully without any errors.</li><li><strong>Review Pending</strong>: Validation is completed, but the results are awaiting manual review.</li><li><strong>Review Completed</strong>: The validation review has been completed and closed.</li></ul> |
| **Pipeline Stage**           | Default value is **Dev**. Updates to the next stage upon each promotion in the release pipeline.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Pipeline Status**          | Status of the release pipeline execution.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Actions**                  | <p>Actions available for the user story: <strong>Edit</strong>, <strong>Validate</strong>, <strong>Validation Report</strong>, <strong>Promote</strong>, <strong>Pipeline Activity</strong>. </p><p></p><p><em><strong>Note</strong></em><strong>:</strong> Promote not available for MTAR applications.</p>                                                                                                                                                                                                                                                                                                                                                                                                                  |

6\) When you click the **Action** button, you will see the list of available actions that can be performed on the user story.

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

| **Action**            | **Description**                                                                                                |
| --------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Edit**              | To edit a user story.                                                                                          |
| **Validate**          | To validate the user story.                                                                                    |
| **Validation Report** | To view the validation report. _**Note**_**:** This option becomes available once the validation is triggered. |
| **Promote**           | Triggers the release pipeline associated with the project, as configured in **Project Settings**.              |
| **Pipeline Activity** | View various stages, tasks, and execution status of the triggered release pipeline.                            |
| **Delete**            | You can delete the existing user story.                                                                        |

7\) The Validation Report will look as follows:

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

8\) On clicking the **Pipeline Activity**, you can view the release pipeline execution status as follows:

<figure><img src="../../.gitbook/assets/image (1123).png" alt=""><figcaption></figcaption></figure>

9\) **Options in Pipeline Activity Screen (Right Panel)**\
The right side of the **Pipeline Activity** screen contains the following options:

* **Abort:**\
  This button allows users to stop a currently running pipeline activity. When clicked, a confirmation prompt appears. Upon confirmation, the pipeline status is updated to **Aborted** for the respective task.&#x20;

<figure><img src="../../.gitbook/assets/image (1124).png" alt=""><figcaption></figcaption></figure>

* The **Pipeline Stage** and **Pipeline Status** of the related user story are also updated to **Aborted**.

<figure><img src="../../.gitbook/assets/image (1125).png" alt=""><figcaption></figcaption></figure>

* **History**:&#x20;

This option displays the execution history of the release pipeline, including details such as the number of times the pipeline was executed, who triggered each execution, and the status of each run.&#x20;

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1126).png" alt=""><figcaption></figcaption></figure>

* When you click on the arrow button (**>**), you are taken to the **Pipeline Activity** screen.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1127).png" alt=""><figcaption></figcaption></figure>

**Refresh**:&#x20;

This button allows you to update the Pipeline Activity screen with the latest information. When you click on the Refresh button, it reloads the current status of the release pipeline to reflect any recent changes or updates.

<figure><img src="../../.gitbook/assets/image (1128).png" alt=""><figcaption></figcaption></figure>

### Release Audit Report&#x20;

You have the option to export the details as a **Release Audit Report**. The exported document provides comprehensive information to help track and communicate the progress of the user story.

<figure><img src="../../.gitbook/assets/image (15) (1) (1).png" alt=""><figcaption></figcaption></figure>

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
5.  **Approval and Audit Summary**

    *   A comprehensive summary of:

        * Approvals obtained for the user story.
        * Audit trails detailing all actions taken.



    <figure><img src="../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## **Deputy Users** <a href="#pdf-page-shdnuqg7ccu0ghnrleue-deputy-users" id="pdf-page-shdnuqg7ccu0ghnrleue-deputy-users"></a>

Deputy users can manage tasks when the primary user is unavailable.

### **Assigning Deputy Users** <a href="#pdf-page-shdnuqg7ccu0ghnrleue-assigning-deputy-users" id="pdf-page-shdnuqg7ccu0ghnrleue-assigning-deputy-users"></a>

1. Click on your **profile icon** in the **top-right corner** and select **Profile**.

<figure><img src="../../.gitbook/assets/image (1385).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FE49EJn3ILQJCINDjrA9T%252Fimage.png%3Falt%3Dmedia%26token%3D89c2479a-7660-4f8e-a98a-ff1a3fb530a7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=62ba9383&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. Click on the **Deputy Users** tab next to "**Projects**."
3. Click the **Add** button, and a **pop-up screen** will appear.

<figure><img src="../../.gitbook/assets/image (1386).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F3NtKufj5jqZs7trYak96%252Fimage.png%3Falt%3Dmedia%26token%3D1cf9fd33-627d-4c1f-9ada-ce103853f831&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=baf7a62c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. **Select Project & User:**

* Select the project for which you want to assign a deputy.
* Search for the **User** in the system and select them.

5. Click the **Create** button to assign deputy permissions to the selected user.

<figure><img src="../../.gitbook/assets/image (1387).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fh2FU3rOpviu3Pup51P6b%252Fimage.png%3Falt%3Dmedia%26token%3D1d39bf9b-4673-456c-a3c6-0351afd6eead&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6b79f391&#x26;sv=2" alt=""><figcaption></figcaption></figure>

6. When a user story is promoted, the assigned Deputy User will receive an approval request. The Deputy User can then navigate to the **My Tasks** section and go to the **Tasks** tab.&#x20;
7. In the **Action** column, they can choose to **Approve** or **Reject** the request.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FKW21vajbvqYWmHIWwwKU%252Fimage.png%3Falt%3Dmedia%26token%3D5ed024a6-d23a-4217-a1e8-a9992e157243&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=54cd62c7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

8. When you click on the **Approve/Reject** button, a detailed view will appear, displaying relevant information about the user story.&#x20;
9. The Deputy User can review this information before making a decision to approve or reject the user story promotion.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FZ3zjGoeTsHBwWFCjGpAU%252Fimage.png%3Falt%3Dmedia%26token%3Dbade8a64-b497-4c0e-a9c4-0f086ac40faa&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=61f71a41&#x26;sv=2" alt=""><figcaption></figcaption></figure>

10. When the task is approved, a confirmation message will appear. In the **Pipeline Activity** section, you can see the task marked as **completed**, along with the name of the **Deputy User** who approved it.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fo8BTyNeMrKtsJwQQhZwG%252Fimage.png%3Falt%3Dmedia%26token%3D69a51b6f-ffe2-45dd-b055-d436977e3aa7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ae4505c4&#x26;sv=2" alt=""><figcaption></figcaption></figure>

11. In the **Deputy Tasks** section, the **Deputy User** can view the **task status**, including the **task name, reference ID, stage, task type, delivery time, assigned to, and action**.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F6bieUIzzV1b8mUVSrVfp%252Fimage.png%3Falt%3Dmedia%26token%3Dc6ddad2e-bf51-4ea9-bc21-950781fe70ad&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b8ca79a5&#x26;sv=2" alt=""><figcaption></figcaption></figure>

12. When you check the **History** in the **My Tasks** section, you can see a record of all actions taken, including approvals, rejections, and task completions, along with the corresponding timestamps and the user who performed each action.

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
