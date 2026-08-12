# Working with User stories

A user story carries the change(s) to be delivered. How changes are attached depends on the branching model of each application involved.

### Add MTAR Applications

To associate MTAR applications with a User Story:

1. Navigate to **Change Management** and click **User Stories**.
2. Click **Create New User Story**.

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

2. Enter the required details and click **Create**.

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Click **Actions**, and then click **Edit**.
4. In the **MTAR Applications** section, click **Add**.

<figure><img src="../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Step 1: MTAR Applications**

The **MTAR Applications** step displays all registered MTAR applications.

1. Select the required MTAR application.
2. Review the application details, including:
   * **Application Name**
   * **Description**
   * **Repository URL**
   * **Branching Model**
3. Click **Next**.

<figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

**Step 2: Source Reference**

When adding the application to a user story, the **Source Reference** step lets you either create a new feature branch or reference an existing one.

| Field             | Type     | Description                                                                                                                                                    |
| ----------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Select**        | Radio    | “Create \<Feature/Hotfix> Branch” to have ReleaseOwl create the branch in Git, or “I Already Have a \<Feature/Hotfix> Branch” to reference an existing branch. |
| **Branch name**   | Text     | The feature/hotfix branch name (e.g. hotfix/DP-488).                                                                                                           |
| **From Branch**   | Dropdown | The base branch the new branch is cut from. Defaults to the application’s “Create Feature Branch From Branch” value; can be overridden.                        |
| **Create Branch** | Button   | Creates the branch in the Git repository.                                                                                                                      |

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

* If **I Already Have a Feature Branch** is selected, Enter  the existing feature branch and click **Finish**.

<figure><img src="../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

**Cherry Pick Model**

In the Cherry-Pick model no feature branch is created. Instead, you select the commits related to the user story. The available commits are populated from the application’s development branch — the landscape branch flagged as “**Development Branch**” . The selected commits are cherry-picked onto the target environment branches during promotion.

<figure><img src="../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

#### Edit Feature Branch / Commits

You can edit the **Feature Branch** or the selected **commits** after an MTAR application has been added to the User Story.

To edit the source reference:

1. In the **MTAR Applications** section, click the **Actions** button corresponding to the required MTAR application.
2. Click **Edit Feature Branch**.

<figure><img src="../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

3. Update the **Feature Branch** (for the **Feature Branch Model**) or modify the selected **commits** (for the **Cherry Pick Model**).
4. Click **Save** /**Add** to apply the changes.

<div><figure><img src="../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure></div>

### User Story Actions

The following actions are available on the User Story toolbar:

* **Validate** – Validates the User Story against the configured target environment and generates a **Validation Report**.  Depending on the Release Pipeline and associated Build Pipeline configuration, the validation may include artifact validation, dependency and impact analysis, static code analysis, SonarQube analysis, ESLint validation, OPA5 test execution, and build verification.
* **Promote** – Promotes the User Story to the next stage in the release pipeline.
* **Save** – Saves the changes made to the User Story. Ensure that you click **Save** before clicking **Promote**.
* **Refresh** – Refreshes the User Story and reloads the latest information.

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

* **Activity Log**- Click **Activity Log** to view the complete history of actions performed on the User Story.

<figure><img src="../../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

* **Release Package Details**: Click **Release Package Details** to view the release package information associated with the User Story.&#x20;
* **Export User Story** : Click **Export User Story** to export the User Story details.&#x20;

<figure><img src="../../.gitbook/assets/image (2127).png" alt=""><figcaption></figcaption></figure>

### User Story promotion

•    Initiated manually from the user story.

•    Source is the story’s feature branch (Feature Branch model) or selected commits (Cherry-Pick model).

•    Each user story is processed individually. In the Feature Branch model the feature branch is merged into each environment branch as the story advances (Development → QA → Production), with the source constant and only the Target Environment changing per stage.

<figure><img src="../../.gitbook/assets/image (2168).png" alt=""><figcaption></figcaption></figure>
