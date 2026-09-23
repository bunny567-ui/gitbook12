# Working with User Stories

A user story represents the changes to be delivered. The way changes are associated with a user story depends on the branching model used by the RAP application. User stories allow you to group and manage related changes that are deployed together through a [Release Pipeline.](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/working-with-release-pipelines/use-cases/automated-rap-applications)

#### Add RAP Applications <a href="#add-mtar-applications" id="add-mtar-applications"></a>

To associate RAP applications with a User Story:

1. Navigate to **Change Management** and click **User Stories**.
2. Click **Create New User Story**.

<figure><img src="../../.gitbook/assets/image (2277).png" alt=""><figcaption></figcaption></figure>

3. Enter the required details and click **Create**.

<figure><img src="../../.gitbook/assets/image (2278).png" alt=""><figcaption></figcaption></figure>

4. Click **Actions**, and then click **Edit**.

<figure><img src="../../.gitbook/assets/image (2279).png" alt=""><figcaption></figcaption></figure>

#### Setting the Change Type

1. In the User Story section, the **Change Type** field displays two options:

* **Normal**
* **Hotfix**

2. Select the required change type.
3.  **Normal:** . The user selects the required commits related to the change; those commits are cherry-picked onto the target environment's branch during promotion.

    **Hotfix:** The user story is used for urgent fixes. ReleaseOwl always creates and assigns a dedicated hotfix    &#x20;branch to the user story. Promotion is carried out using the application's Hotfix configuration, so    &#x20;the fix can be delivered to production without waiting for the regular release.&#x20;

<figure><img src="../../.gitbook/assets/image (2280).png" alt=""><figcaption></figcaption></figure>

#### **Attaching a RAP Application**

Go to the user story's RAP Applications tab and use + Add to attach one or more RAP applications to the&#x20;story (and Remove to detach). A single user story can contain multiple applications. The Source Reference&#x20;step that follows differs by the story's Change Type.&#x20;

<div><figure><img src="../../.gitbook/assets/image (2281).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (2282).png" alt=""><figcaption></figcaption></figure></div>

**Normal story — selecting commits**. The available commits are populated from the\
application's development branch — the landscape row flagged “Development Branch”. Select the&#x20;commits required for this change; they are cherry-picked onto the target environment's branch during&#x20;promotion.

<figure><img src="../../.gitbook/assets/image (2317).png" alt=""><figcaption></figcaption></figure>

#### Hotfix Story — Hotfix Branch

For a **Hotfix Story**, ReleaseOwl always creates and assigns the hotfix branch. There is no commit-selection step for a Hotfix Story.

| **Field**          | **Type** | **Description**                                                                                                                                                                      |
| ------------------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Select**         | Radio    | Select **Create Hotfix Branch** to have ReleaseOwl create the branch in Git, or **I Already Have a Hotfix Branch** to reference an existing branch.                                  |
| **Hotfix Branch**  | Text     | The hotfix branch name.                                                                                                                                                              |
| **From Branch**    | Dropdown | The dropdown lists the application's environment branches . For a production fix, select the branch running in production so the hotfix contains exactly what is live plus your fix. |

* Click **Finish** to create the hotfix branch and complete the assignment.

<figure><img src="../../.gitbook/assets/image (2285).png" alt=""><figcaption></figcaption></figure>

* If **I Already Have a Hotfix Branch** is selected, enter the existing hotfix branch name and click **Finish.**

<figure><img src="../../.gitbook/assets/image (2286).png" alt=""><figcaption></figcaption></figure>

**Edit Commits**

You can edit the  selected **commits** after a RAP application has been added to the User Story.

To edit the source reference:

1. In the **RAP** **Applications** section, click the **Actions** button corresponding to the required RAP application.
2. Click **Edit Commits**.

<figure><img src="../../.gitbook/assets/image (2318).png" alt=""><figcaption></figcaption></figure>

3. Modify the selected **commits**.
4. Click **Add** to apply the changes.

#### User Story Actions <a href="#user-story-actions" id="user-story-actions"></a>

The following actions are available on the User Story toolbar:

* **Validate** – Validates the User Story against the configured target environment and generates a **Validation Report**.
* **Promote** – Promotes the User Story to the next stage in the release pipeline.
* **Save** – Saves the changes made to the User Story. Ensure that you click **Save** before clicking **Promote**.
* **Refresh** – Refreshes the User Story and reloads the latest information.

<figure><img src="../../.gitbook/assets/image (2291).png" alt=""><figcaption></figcaption></figure>

* **Activity Log**- Click **Activity Log** to view the complete history of actions performed on the User Story.

<figure><img src="../../.gitbook/assets/image (2292).png" alt=""><figcaption></figcaption></figure>

* **Release Package Details**: Click **Release Package Details** to view the release package information associated with the User Story.
* **Export User Story** : Click **Export User Story** to export the User Story details.

<figure><img src="../../.gitbook/assets/image (2293).png" alt=""><figcaption></figcaption></figure>

#### User Story promotion <a href="#user-story-promotion" id="user-story-promotion"></a>

• Initiated manually from the user story.

• Each user story is processed individually. As the story progresses through the deployment lifecycle (Development → QA → Production), the commits are merged into the corresponding environment branch at each stage. The source branch remains constant, while only the **Target Environment** changes according to the current stage.

<figure><img src="../../.gitbook/assets/image (2294).png" alt=""><figcaption></figcaption></figure>

#### Deployment - RAP

1. Click **Promote** to start the deployment process.

<figure><img src="../../.gitbook/assets/image (2310).png" alt=""><figcaption></figcaption></figure>

2. If the Release Pipeline includes a **Deployment** task, monitor the deployment status of the User Story.
3. Click **Deploy Logs** to view the deployment details.

<div><figure><img src="../../.gitbook/assets/image (2311).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (2312).png" alt=""><figcaption></figcaption></figure></div>

#### ABAP Checkout -RAP&#x20;

If your [Release Pipeline](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/working-with-release-pipelines/use-cases/automated-rap-applications) includes an **ABAP Checkout** task, click **Checkout Log** to view the details of the checkout operation.

<figure><img src="../../.gitbook/assets/image (2313).png" alt=""><figcaption></figcaption></figure>

