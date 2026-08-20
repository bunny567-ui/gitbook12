# Pull Request Task

This task creates a pull request from a source branch to a target branch and delivers a review task to the assigned reviewer.

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

#### GitLab Webhook Setup

Follow the steps below to configure a webhook for the required GitLab repository.

1. Open the required GitLab repository.
2. Navigate to: **Settings → Webhooks**

<figure><img src="../../../.gitbook/assets/image (2207).png" alt=""><figcaption></figcaption></figure>

3. Click **Add new webhook**.

<figure><img src="../../../.gitbook/assets/image (2208).png" alt=""><figcaption></figcaption></figure>

4. Enter the following details:

* **Name** _(optional)_ – Enter a name for the webhook.
* **Description** _(optional)_ – Enter a description for the webhook.
* **URL** – Enter the webhook URL provided by the application.

{% hint style="info" %}
**URL:** https:///ratesaptms/webhook/tenant/{tenantName}/project/{projectID}/pullRequest?rotoken={secretKey}
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (2212).png" alt=""><figcaption></figcaption></figure>

5. Under **Triggers**, enable: **Merge request events**

<figure><img src="../../../.gitbook/assets/image (2211).png" alt=""><figcaption></figcaption></figure>

6. Make sure **Enable SSL verification** is enabled.
7. Click **Save changes** to create the webhook.

<figure><img src="../../../.gitbook/assets/image (2213).png" alt=""><figcaption></figcaption></figure>

8. After creating the webhook, go to the **Test** section of the webhook configuration.
9. From the **Test** dropdown, select: **Merge request events**
10. Click **Test** to send a test webhook request.

<figure><img src="../../../.gitbook/assets/image (2215).png" alt=""><figcaption></figcaption></figure>

11. Verify that the test request is successfully received by the application and that the webhook connection is established successfully.

#### Bitbucket Webhook Setup

Follow the steps below to configure a webhook for the required Bitbucket repository.

1. Open Bitbucket and locate the required repository, for example, under **Repositories** in the left sidebar.
2. Click the **⋯ (More options)** menu next to the repository name and select **Settings**.

<figure><img src="../../../.gitbook/assets/image (2224).png" alt=""><figcaption></figcaption></figure>

3. In the **Repository details** section, enter the repository name and select the required project.

<figure><img src="../../../.gitbook/assets/image (2225).png" alt=""><figcaption></figcaption></figure>

4. In the repository settings, navigate to **Workflow** and select **Webhooks**.

<figure><img src="../../../.gitbook/assets/image (2226).png" alt=""><figcaption></figcaption></figure>

5.

    Enter the following details:

    * **Title (Optional):** Enter a name for the webhook.
    *   **URL:** Enter the webhook URL provided by the application.

        `https://<host>/ratesaptms/webhook/tenant/{tenantName}/project/{projectID}/pullRequest?rotoken={secretKey}`
6. In the **Status** section, select the **Active** checkbox.
7. In the **Triggers** section, under **Pull Request**, select the **Approved** checkbox.
8. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (2228).png" alt=""><figcaption></figcaption></figure>

#### &#x20;Azure DevOps Webhook Setup

Follow the steps below to configure a webhook in Azure DevOps.

1. Go to **Project Settings** in the required Azure DevOps project.

<figure><img src="../../../.gitbook/assets/image (2216).png" alt=""><figcaption></figcaption></figure>

2. In **Project Settings**, select **Service Hooks**.

<figure><img src="../../../.gitbook/assets/image (2217).png" alt=""><figcaption></figcaption></figure>

3. Click the **+** button to create a new service hook.

<figure><img src="../../../.gitbook/assets/image (2218).png" alt=""><figcaption></figcaption></figure>

4. Select **Webhooks** and click **Next**.

<figure><img src="../../../.gitbook/assets/image (2219).png" alt=""><figcaption></figcaption></figure>

5. Select the required repository and the trigger for the event, which is **Pull Request Updated**. Click **Next**.

<figure><img src="../../../.gitbook/assets/image (2220).png" alt=""><figcaption></figcaption></figure>

6.  &#x20;In the **Settings** section, enter the following URL:

    `https://<host>/ratesaptms/webhook/tenant/{tenantName}/project/{projectID}/pullRequest?rotoken={secretKey}`&#x20;
7. Click **Next**.

<figure><img src="../../../.gitbook/assets/image (2221).png" alt=""><figcaption></figcaption></figure>

8. Fill in the required details and click **Test**.

<figure><img src="../../../.gitbook/assets/image (2222).png" alt=""><figcaption></figcaption></figure>

9. A **Success** message is displayed when the webhook configuration is tested successfully.

<figure><img src="../../../.gitbook/assets/image (2223).png" alt=""><figcaption></figcaption></figure>

#### Github Setup

Follow the steps below to configure a webhook for the required GitHub repository.

1. Open the required repository in GitHub.
2. Go to **Settings** and select **Webhooks** from the left navigation.
3. Click **Add webhook**.

<figure><img src="../../../.gitbook/assets/image (2229).png" alt=""><figcaption></figcaption></figure>

4. In the **Payload URL** field, enter the webhook URL provided by the application:

`https://<host>/ratesaptms/webhook/tenant/{tenantName}/project/{projectID}/pullRequest?rotoken={secretKey}`

5. Set **Content type** to **application/json**.

<figure><img src="../../../.gitbook/assets/image (2231).png" alt=""><figcaption></figcaption></figure>

6. Under **Which events would you like to trigger this webhook?**, select **Let me select individual events**.
7. Select **Pull request reviews** as the event to trigger the webhook.
8. Ensure that **Active** is selected to enable the webhook.
9. Click **Add webhook** to save the configuration.

<div><figure><img src="../../../.gitbook/assets/image (2232).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (2233).png" alt=""><figcaption></figcaption></figure></div>

#### &#x20;Configure the Required Scopes

Follow the steps below to create a GitHub Personal Access Token (classic) with the required scopes.

1. Sign in to GitHub and click your profile picture in the upper-right corner.
2. Select **Settings**.



<figure><img src="../../../.gitbook/assets/image (2234).png" alt=""><figcaption></figcaption></figure>

3. In the left navigation, scroll down and select **Developer settings**.

<figure><img src="../../../.gitbook/assets/image (2235).png" alt=""><figcaption></figcaption></figure>

4. Under **Developer settings**, select **Personal access tokens** and then select **Tokens (classic)**.

<figure><img src="../../../.gitbook/assets/image (2236).png" alt=""><figcaption></figcaption></figure>

5. On the **Tokens (classic)** page, click **Generate new token** and select **Generate new token (classic)**.

<figure><img src="../../../.gitbook/assets/image (2237).png" alt=""><figcaption></figcaption></figure>

6. Under **Select scopes**, select the scopes required by the application, as shown in the following image.

<div><figure><img src="../../../.gitbook/assets/image (2238).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (2239).png" alt=""><figcaption></figcaption></figure></div>

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

