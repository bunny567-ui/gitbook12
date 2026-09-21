# Automated RAP Applications

**Release Pipelines**

These tasks are added to a stage of a Release Pipeline (Release → Release Pipelines) to drive a RAP\
application through checkout, validation, and deployment. Pipeline-level concepts (stages, triggers, generictasks such as Approval or Wait For Promotion) are the same as for any other ReleaseOwl application type&#x20;and are not repeated here.

{% hint style="info" %}
**Note:** You can create a multi-stage pipeline for continuous deployment across various environments one after the other towards continuous delivery of application all through Dev - QA - Staging - Production.
{% endhint %}

### **Creating a Release Pipeline**

Creating a Release Pipeline is a three-step process.

| Step 1 | Enter a name in Release Pipeline Name                                                                                                    |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Step 2 | Click '**Add Stages**' to add the required stages. Add various types of pre-deployment, deployment, and post-deployment tasks as needed. |
| Step3  | Specify the email ids to receive notifications about release pipeline execution status.                                                  |

#### **For creating release pipeline:**

1. Select the required CPI Project.
2. Navigate to **Release** and click on the **Release Pipelines.**

<figure><img src="../../../.gitbook/assets/image (2296).png" alt=""><figcaption></figcaption></figure>

3. Click **Create New Release Pipeline** to create the pipeline.

<figure><img src="../../../.gitbook/assets/image (2297).png" alt=""><figcaption></figcaption></figure>

4. Enter a **Pipeline Name**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (28).png" alt=""><figcaption></figcaption></figure>

5. Click **Add Stage**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (14).png" alt=""><figcaption></figcaption></figure>

<br>

6. **Tasks:** Click Add to enter any tasks that are to be performed

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (10).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** To remove any stage, click Remove stage button.
{% endhint %}

7. Different tasks that can be added are as follows:

<figure><img src="../../../.gitbook/assets/image (2295).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** All the tasks except Deployment Task are similar for any project type. For CPI projects, Wait for Promotion and Validation tasks are the two extra tasks available other than the ones available for every project type.
{% endhint %}

#### **Post-Creation Options**

Once the Release Pipeline is created, you can use the **Actions** button for the following options:

* **Save As**:  Opens a popup where you can enter a new name and create a copy of the pipeline.

<figure><img src="../../../.gitbook/assets/image (2298).png" alt=""><figcaption></figcaption></figure>

**Versions**: Displays all versions for the selected Release Pipeline. This option helps users track generated versions of the **Release Pipeline**. Versions are displayed only after the **Release Pipeline** has been promoted for the corresponding user story.

To view a specific version:

1. Select the required version from the created Release Pipeline list.

<figure><img src="../../../.gitbook/assets/image (2299).png" alt=""><figcaption></figcaption></figure>

2. Click the **Actions (⋯)** button for that version.
3. Select **View**. This allows you to view the details of the selected version of the release pipeline.

<figure><img src="../../../.gitbook/assets/image (2300).png" alt=""><figcaption></figcaption></figure>

* **Delete:** Deletes an existing release pipeline from the system.

<figure><img src="../../../.gitbook/assets/image (2301).png" alt=""><figcaption></figcaption></figure>

* **Archive** : The **Archive** option is available, which archives the project instead of deleting it.

<figure><img src="../../../.gitbook/assets/image (2302).png" alt=""><figcaption></figcaption></figure>

**Export Release Pipeline:** It is the process of downloading the complete configuration of an existing release pipeline as a file (usually in **JSON format**) so it can be reused, shared, or backed up.

1. Navigate to the **Release Pipelines** section.
2. Select the existing pipeline you want to reuse.
3. Click **Export Release Pipeline**.
4. The pipeline configuration is downloaded as a **JSON file** to your local system.

<figure><img src="../../../.gitbook/assets/image (2303).png" alt=""><figcaption></figcaption></figure>

**Import Release Pipeline** : It is a process of creating a new release pipeline by uploading a previously exported pipeline configuration file (usually in **JSON format**).

1. Navigate to the **Release Pipelines** section.
2. Click **New Release Pipeline**.

<figure><img src="../../../.gitbook/assets/image (2304).png" alt=""><figcaption></figcaption></figure>

3. Select the **Import Release Pipeline.**
4. Upload the previously exported **JSON** file.
5. Enter a name for the new release pipeline.
6. Review the pipeline details.
7. Click **Create** to create the new release pipeline.

<figure><img src="../../../.gitbook/assets/image (2305).png" alt=""><figcaption></figcaption></figure>

#### ABAP Checkout Task

For RAP applications, there is no Pull Request task. Changes are merged directly into the target branch. The **ABAP Checkout** task ensures that the target BTP ABAP Environment has the appropriate branch checked out in its software component before validation and deployment are performed.

The task monitors the target system until the checkout operation is completed. The result, including success or failure, is recorded against the user story for traceability.

| Field                      | Type     | Description                                                                                                                                                                                                                       |
| -------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name** / **Description** | Text     | Identifies the task.                                                                                                                                                                                                              |
| **Checkout Source**        | Dropdown | Specifies the source of the checkout. Available options include **Branch/Commits from User Story** and **Branch from environment**. When **Branch from environment** is selected, the **Source Environment** field is displayed.  |
| **Target Environment**     | Dropdown | Specifies the environment from which the branch is obtained when **Checkout Source** is set to **Branch from environment**.                                                                                                       |
| **Notify Users**           | Checkbox | Sends notifications when the task completes.                                                                                                                                                                                      |

For a Normal story, which contains commits rather than its own branch, the checkout source is expected to resolve to the target environment's branch after the Merge task has merged the story commits into that branch. This behavior should be verified against the live application screen.

<figure><img src="../../../.gitbook/assets/image (2307).png" alt=""><figcaption></figcaption></figure>

#### Merge Task

The **Merge** task merges changes from a source into the branch associated with the target environment. The source and target branches are resolved at runtime based on the task configuration.

For RAP applications, the Merge task does not require a preceding Pull Request task. The source changes are merged directly into the target branch.

| Field                          | Type                | Description                                                                                                                                    |
| ------------------------------ | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**/ **Description**      | Text                | Identifies the task.                                                                                                                           |
| **Merge Source**               | Dropdown            | Specifies the source of the changes. Options include **Branch/Commits from User Story**, **Branch from environment**, and **Staging branch**.  |
| **Target Environment**         | Dropdown            | Specifies the environment whose branch receives the merged changes.                                                                            |
| **Notify Users**               | Checkbox            | Sends notifications when the task completes.                                                                                                   |
| **Create Staging Branch for**  | Dropdown (Advanced) | Specifies whether a staging branch is created from the target environment branch. Options are **None**, **Release Package**, or **Both**.      |
| **Execute this task only for** | Dropdown (Advanced) | Specifies whether the task applies to **User Story**, **Release Package**, or **Both** promotion modes.                                        |



#### Validate Task

The **Validate** task runs quality checks against the target BTP ABAP Environment and reports the results.

For RAP applications, there is no separate Build task that produces an artifact for validation. The Validate task operates against the code currently checked out in the target environment's software component, following the ABAP Checkout task described in §7.2.

| Field                       | Type     | Description                                                   |
| --------------------------- | -------- | ------------------------------------------------------------- |
| **Name** / **Description**  | Text     | Identifies the task.                                          |
| **Target**                  | Dropdown | Specifies the target environment to validate.                 |
| **Run ATC**                 | Checkbox | Runs ABAP Test Cockpit checks against the software component. |
| **Run ABAP Unit Tests**     | Checkbox | Runs ABAP Unit tests against the software component.          |
| **User Story Dependencies** | Checkbox | Optionally validates user story dependencies.                 |

<figure><img src="../../../.gitbook/assets/image (2308).png" alt=""><figcaption></figcaption></figure>

#### Deployment Task

The **Deployment** task deploys the RAP application to the target BTP ABAP Environment. The RAP Deployment task instructs the target system to pull the current commit from the target environment's branch into the application's software component. The task monitors the target system until the pull operation is completed and records the deployment result for audit and troubleshooting.

| Field                      | Type     | Description                                                      |
| -------------------------- | -------- | ---------------------------------------------------------------- |
| **Name** / **Description** | Text     | Identifies the task.                                             |
| **Select Environment(s)**  | Dropdown | Specifies the target BTP ABAP Environment system for deployment. |
| **Notify Users**           | Checkbox | Sends notifications when the task completes.                     |

The deployment log records details such as the software component, branch, commit, status, and any error message. Possible deployment statuses include **Not Started, In Progress, Success, Failed, Empty** (nothing to pull), **Not Present**, and **Timeout**.

<figure><img src="../../../.gitbook/assets/image (2309).png" alt=""><figcaption></figcaption></figure>



