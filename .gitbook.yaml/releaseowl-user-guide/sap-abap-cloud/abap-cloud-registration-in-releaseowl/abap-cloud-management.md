# ABAP Cloud Management

This section provides a comprehensive guide for configuring Projects, Build Pipelines, and Release Pipelines in ReleaseOwl for SAP BTP ABAP Cloud environments. By following these steps, teams can ensure controlled, automated, and auditable build and deployment processes within ReleaseOwl.

### Create the Project <a href="#create-the-project" id="create-the-project"></a>

1. Go to the **Administration** page of the application.
2. Under the **Projects** section, locate the **Create New Project** button.
3. Click on the **Create New Project** button located at the top right corner.
4. A popup form titled **Create Project** will appear.
5. Enter the following details:

| **Field**          | **Description**                                                                                |
| ------------------ | ---------------------------------------------------------------------------------------------- |
| **Name**           | Provide a unique name for your project.                                                        |
| **Description**    | Optionally, add a description for better clarity.                                              |
| **Project Prefix** | Specify a prefix that aligns with your project standards. This will act as a short identifier. |
| **Project Type**   | Select **SAP C** as the project type.                                                          |

<figure><img src="../../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

6. To the right of each project, click on the **action button** (three dots).
7. Click on **Switch To Project** to navigate to the configuration page of the selected project.

<figure><img src="../../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

8. Navigate to the **Project Settings** page. Click the **Environments** tab.
9. Click **+ Add** (top-right of the **Environments** table).
10. Select the desired environment and click **Select**.
11. If this environment is the **source for deployments or synchronization**, check the **Source** checkbox.

<figure><img src="../../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

**Manage User Roles and Permissions**

* Go to the **Users** tab.
* Click the **Edit (lock) icon** next to the user.
* Check the **Deploy** checkbox for relevant environment(s).

<figure><img src="../../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

### Build Pipeline Configuration in ReleaseOwl

#### Step 1: Create a New Build Pipeline

1. Navigate to **Build Pipelines** in the ReleaseOwl dashboard.
2. Click **New Build Pipeline**.

<figure><img src="../../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

3. Select **Create New Build Pipeline**.
4. Click **Create**.

<figure><img src="../../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

5. Enter the **Pipeline Name** (as per your naming convention).
6. Click **Next (Step 2)**.

<figure><img src="../../../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

#### Step 2: Configure Environment Details

1. Select the registered **ABAP Environment**.
2. For the **Software Component Name**:
   * Go to **Manage Software Components** in ABAP Cloud.
   * Copy the exact **Software Component Name**.
   * Paste it into the **Software Component** field in **ReleaseOwl**.

<figure><img src="../../../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

* For the **Branch Name**:
  * In the Software Component details, locate the available branch.
  * Copy the required branch name.

<figure><img src="../../../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

* Paste it into the Branch field.
* Click **Next (Step 3)**.

<figure><img src="../../../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

#### Step 3: Quality Checks Configuration

1. In this step, enable **ATC Checks** to perform static code analysis and ensure compliance with coding standards, performance, and security guidelines.
2. Enable **ABAP Unit Test Checks** to execute automated unit tests and validate the functional correctness of the code.&#x20;
3. These checks help maintain code quality and prevent defective or non-compliant code from progressing in the pipeline.
4. Click **Next (Step 4)** to continue.

<figure><img src="../../../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

#### Step 4: Execution Settings

1. Choose the execution mode:
   * **Manual** (triggered manually), or
   * **Scheduled** (runs at defined intervals).
2. Click **Next**.
3. Enter the required **Email ID(s)** for notifications.
4. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

#### Run the Build Pipeline

After saving:

1. Select the created Build Pipeline.
2. Click **Build Now** to trigger the execution.
3. The system will display the status of the latest build (Success or Failure).

<figure><img src="../../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Before triggering the build, ensure all relevant Transport Requests (TRs) are in the **Released** stage. Builds may fail if transports are not released.
{% endhint %}

4.  Upon completion, the build results will include:

    * **ATC Report** (static code analysis results)

    <figure><img src="../../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

    * **ABAP Unit Test Report** (unit test execution results)

    <figure><img src="../../../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

    * Overall build execution status

    These reports can be accessed directly from the build details screen.

<figure><img src="../../../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

### Release Pipelines

**Release Pipelines** in **ReleaseOwl** facilitate orchestrated deployments to SAP environments with structured approval workflows. A pipeline can consist of one or more stages, each representing a deployment phase (e.g., Dev, QA, Prod). Within each stage, users can define a sequence of actions including approval tasks, manual interventions, deployment steps, external callouts, and automated test executions—ensuring controlled and auditable releases across the landscape.

#### **Creating a Release Pipeline**

Creating a **Release Pipeline** is a three-step process.

| Step 1 | Enter a name in Release Pipeline Name                                                                                                    |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Step 2 | Click '**Add Stages**' to add the required stages. Add various types of pre-deployment, deployment, and post-deployment tasks as needed. |
| Step3  | Specify the email ids to receive notifications about release pipeline execution status.                                                  |

#### **For creating release pipeline:**

1. Navigate to **Release** and click on the **Release Pipelines.**
2. Click **Create New Release Pipeline**.

<figure><img src="../../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

3. Enter the release pipeline name&#x20;

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)   (6).png" alt=""><figcaption></figcaption></figure>

4. Click **Add Stage**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) ( (2).png" alt=""><figcaption></figcaption></figure>

<br>

5. **Tasks:** Click Add to enter any tasks that are to be performed

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** To remove any stage, click Remove stage button.
{% endhint %}

6. Different tasks that can be added are as follows:

<figure><img src="../../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** All the tasks except Deployment Task are similar for any project type. For CPI projects, Wait for Promotion and Validation tasks are the two extra tasks available other than the ones available for every project type.
{% endhint %}

### **Deployment Task**

The **Deployment Task** in the **Release Pipeline** is responsible for deploying the validated software component to the configured SAP BTP ABAP Environment.

<figure><img src="../../../.gitbook/assets/image (64).png" alt=""><figcaption></figcaption></figure>



<table><thead><tr><th></th><th width="502"></th></tr></thead><tbody><tr><td>Name </td><td>Enter any name of your choice for the approval task being created.</td></tr><tr><td>Description</td><td>Any message that is to be conveyed for the deployment.</td></tr><tr><td>Select Environment</td><td>Choose the registered ABAP Environment (e.g., QA or Production).</td></tr><tr><td>Component Name </td><td>Enter the Software Component name exactly as maintained in ABAP Cloud</td></tr><tr><td>Branch Name</td><td>Enter the corresponding Git branch (e.g., main).</td></tr><tr><td>Schedule Time</td><td>You can execute a Release Pipeline either manually or can schedule it to get executed automatically once its reference build pipeline gets executed successfully.</td></tr></tbody></table>

<figure><img src="../../../.gitbook/assets/image (65).png" alt=""><figcaption></figcaption></figure>

#### Run the Release Pipeline

1. After creating the pipeline, click **Run**.
2. Enter the **Cycle Name**.
3. Select the corresponding **Build**.
4. Trigger the pipeline execution.

The release process will execute according to the defined stages and tasks, ensuring a controlled and auditable deployment across environments.

<figure><img src="../../../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>
