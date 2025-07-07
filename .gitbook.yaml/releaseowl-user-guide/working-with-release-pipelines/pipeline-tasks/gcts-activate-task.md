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

<figure><img src="../../../.gitbook/assets/image (42) (1).png" alt=""><figcaption></figcaption></figure>

**gCTS Activation Status Validation**&#x20;

In the gCTS Activation Acitivity, the gCTS STMS Transport Request ID is  used for every successful activation to check import into the target system, ensuring consistent and traceable deployment.

During the Activation Status validation, ReleaseOwl attempts to read the gCTS logs to identify the gCTS STMS transport request associated with the activation. If the logs do not contain a reference to a gCTS transport, ReleaseOwl cannot conclusively determine whether the commit changes were successfully imported using the STMS transport.

{% hint style="info" %}
**Note** : ReleaseOwl  uses a combination of the gCTS STMS transport and activation status to determine whether commit changes have been successfully imported. This ensures that a commit is only considered successfully delivered when both indicators validate the import, significantly improving the accuracy and reliability of deployment tracking.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (1337).png" alt=""><figcaption></figcaption></figure>

**Enhanced Activation Logic for gCTS Transport**

ReleaseOwl now includes an improved activation validation logic for gCTS transport:

* During commit activation, the system compares the timestamp of the commit being activated with the current active commit. If the current active commit date and time are **newer or equal**, the activation is skipped to prevent accidental downgrades.
* Additionally, the system checks whether the commit to be activated exists in the latest 150 local commits in the gCTS system. If the commit is already present in the local history and not yet activated, its timestamp is validated to ensure it's not older than the active commit.

This logic ensures that only appropriate commits are activated, maintaining the integrity and sequence of the transported changes.

**gCTS Activation Timeout Handling**

When a timeout occurs during the commit activation process, ReleaseOwl may be unable to confirm whether the commit was successfully activated in the gCTS application. In such scenarios, the pipeline is automatically suspended to avoid proceeding without confirmation.

To address this, a **Refresh** option has been introduced within the Deploy Log interface. Users can manually trigger this refresh to fetch the latest activation status from gCTS. Once the updated status is retrieved and verified, users can resume and continue the pipeline execution seamlessly.

This enhancement improves process reliability by allowing users to make informed decisions and recover from temporary network or system delays during activation.

{% hint style="info" %}
Note: This enhancement ensures better control and reliability in scenarios where activation is delayed or uncertain, allowing users to safely proceed after validating the actual commit status
{% endhint %}
