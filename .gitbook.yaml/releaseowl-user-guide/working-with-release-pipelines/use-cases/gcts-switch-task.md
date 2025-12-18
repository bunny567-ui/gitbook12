# GCTS Switch Task

The **GCTS Switch Task** in **ReleaseOwl** is used to change the branch associated with a system. For example, if a UAT system is currently pointing to the “QA” branch and a hotfix needs to be tested, this task can be used to switch the system to the “Hotfix” branch.

### Prerequisites

* The required **transports must be added** in the User Story.

### GCTS Switch Task – Flow

1. **Create a Pipeline** and add the **GCTS\_SWITCH\_TASK**.
   * Configure the task with:
     * **GCTS Environment**
     * **GCTS Repo**
     * **Branch To Switch**

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



2. **Create a User Story**.

* Attach the pipeline (with the **GCTS\_SWITCH\_TASK**) to the user story.
* In parallel, add a **Transport** to the same user story.
* Save the user story.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Promote the **User Story.**

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



4. After promotion, the system begins monitoring the **switch\_status**.
   * If the switch\_status = **TIMEOUT**, the user story moves to **Suspend** state with a **Refresh** icon. You can click this icon to retry the switch.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Upon clicking **Refresh**, the switch\_status may update to **SUCCESS** or **SWITCHED\_WITH\_WARNINGS**.
  * In this case, the **Continue Deployment** option becomes available. Clicking it resumes the process and marks the overall status as **Completed**.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Scenarios for SWITCHED\_WITH\_WARNINGS

* **Case 1: Transport ID Not Found in Logs**
  * If the GCTS Switch log does not contain a Transport ID, the system sets the **switch\_status = SWITCHED\_WITH\_WARNINGS**.
* **Case 2: Transport ID Found but Validation Required**
  * If a Transport ID is found in the log, the system verifies whether the respective Transport ID is **activated**; if activated, the **switch\_status = SUCCESS**, otherwise it is set to **another status**.

### Additional Option – Manual Completion (Mark as Complete)

* At any point, the user may choose to bypass waiting for the switch to complete by using the **Mark as complete in the Manual completion** option.
* Steps:
  1. In **Manual Completion**, click **Mark as Complete**.

<figure><img src="../../../.gitbook/assets/image (1540).png" alt=""><figcaption></figcaption></figure>

2. Enter the **Manual Complete Reason**.
3. Click **Mark as Complete** to confirm.

<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Once confirmed, the **Manual Deploy Details** section will be available, displaying:
   * **Deployed By**
   * **Deployed On**
   * **Reason**

<figure><img src="../../../.gitbook/assets/image (13) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. After that, a message will appear confirming that the deployment has resumed successfully.&#x20;

<figure><img src="../../../.gitbook/assets/image (17) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. The option **Continue Deployment** will also appear to complete the task.

<figure><img src="../../../.gitbook/assets/image (15) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

7. Click **Continue Deployment** → the **GCTS Switch Task** will be completed successfully, and the process will move to the **next stage**.

<figure><img src="../../../.gitbook/assets/image (16) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
