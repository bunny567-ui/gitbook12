# Build Task

Builds the application code using the Build Pipeline configured in ReleaseOwl, producing the MTAR artifact.

| Field                                                     | Type     | Description                                                                                                                                                                              |
| --------------------------------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name / Description**                                    | Text     | Task identity.                                                                                                                                                                           |
| **Build Source**                                          | Dropdown | **Branch from User Story**, **Branch from environment** (reveals a **Source Environment**), or **Staging branch**.                                                                       |
| **Select Environment(s)**                                 | Dropdown | The environment whose configured Build Pipeline is used to build.                                                                                                                        |
| **Use Different Settings for Build from Release Package** | Checkbox | Lets User Story builds and Release Package builds use different sources (for example, User Story builds from the environment branch and Release Package builds from the staging branch). |
| **Notify Users**                                          | Checkbox | Sends notifications on completion.                                                                                                                                                       |

The per-environment **Build Pipeline** configured in the landscape is used for fixed environment branches. For dynamic branches, such as hotfix and staging branches, the **Build** task uses the application's dynamic Build Pipeline.

<figure><img src="../../../.gitbook/assets/image (2188).png" alt=""><figcaption></figcaption></figure>
