# Working with User Stories

A user story carries the change(s) to be delivered. How changes are attached depends on the branching&#x20;model of the RAP application involved.

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

<figure><img src="../../.gitbook/assets/image (2283).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/image (2288).png" alt=""><figcaption></figcaption></figure>

3. Modify the selected **commits**.
4. Click **Add** to apply the changes.

