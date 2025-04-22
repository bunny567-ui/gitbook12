# Create Release Package with Transports

Release Package is a collection of one or more user stories or transports that are validated and deployed as a single entity.

### To create a release package:

1. Go to **Release** and click **Release Packages.**
2. Click **Create New Release Package.**\


<figure><img src="../../.gitbook/assets/image (1034).png" alt=""><figcaption></figcaption></figure>

3. Fill in the necessary details:&#x20;

| **Field / Element**            | **Description**                                                                                                                                               |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                       | Enter the name of the new Release Package. This is a mandatory field.                                                                                         |
| **Description**                | Provide an optional description for the package to clarify its purpose or content.                                                                            |
| **Release Pipeline**           | Select the Release Pipeline that should be triggered for deployment upon promotion of the Release Package.                                                    |
| **Promote from (Stage)**       | Default is `Dev`. Displays the list of stages defined in the selected Release Pipeline (excluding the final stage like `Prod`).                               |
| **Add Stories for Promotion**  | Automatically adds all eligible **transports** that are **not already part of another release package** and are ready to be promoted from the selected stage. |
| **Add User Story / Transport** | Allows manual selection of user stories or transports from the selected Promote from (Stage). You can select multiple entries in one go.                      |
| **Auto Sequence**              | If selected, the transports will be imported in the same order as they appear in the STMS import queue, ensuring consistency.                                 |

<figure><img src="../../.gitbook/assets/image (1036).png" alt=""><figcaption></figcaption></figure>



4. Clicking the **eye icon** on a user story shows its summary and transport details, such as the status and version control information.

<figure><img src="../../.gitbook/assets/image (1035).png" alt=""><figcaption></figcaption></figure>

5. You can customize the columns seen in the **Create/Edit Release Package** screen by clicking the Settings Gear icon next to **Add Transport / Add User Story** option.\


<figure><img src="../../.gitbook/assets/image (1039).png" alt=""><figcaption></figcaption></figure>



6. Once created, you can see the newly created release package in the Release Package page.

<figure><img src="../../.gitbook/assets/image (1037).png" alt=""><figcaption></figcaption></figure>
