# Approval Task

### Approval Task

Pauses the release pipeline until a designated approver signs off. If a deployment requires prior approval, add an Approval Task **before** the Deployment Task when creating the Release Pipeline. The pipeline does not proceed to the next task until the approval is completed.

| Field                               | Type                 | Description                                                                                                                                                                                    |
| ----------------------------------- | -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                            | Text                 | Task name. Only letters, numbers, underscores (`_`), and periods (`.`) are permitted.                                                                                                          |
| **Description**                     | Text                 | Message conveyed to the task performer.                                                                                                                                                        |
| **Assign To**                       | User / Role / Custom | Who can approve the task — see _Assignment types_ below.                                                                                                                                       |
| **Message**                         | Rich text            | Instruction shown to the task approver.                                                                                                                                                        |
| **Disable Email Notification**      | Checkbox             | Approvers do not receive the approval email link; they are notified only of the final status (approved/rejected).                                                                              |
| **Approval Message Required**       | Checkbox             | Approvers must enter a comment when performing the Approve or Reject action from My Tasks. The action cannot be completed without a comment.                                                   |
| **Promoter cannot be the approver** | Checkbox             | Prevents the person who promoted the change from approving their own promotion. Even if the promoter is the assigned user or holds the assigned role, they cannot complete this approval task. |

#### Assignment types

* **User** — a specific user selected from the available list is responsible for approving the task.
* **Role** — any user holding the selected role can approve. Use this when approval belongs to a function (e.g., Release Manager) rather than an individual.
* **Promoter** — the task is assigned to the user who promoted the change. The promoter themselves receives the approval task in My Tasks and confirms the action to let the pipeline continue. Use this as a self-confirmation checkpoint (e.g., "verify and continue") rather than an independent approval.
* **Custom** — approval is granted per **component**: any user associated with the custom-defined roles assigned to each component can approve. This allows different roles to approve different components within the same task. The following options are available only for the **Custom** assignment type:

| Option                         | Purpose                                                                                                                                                                                                                        |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Add Component and Role (+)** | <p>Opens a popup: select the Component, add one or more Roles (comma-separated) for it, and click <strong>Add</strong> to save the component–role mapping.<br><img src="../../../.gitbook/assets/image (2177).png" alt=""></p> |
| **Export Roles**               | Downloads the current role assignments (the list of components and their associated roles) as a file.                                                                                                                          |
| **Import Roles**               | Uploads a previously exported roles file — useful for reusing the same mapping in another release pipeline.                                                                                                                    |

<figure><img src="../../../.gitbook/assets/image (2176).png" alt=""><figcaption></figcaption></figure>

#### How it works

When the pipeline reaches the Approval Task, it is delivered to the assignee(s) and appears under **My Tasks** when they log in to ReleaseOwl. The approver reviews the task and either **Approves** or **Rejects** it. On approval, the pipeline continues to the next task (typically the Deployment Task); on rejection, the pipeline does not proceed.

#### Behavior notes

* With **Disable Email Notification** enabled, approvers must discover the task through My Tasks — plan for this if your approvers rely on email.
* With **Approval Message Required** enabled, every Approve/Reject action carries a mandatory comment, giving you an audit trail of why each decision was made.
* For Custom assignment, maintain the component–role mapping once, **Export Roles**, and **Import Roles** into other pipelines to keep approval governance consistent across pipelines.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
