# GCTS Activate Task

### GCTS Activate Task

This Task is used when a system needs to be updated to latest commit of the associated branch.

Fill in the required details:

| **Field**            | **Description**                                                                                              |
| -------------------- | ------------------------------------------------------------------------------------------------------------ |
| **Task Name**        | Auto-populated with the name from the GCTS Merge task.                                                       |
| **GCTS Environment** | Select the target environment (e.g., development, quality, or production) where the activation should occur. |
| **GCTS Repository**  | Choose the appropriate Git repository that contains the changes to be activated.                             |
| **Description**      | Any message that is to be conveyed  to the task performer can be mentioned here.                             |

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>





<figure><img src="../../../.gitbook/assets/image (1337).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :** During activation status validation, the system reads the **gCTS logs** to identify the **STMS transport request** associated with the activation. If the logs do **not** contain a reference to a gCTS transport request, it is **not possible to conclusively determine** whether the commit changes were imported via STMS.
{% endhint %}
