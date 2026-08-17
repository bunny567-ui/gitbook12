# Manual Task

Adds a manual checkpoint to the release pipeline for activities performed outside ReleaseOwl — configuration updates, manual testing, or other required changes, typically after a deployment. The pipeline pauses at this task and continues only when the assignee marks it **Complete**. Once a manual task is added, the following screen will be displayed.

<figure><img src="../../../.gitbook/assets/image (2185).png" alt=""><figcaption></figcaption></figure>

**Fill in the required details:**

| Field                               | Type                                             | Description                                                                                                                                                                                                        |
| ----------------------------------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Name**                            | Text                                             | Task name. Only letters, numbers, underscores (`_`), and periods (`.`) are permitted.                                                                                                                              |
| **Description**                     | Text                                             | Message conveyed to the task performer — describe exactly what must be done before completing the task.                                                                                                            |
| **Assign To**                       | User / Role / Custom / Story Assignee / Promoter | Who performs the task — see _Assignment types_ below.                                                                                                                                                              |
| **Disable Email Notification**      | Checkbox                                         | The assignee does not receive the task email link; only a notification about the final status is sent.                                                                                                             |
| **Complete Message Required**       | Checkbox                                         | The performer must enter a completion message before marking the task as **Complete** from My Tasks. The task cannot be completed without it.                                                                      |
| **Promoter cannot be the approver** | Checkbox                                         | Prevents the user who promoted the change from completing this task, even if they are covered by the Assign To selection (e.g., they hold the assigned role). Enforces that a second person confirms the activity. |

#### Assignment types

* **User** — a specific user selected from the available list performs the task.
* **Role** — any user holding the selected role can perform the task.
* **Custom** — dynamic assignment using custom-defined conditions.
* **Story Assignee** — the task goes to the person assigned to the related user story.
* **Promoter** — the task goes to the user who promoted the change in the release pipeline.

#### How it works

When the pipeline reaches the Manual Task, it appears under the assignee's **My Tasks** section upon logging in to ReleaseOwl. The performer carries out the described activity, then clicks **Complete** — entering a completion message if _Complete message required_ is enabled. The pipeline then continues to the next task.

#### Behavior notes

* A Manual Task records **that** an activity was done — enable _Complete message required_ if you need an audit trail of what was actually performed.
* With _Disable email notification_ enabled, performers must find the task via My Tasks.
* Unlike an Approval Task, a Manual Task has a single outcome (**Complete**) — there is no reject path.
