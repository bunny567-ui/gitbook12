# Create Release Package with CPI

Release Package is a collection of one or more user stories that are validated and deployed as a single entity.

### To create a release package:

1. Go to **Release** and click **Release Packages.**
2. Click **Create New Release Package.**<br>

<figure><img src="../../.gitbook/assets/image (1032).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** You can create a Release Package with User Stories for an SAP Integration Suite project.
{% endhint %}

3. Fill in the necessary details:&#x20;

| **Field / Element**           | **Description**                                                                                                                                                                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Name**                      | Enter the name of the new Release Package. This is a mandatory field.                                                                                                                                                                      |
| **Description**               | Provide an optional description for the package to clarify its purpose or content.                                                                                                                                                         |
| **Release Pipeline**          | Select the Release Pipeline that should be triggered for deployment upon promotion of the Release Package.                                                                                                                                 |
| **Promote from (Stage)**      | Default is `Dev`. Displays the list of stages defined in the selected Release Pipeline (excluding the final stage like `Prod`).                                                                                                            |
| **Add Stories for Promotion** | Automatically adds all eligible user stories that are **not already part of another release package** and are ready to be promoted from the selected stage.                                                                                |
| **Add User Story**            | Allows manual selection of user stories  from the selected Promote from (Stage). You can select multiple entries in one go.                                                                                                                |
| **Arrows (**&#x1F53C; 🔽)     | The **arrow buttons** let you change the **execution order** of user stories in the pipeline. Use them when one artifact depends on another, ensuring dependent components are deployed in the correct sequence during pipeline execution. |

4. Click **Save.**

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (19).png" alt=""><figcaption></figcaption></figure>

5. When you click the **Show** button, a preview of the user story is displayed. This preview includes details such as the **CPI Artifacts**, their **type**, **version**, and information about **who synced** them and **when**.

<figure><img src="../../.gitbook/assets/image (1228).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1227).png" alt=""><figcaption></figcaption></figure>

6. You can customize the columns seen in the **Create/Edit Release Package** screen by clicking the Settings **Gear** icon.&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (29).png" alt=""><figcaption></figcaption></figure>

7. Once created, you can see the newly created release package in the **Release Package** page.

<figure><img src="../../.gitbook/assets/image (1129).png" alt=""><figcaption></figcaption></figure>

#### Release Package Actions

The following actions can be performed on each release package.

| Action                         | Description                                                                                                     |
| ------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| **Edit**                       | Modify the Release Package details and manage the associated SAP CPI artifacts, such as iFlows.                 |
| **Validate**                   | Validate the CPI artifacts and configurations included in the Release Package before promotion.                 |
| **Validation Report**          | View the validation results, including any errors or warnings identified in the CPI artifacts.                  |
| **Promote**                    | Promote the CPI Release Package to the next environment in the configured Release Pipeline.                     |
| **Pipeline Activity**          | View the pipeline execution details and status of the Release Package across different stages and environments. |
| **Unlock**                     | Unlock the CPI Release Package to allow further actions or modifications.                                       |
| **Deployment History**         | View the deployment history and status of the CPI artifacts across environments.                                |
| **Audit History**              | View the history of changes and actions performed on the CPI Release Package.                                   |
| **Archive**                    | Archive the CPI Release Package when it is no longer required for active release activities.                    |
| **Release Audit Report (PDF)** | Generate a PDF report containing the audit and release activity details of the CPI Release Package.             |

<figure><img src="../../.gitbook/assets/image (2163).png" alt=""><figcaption></figcaption></figure>

### **Validation Report**

Validation report is visible only after the validation process is complete.\
\
**To view the validation report:**

1\. Go to a required package and click **Actions**. Click **Validation Report**.

2\. The validation report is displayed below.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

#### CPI Governance

**CPI Governance** in ReleaseOwl provides a centralized framework for defining and enforcing governance policies and best practices for **SAP Cloud Integration (CPI)** artifacts. It helps ensure that integration flows follow consistent **security, coding, design, and operational standards** across projects.

#### How CPI Governance Works

1. **Define Governance Rules**\
   Administrators configure **CPI Rules** in ReleaseOwl to establish the required governance standards for CPI artifacts.
2. **Validate CPI Artifacts**\
   When a CPI artifact is validated, ReleaseOwl automatically checks it against the configured governance rules and **CPI Design Guidelines**.
3. **Generate Compliance Results**\
   The validation produces a compliance report indicating whether the artifact is **Compliant** or **Non-Compliant**. Findings are categorized by severity, such as **High, Medium, and Low**.
4. **Review and Fix Issues**\
   The validation results provide actionable information about the identified issues. Users can access the affected integration flow steps directly from the report to review and address the findings.
5. **Follow Recommended Practices**\
   The guidelines can also reference recommended integration packages, such as **CPI Cloud Exemplar**, to help developers follow proven patterns for performance, security, and efficiency.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### CPI Downgrade Check

This feature ensures that the correct user story is reused during a downgrade operation when a target version already exists.

#### How CPI Downgrade  Works

1. During a downgrade, the system checks whether the **target version** is already associated with a user story.
2. If a user story already exists for the target version, the system displays that **existing user story**.
3. After the downgrade validation is successful, the system **reuses the same artifact-assigned user story**.
4. The reused user story is displayed in the **Target User Story** column.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

#### User Story Dependency Check

**User Story Dependency Check** is a validation mechanism in ReleaseOwl that ensures a user story’s dependent user stories have already been deployed to the **correct target system and stage** before the current user story is deployed.

It prevents a user story from being deployed when one of its required dependent stories is missing from the expected environment.

#### How User Story Dependency Check Works

When the **Validation Task** runs, it checks the dependencies associated with the user story and determines where each dependent user story is expected to be deployed. The validation behavior depends on the project relationship and the availability of **Landscape Stage Mapping**.

1.  **Multiple target stages mapped to the same system**

    * If multiple target stages are mapped to the same system for a landscape, the dependent user story is expected to be deployed to **all mapped target systems**.
    * If the deployment is missing in even one of the mapped target systems, the validation fails.

    <figure><img src="../../.gitbook/assets/image (2162).png" alt=""><figcaption></figcaption></figure>
2. **Dependent user story belongs to a different project**
   * If the dependent user story belongs to another project and no Landscape Stage Mapping is configured, ReleaseOwl cannot determine the corresponding target system or stage.
   * In this case, the Validation Task throws an exception.
3. **Dependent user story belongs to the same project**
   * If the dependent user story belongs to the same project and no Landscape Stage Mapping is configured, the **current target stage** is used for validation.
   * The Validation Task checks whether the dependent user story has already been deployed to that stage.
   * No exception is raised.
4. **Cyclic dependency**
   * ReleaseOwl also prevents circular dependencies between user stories.
   * For example, if **User Story A depends on User Story B**, and User Story B directly or indirectly depends on User Story A, a cyclic dependency exists.
   * When such a dependency is added, ReleaseOwl throws an error and blocks the dependency from being created.

<figure><img src="../../.gitbook/assets/image (2159).png" alt=""><figcaption></figcaption></figure>
