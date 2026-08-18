# Merge Task

Merges changes from a source branch into a target branch. The source and target branches are resolved at runtime from the task configuration.

| Field                          | Type                | Description                                                                                                                                                 |
| ------------------------------ | ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name / Description**         | Text                | Task identity.                                                                                                                                              |
| **Merge Source**               | Dropdown            | **Branch/Commits from User Story**, **Branch from environment**, or **Staging branch**.                                                                     |
| **Target Environment**         | Dropdown            | The environment whose branch receives the merge.                                                                                                            |
| **Notify Users**               | Checkbox            | Sends notifications on completion.                                                                                                                          |
| **Create Staging Branch for**  | Dropdown (Advanced) | **None**, **Release Package**, or **Both** — determines whether a staging branch is created from the target environment branch instead of merging directly. |
| **Execute this task only for** | Dropdown (Advanced) | **User Story**, **Release Package**, or **Both** — scopes the task to the relevant promotion mode.                                                          |

By default the source changes are merged directly into the target environment branch. When staging is enabled, changes are merged into a staging branch cut from the target environment branch instead; a later Merge task then promotes the staging branch into the target environment branch. Creating a staging branch is optional — configure the Merge and Build tasks to match your requirement.

<figure><img src="../../../.gitbook/assets/image (2187).png" alt=""><figcaption></figcaption></figure>
