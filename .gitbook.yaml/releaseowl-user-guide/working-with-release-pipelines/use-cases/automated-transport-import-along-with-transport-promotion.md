# Automated Transport import along with Transport Promotion

### **Release Pipelines**

Release Pipelines orchestrate automated deployments into SAP environments with the right approvals in place. Each pipeline can contain **one or more stages**, corresponding to SAP environments like Dev, QA, Staging, and Production.

{% hint style="info" %}
**Note:** You can create a multi-stage pipeline for continuous deployment across various environments one after the other towards continuous delivery of application all through Dev - QA - Staging - Production.
{% endhint %}

### **Creating a Release Pipeline**

Creating a Release Pipeline is a three-step process.

| **Step1** | Enter a name in Release Pipeline Name                                                                                                    |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Step2** | Click '**Add Stages**' to add the required stages. Add various types of pre-deployment, deployment, and post-deployment tasks as needed. |
| **Step3** | Specify the email ids to receive notifications about release pipeline execution status.                                                  |

#### For creating release pipeline:

1.  Select the required On-Prem Project and in Release go to Release Pipelines.\


    <figure><img src="../../../.gitbook/assets/image (15) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
2. Click **Create New Release Pipeline.**
3. **Release Pipeline Name:** Give a name for the release pipeline.\


<figure><img src="../../../.gitbook/assets/image (13) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4.  **Add Stages:**

    * Click **Add Stage**
    * Name the stage (e.g., `Dev`, `QA`, `UAT`, `Prod`)
    * Click **OK**\


    <figure><img src="../../../.gitbook/assets/image (14) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
5. **Add Tasks in Each Stage:** Click **Add** to configure tasks within the stage.\


<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** All the tasks **except Deployment** Task are similar for any project type.
{% endhint %}

6. Once all tasks are added, click the **Save** button to finalize the pipeline configuration.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Post-Creation Options**

Once the Release Pipeline is created, you can use the **Actions** button for the following options:

* **Delete**: Permanently removes the pipeline from the project.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
