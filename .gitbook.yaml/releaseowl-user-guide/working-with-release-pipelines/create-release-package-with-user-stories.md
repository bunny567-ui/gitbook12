# Create Release Package with User Stories

Release Package is a collection of one or more user stories that are validated and deployed as a single entity.

### To create a release package:

1. Go to **Release** and click **Release Packages.**
2. Click **Create New Release Package.**\


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
| **Arrows (**&#xD83D;� 🔽)     | The **arrow buttons** let you change the **execution order** of user stories in the pipeline. Use them when one artifact depends on another, ensuring dependent components are deployed in the correct sequence during pipeline execution. |

4. Click **Save.**

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. When you click the **Show** button, a preview of the user story is displayed. This preview includes details such as the **CPI Artifacts**, their **type**, **version**, and information about **who synced** them and **when**.

<figure><img src="../../.gitbook/assets/image (1228).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1227).png" alt=""><figcaption></figcaption></figure>

6. You can customize the columns seen in the **Create/Edit Release Package** screen by clicking the Settings **Gear** icon.&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

7. Once created, you can see the newly created release package in the **Release Package** page.

<figure><img src="../../.gitbook/assets/image (1129).png" alt=""><figcaption></figcaption></figure>
