# Pull Request Task

#### Pull Request Task <a href="#pull-request-task" id="pull-request-task"></a>

Creates a pull request from a source branch to a target branch and delivers a review task to the assigned reviewer.

**Prerequisite — GitLab Token**

The **Pull Request** and **Merge** tasks authenticate to GitLab using the token stored in the project's **Version Control** credential.

Before configuring these tasks, generate a GitLab access token with the required permissions.

1. Log in to GitLab using the service account that ReleaseOwl will use.
2. Go to **Preferences → Access Tokens**. Alternatively, go to **Group/Project → Settings → Access Tokens**.
3. Click **Add new token**.
4. Enter a **Name** and **Expiration date** for the token.
5. In the **Resource and permission selector**, select the **Group and project** tab and enable the following granular permissions:

| Resource                                     | Permissions that MUST be enabled         | If NOT enabled                                                                                                                                                                                     |
| -------------------------------------------- | ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Repository → **Code**                        | **Read**                                 | ReleaseOwl cannot read the source and target branches. PR creation fails immediately.                                                                                                              |
| Repository → **Commit**                      | **Create, Read, Update**                 | Story commits cannot be read and merge commits cannot be written. The Merge task fails even when the PR is approved.                                                                               |
| Repository → **Merge Request**               | **Approve, Create, Merge, Read, Update** | The core of the feature. Without **Create**, the Pull Request task cannot open the PR; without **Read**, it cannot track review status; without **Merge**, the downstream Merge task cannot merge. |
| Repository → **Merge Request Approval Rule** | **Create, Read, Update**                 | Approval state of the PR cannot be evaluated. The Merge task cannot verify the PR is approved before merging.                                                                                      |
| Repository → **Branch**                      | **Create, Read**                         | Feature branches cannot be created (Feature Branch model), and environment branches cannot be resolved as PR source/target.                                                                        |
| Search → **Global Search**                   | **Use**                                  | Repository and merge request lookup via the search API fails.                                                                                                                                      |

{% hint style="info" %}
**Note :** All the above permissions are mandatory. If any permission is missing, the pipeline may fail at runtime. For example, the Pull Request may not be created, the approval status may not be read, or the Merge task may not be able to merge the pull request.
{% endhint %}

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FgDqx22dW4u5DZ8vysOjw%252Fimage.png%3Falt%3Dmedia%26token%3D424f41a3-a4a2-455c-ad49-4514da6577a0&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=aa2bff70&#x26;sv=2" alt="" height="875" width="1685">

#### Configure the Pull Request Task

Configure the following fields when adding the **Pull Request Task** to the release pipeline:

| Field                               | Type        | Description                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                            | Text        | Task name.                                                                                                                                                                                                                                                                                                                             |
| **Description**                     | Text        | Task description.                                                                                                                                                                                                                                                                                                                      |
| **Change Source**                   | Dropdown    | **Branch from User Story** (typical for Feature Branch model — PR from the story’s feature branch to the target environment branch) or **Branch from environment** (PR from a Source Environment branch to the target environment branch; used for Release Package promotions). A **Source Environment** field appears for the latter. |
| **Target Environment**              | Dropdown    | The environment whose branch is the PR target.                                                                                                                                                                                                                                                                                         |
| **Assign To**                       | Role / User | Who receives the review task (a Role or a specific User) — same as the Approval task.                                                                                                                                                                                                                                                  |
| **Promoter cannot be the approver** | Checkbox    | Prevents the person promoting from approving their own change.                                                                                                                                                                                                                                                                         |
| **Disable email notification**      | Checkbox    | Suppresses the notification email.                                                                                                                                                                                                                                                                                                     |
| **Approval message required**       | Checkbox    | Requires a message on completion.                                                                                                                                                                                                                                                                                                      |
| **Message**                         | Rich text   | Instruction shown to the reviewer.                                                                                                                                                                                                                                                                                                     |

**How it works (Feature Branch model)**: The reviewer receives a task in My Tasks, opens the pull request directly in the Git repository, and approves it there — they do not merge it in Git. The actual merge is performed by the downstream Merge task in the pipeline. The reviewer then returns to ReleaseOwl and completes the Pull Request task, and the pipeline continues. Completion can also be automated with a Git webhook.

**Behavior**

If a reviewer merges the pull request directly in Git instead of only approving, the downstream **Merge** task still runs but finds no changes to merge — it completes without error.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F8C5h6h660qPdkZ1DJ4mS%252Fimage.png%3Falt%3Dmedia%26token%3Dc1946eb1-ef54-4248-bad5-60a8c7ad20bf&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=4c8e4da&#x26;sv=2" alt="" height="871" width="1918">

