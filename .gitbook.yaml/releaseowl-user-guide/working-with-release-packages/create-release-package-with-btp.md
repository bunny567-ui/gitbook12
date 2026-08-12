# Create Release Package with BTP

### Release Package promotion

A Release Package is a frozen bundle of user stories promoted together as one unit.

•    Initiated from the Release Packages menu, through the same release pipeline.

•    With Merge/Build Source = “Branch from environment”, the whole environment branch is promoted forward (environment-to-environment).

•    With Source = “Branch/Commits from User Story”, each user story in the package is merged individually.

**A typical scoping pattern**: The Pull Request and per-feature-branch Merge tasks are scoped to User Story, while a branch-level Merge (Branch from environment) plus staging is scoped to Release Package.

### Staging branches

For Release Package promotions where changes should not be merged directly into the target environment branch, enable staging on the Merge/Build tasks:

1\.   A staging branch is created from the target environment branch.

2\.   The source changes (branch-from-environment, feature branches, or commits) are merged into the staging branch.

3\.   The Build task builds from the staging branch, using the dynamic build pipeline (staging is a dynamic branch).

4\.   The Deployment task deploys the resulting artifact.

5\.   A subsequent Merge task promotes the staging branch into the target environment branch.

{% hint style="info" %}
**Note :** Staging is optional. Whether it is created for Release Package only or for Both User Story and Release Package is controlled by “Create Staging Branch for” on the Merge/Build task.
{% endhint %}

#### To create a release package

1. Go to **Release** and click **Release Packages.**
2. Click **Create New Release Package.**

<figure><img src="../../.gitbook/assets/image (2171).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** You can create a Release Package with User Stories for an SAP Integration Suite project.
{% endhint %}

3. Fill in the necessary details:&#x20;

| **Field / Element**           | **Description**                                                                                                                                             |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                      | Enter the name of the new Release Package. This is a mandatory field.                                                                                       |
| **Description**               | Provide an optional description for the package to clarify its purpose or content.                                                                          |
| **Release Pipeline**          | Select the Release Pipeline that should be triggered for deployment upon promotion of the Release Package.                                                  |
| **Promote from (Stage)**      | Default is `Dev`. Displays the list of stages defined in the selected Release Pipeline (excluding the final stage like `Prod`).                             |
| **Add Stories for Promotion** | Automatically adds all eligible user stories that are **not already part of another release package** and are ready to be promoted from the selected stage. |
| **Add User Story**            | Allows manual selection of user stories  from the selected Promote from (Stage). You can select multiple entries in one go.                                 |

4. Click **Save.**

<figure><img src="../../.gitbook/assets/image (2173).png" alt=""><figcaption></figcaption></figure>

5. When you click the **Show** button, a preview of the user story details are displayed.

<figure><img src="../../.gitbook/assets/image (2174).png" alt=""><figcaption></figcaption></figure>

