# GCTS Merge Task

This Task is used when a hotfix changes need to be merged to other development branches. After a major release of a project, the changes from the master branch can be merged to other development branches.

Fill in the required details:

| **Field**                  | **Details**                                                                                                                                                |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                   | Enter a unique name for the GCTS Merge task of your choice.                                                                                                |
| **GCTS Environment**       | Select the source and target GCTS environments from the dropdown menu. This defines the environments for the merge.                                        |
| **Domain Controller**      | Automatically populated based on the selected GCTS environment. Indicates the transport controller managing the process.                                   |
| **System ID (SID)**        | Auto-filled field that uniquely identifies the systems involved (e.g., S4D.100). Ensures proper linkage between environments.                              |
| **GCTS Repository (Repo)** | Select the repository from the dropdown menu in the source environment. The corresponding repository in the target environment is automatically displayed. |
| **Branch**                 | Select the source branch (e.g., dev) and target branch (e.g., qa) manually from dropdowns to ensure proper branch mapping.                                 |
| **Notify Users**           | Sends notifications to relevant stakeholders upon merge completion. Ensures transparency and team awareness.                                               |
| **Forward Merge**          | Automatically propagates merged changes according to system landscape hierarchy (e.g., dev → QA → preprod → prod).                                         |
| **Description**            | Any message that is to be conveyed  to the task performer can be mentioned here.                                                                           |

<figure><img src="../../../.gitbook/assets/image (43) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** If you are moving from dev to prod directly without going through quality, you don't need to check the forward merge.
{% endhint %}
