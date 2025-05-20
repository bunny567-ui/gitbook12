# Create Release Package with User Stories

Release Package is a collection of one or more user stories or transports that are validated and deployed as a single entity.

### To create a release package:

1. Go to **Release** and click **Release Packages.**\


<figure><img src="../../.gitbook/assets/image (1032).png" alt=""><figcaption></figcaption></figure>

2. Click **Create New Release Package.**

{% hint style="info" %}
**Note:** You can create a Release Package with only User Stories for an SAP Integration Suite project.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (1031).png" alt=""><figcaption></figcaption></figure>

3. Fill in the necessary details:&#x20;

| **Field / Element**           | **Description**                                                                                                                                             |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                      | Enter the name of the new Release Package. This is a mandatory field.                                                                                       |
| **Description**               | Provide an optional description for the package to clarify its purpose or content.                                                                          |
| **Release Pipeline**          | Select the Release Pipeline that should be triggered for deployment upon promotion of the Release Package.                                                  |
| **Promote from (Stage)**      | Default is `Dev`. Displays the list of stages defined in the selected Release Pipeline (excluding the final stage like `Prod`).                             |
| **Add Stories for Promotion** | Automatically adds all eligible user stories that are **not already part of another release package** and are ready to be promoted from the selected stage. |
| **Add User Story**            | Allows manual selection of user stories  from the selected Promote from (Stage). You can select multiple entries in one go.                                 |
| **Auto Sequence**             | If selected, the user stories will be imported in the same order as they appear in the STMS import queue, ensuring consistency.                             |

4. Click **Save.**
5.  You can customize the columns seen in the **Create/Edit Release Package** screen by clicking the Settings Gear icon. \
    \


    <figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
6. Once created, you can see the newly created release package in the **Release Package** page.

<figure><img src="../../.gitbook/assets/image (1129).png" alt=""><figcaption></figcaption></figure>
