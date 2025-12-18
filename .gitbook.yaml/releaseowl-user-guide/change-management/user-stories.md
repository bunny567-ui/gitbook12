# User Stories

To  Sync user stories using an ALM integration (e.g., JIRA), follow these steps:

1\) Navigate to the **User Stories** section under **Change Management**.

2\) Click the **Sync User Stories** option from the User Stories screen. The user stories from the external system will be synced and displayed in the **User Stories** screen.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) ( (3).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
&#x20;**Note:** Clicking **Sync User Stories** will synchronize records of all issue types from the externally integrated ALM project into ReleaseOwl.

a) If the project you are working on is associated with an external system (e.g., JIRA), any user stories from that system will appear in the **User Stories** screen after syncing.

b) Always ensure to **sync the Sprints first** before syncing the User Stories.
{% endhint %}

3\) Click **OK**. The user stories created in the external system will be synced to ReleaseOwl and will appear on the **User Stories** screen.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4\) To view previously performed sync actions, click on **Sync History**.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :**  The column widths for **User Story ID**, **Status**, **Type**, and **Assigned To** are now dynamically adjusted based on content length. The **Summary** and **Pipeline Status** columns are restricted to a maximum width of **20%** of the table to maintain layout consistency and prevent overflow.
{% endhint %}

### Creating User Stories Without ALM Integration

To create user stories manually for systems not integrated through ALM , follow these steps:

1\) To create a new user story manually, click the **Create New User Story** button.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2\) Enter the following details and click **Save**:

| **Field**           | **Description**                                                                                                                                                               |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Summary**         | A summary of the user story being created.                                                                                                                                    |
| **Description**     | A detailed description of the user story being created.                                                                                                                       |
| **Type**            | Default type is **Story**. Available issue types: **Story**, **Task**, **Sub-task**, **Bug**, **Issue**, **Epic**, **Incident**. Any issue type can be created in ReleaseOwl. |
| **Assigned To**     | Select the user to whom the user story is to be assigned.                                                                                                                     |
| **Sprint**          | The sprint in which the user story will be handled.                                                                                                                           |
| **Release Version** | The version of the release in which the user story will get released.                                                                                                         |

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **2. User Story Tab**

This is the primary section for entering and managing story information.

**a. Core Fields**

| Field                | Description                                                                                |
| -------------------- | ------------------------------------------------------------------------------------------ |
| **Summary**          | A short title summarizing the purpose of the user story.                                   |
| **Description**      | Provides detailed context or requirements for the story (optional).                        |
| **Type**             | Identifies the work item type.                                                             |
| **Assigned To**      | The user responsible for implementing this story.                                          |
| **Status**           | Current state of the story (_Open_, _In Progress_, _Done_).                                |
| **Sprint**           | Sprint in which the story is scheduled for completion.                                     |
| **Release Pipeline** | The release pipeline associated with the story, used for deployment tracking.              |
| **Release Version**  | Specifies the release version or build where this story is included.                       |
| **Component**        | Refers to the business or technical component impacted (e.g., _TC_ for Testing Component). |

<figure><img src="../../.gitbook/assets/image (1613).png" alt=""><figcaption></figcaption></figure>

**b. Actions**

| Action                | Description                                                                                                                                               |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Validate**          | Performs validation to ensure all required details are complete.                                                                                          |
| **Validation Report** | Displays a summary of validation results.                                                                                                                 |
| **Promote**           | Promotes the story to the next stage in the release workflow.                                                                                             |
| **Save**              | Saves all modifications made to the story details.                                                                                                        |
| **Activity Log**      | Displays a chronological list of all actions performed on the story, including status changes, updates, and user actions, allowing for full traceability. |

<figure><img src="../../.gitbook/assets/image (1614).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1619).png" alt=""><figcaption></figcaption></figure>

#### **3.  Artifacts Tab**

This tab dynamically updates based on the projects added in the Artifacts section. Only the relevant artifacts associated with those projects will be displayed.

#### **4. Attachments Tab**

Use this tab to upload and manage supporting files and links related to your user story. You can browse for a file, attach it, or add a reference link as needed.

**Details**

* Maximum file size allowed: **10 MB**.

<figure><img src="../../.gitbook/assets/image (1615).png" alt=""><figcaption></figcaption></figure>

#### Validation Report

* The Validation Report will look as follows:

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* On clicking the **Pipeline Activity**, you can view the release pipeline execution status as follows:

<figure><img src="../../.gitbook/assets/image (1123).png" alt=""><figcaption></figcaption></figure>

**Options in Pipeline Activity Screen (Right Panel)**\
The right side of the **Pipeline Activity** screen contains the following options:

* **Abort:**\
  This button allows users to stop a currently running pipeline activity. When clicked, a confirmation popup appears where the user must provide a reason to proceed. Once confirmed, the pipeline status changes to **Aborted** for the respective task.
* When aborting an action, users can also update the status of the associated User Story.

{% hint style="info" %}
**Note:** The **Abort** action **will not** interrupt a deployment that is already in progress. Use this action only when the pipeline is in a **Waiting for Approval** or **Suspended** state.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (1618).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1124).png" alt=""><figcaption></figcaption></figure>

* The **Pipeline Stage** and **Pipeline Status** of the related user story are also updated to **Aborted**.

<figure><img src="../../.gitbook/assets/image (1125).png" alt=""><figcaption></figcaption></figure>

* **History**:&#x20;

This option displays the execution history of the release pipeline, including details such as the number of times the pipeline was executed, who triggered each execution, and the status of each run.&#x20;

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1126).png" alt=""><figcaption></figcaption></figure>

* When you click on the arrow button (**>**), you are taken to the **Pipeline Activity** screen.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1127).png" alt=""><figcaption></figcaption></figure>

**Refresh**:&#x20;

This button allows you to update the Pipeline Activity screen with the latest information. When you click on the Refresh button, it reloads the current status of the release pipeline to reflect any recent changes or updates.

<figure><img src="../../.gitbook/assets/image (1128).png" alt=""><figcaption></figcaption></figure>

### Release Audit Report&#x20;

You have the option to export the details as a **Release Audit Report**. The exported document provides comprehensive information to help track and communicate the progress of the user story.

<figure><img src="../../.gitbook/assets/image (15) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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



    <figure><img src="../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

