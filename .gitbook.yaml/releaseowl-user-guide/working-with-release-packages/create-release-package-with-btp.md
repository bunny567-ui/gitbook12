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

&#x20;
