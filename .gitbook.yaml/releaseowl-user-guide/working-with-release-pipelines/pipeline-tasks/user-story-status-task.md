# User Story Status Task

The status of a user story can be set to a specific value automatically once the deployment takes place in an environment. Adding this task after a Deployment Task keeps the story status (and, via ALM integration, the linked Jira/ALM issue) in sync with pipeline progress — no manual status updates needed.

On adding a User Story Status Update task, the following screen is displayed.

<figure><img src="../../../.gitbook/assets/image (20) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| Field                  | Type     | Description                                                                                                            |
| ---------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Name**               | Text     | Task name. Only letters, numbers, underscores (`_`), and periods (`.`) are permitted.                                  |
| **Description**        | Text     | Description of the status update step.                                                                                 |
| **User Story Status**  | Dropdown | The status value to set on the user story when this task executes (e.g., after deployment to the stage's environment). |

<figure><img src="../../../.gitbook/assets/image (19) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### How it works

When the pipeline reaches this task, ReleaseOwl updates the linked user story to the configured status. If the story originates from an integrated ALM tool (e.g., Jira), the status change is synchronized back through the ALM integration, keeping both systems aligned.

{% hint style="info" %}
**Note:**  The **User Story Status Update** task within a pipeline can now be **skipped** if needed. Previously, this task had to be completed before the pipeline could move to the next step, which could delay or halt the execution.
{% endhint %}
