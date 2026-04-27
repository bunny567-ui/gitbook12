# Branch Merge Task

The **Branch Merge Task** enables controlled merging of code changes between branches within a pipeline, leveraging supported source control systems such as Git. This task allows users to configure the target repository, source branch, and destination branch, and execute merge operations as part of an automated workflow. The merge process is initiated within the pipeline, ensuring consistency and traceability across environments.

If merge conflicts occur, they are identified and surfaced at the **User Story** level. This provides clear visibility into conflicting changes and enables users to review, resolve, and validate conflicts within the context of the associated work item before proceeding with further pipeline execution.

A **Branch Merge Task** can be added as follows:

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

#### **Branch Merge Task Configuration**

| **Field**                    | **Description**                                                                                             |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Name**                     | Enter a valid name using letters, numbers, underscores (\_) or periods (.).                                 |
| **Description**              | Provide a brief description of the task. This field is used to describe the purpose of the merge operation. |
| **Enter Repository URL**     | Specify the Git repository URL where the branch merge operation will be executed.                           |
| **Version Control Platform** | Select the source control system (e.g., GitHub, GitLab, Bitbucket) associated with the repository.          |
| **SCM Credentials**          | Select the Credentials from the drop down method that was registered                                        |
| **Source Branch**            | Enter the name of the branch from which changes need to be merged.                                          |
| **Target Branch**            | Enter the name of the branch into which changes will be merged.                                             |

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

#### **Completing the Branch Merge Task**

1. After adding the **Branch Merge Task** to the Release Pipeline, save the configuration and promote the task through any supported mode, such as **User Story.**
2. In the Pipeline Activity, you can view the details of the Git branches (source and target) that were selected and applied during the Branch Merge Task.
3.  **Merge Status**

    Check the status of each file:

    * If the status is **Resolved**, the merge has been successfully completed for that file.
    * If conflicts exist, they must be resolved before proceeding.

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>
