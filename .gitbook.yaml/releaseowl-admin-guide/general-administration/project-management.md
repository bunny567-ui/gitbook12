# Project Management

Project Management in ReleaseOwl simplifies the planning, execution, and deployment of SAP artifacts by providing centralized control over environments, user roles, and release pipelines.

### Steps to Create a Project

1. Go to the **Administration** page.
2. Under the **Projects** section, click on the **Create New Project** button located at the top right corner.

<figure><img src="../../.gitbook/assets/image (1175).png" alt=""><figcaption></figcaption></figure>

3. A popup form titled **Create Project** will appear.

<figure><img src="../../.gitbook/assets/image (1165).png" alt=""><figcaption></figcaption></figure>

4. Enter the following details:

| **Field**          | **Description**                                                                                |
| ------------------ | ---------------------------------------------------------------------------------------------- |
| **Name**           | Provide a unique name for your project.                                                        |
| **Description**    | Optionally, add a description for better clarity.                                              |
| **Project Prefix** | Specify a prefix that aligns with your project standards. This will act as a short identifier. |
| **Project Type**   | Select the appropriate project type from the dropdown menu. Options might include:             |
|                    | - SAP BTP (MTAR)                                                                               |
|                    | - SAP On-Premise                                                                               |
|                    | - SAP Datasphere                                                                               |
|                    | - Others (based on your environment configuration)                                             |

5. Once all fields are filled, click on the **Save** button to create the project.
6. The newly created project will be listed in the **Projects** table.
7. The table will display key details such as the project’s **name**, **type**, and **creator**.

<figure><img src="../../.gitbook/assets/image (1166).png" alt=""><figcaption></figcaption></figure>

8. To the right of each project, click on the action button(three dots).
9. The **Archive** option is available, which archives the project instead of deleting it.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

10. To view archived projects, open the **Show** dropdown at the top and select **Archived**.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



11. In the **Archived** section, locate the item you want to reactivate.
12. Click the **Actions** button (three dots) next to the item.
13. Select **Activate**. The item will be moved back to the **Active Projects** section .

<figure><img src="../../.gitbook/assets/image (1562).png" alt=""><figcaption></figcaption></figure>

### General Settings Configuration

1. Click on **Project Settings** to navigate to the configuration page of the selected project.

<figure><img src="../../.gitbook/assets/image (1563).png" alt=""><figcaption></figcaption></figure>

2. On the **Project Settings** page, select the **General** tab
3. Select the **General** tab.
4. This section contains basic information about the project, including:
   * **Name**: The project name.
   * **Description**: A brief description of the project.
   * **Project Prefix**: A short identifier for the project.
   * **Default Pipeline**: The pipeline associated with the project.
   * **Attachments are mandatory for User Story Promotion**: &#x20;
     * Enable this option to make attachments mandatory during User Story promotion.
     * When this option is checked, any attempt to promote a User Story without attachments will be restricted.
     * During **Change Management**, if a User Story does not have attachments, an error message will appear, preventing the promotion until the required attachments are added.
5. In the **Release Pipeline (default)** field:
   * Click on the dropdown or the search icon to browse the list of pipelines configured for the project.
6. Click the **Save** button located at the top-right corner to save the details.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :**&#x20;
{% endhint %}

### Environments

1. In the **Project Settings** page, navigate to the **Environments** tab.
2. This section displays all environments already associated with the project.
3. Click on the **+ Add** button in the top-right corner of the Environments table.
4. If this environment will serve as the source for deployments or synchronization, check the **Source** checkbox.
5. The newly added environment will appear in the **Environments** table with its name, type, and host URL.

<figure><img src="../../.gitbook/assets/image (1169).png" alt=""><figcaption></figcaption></figure>

### Users

1. In the **Project Settings** page, click on the **Users** tab.
2. This tab lists all existing users associated with the project.
3. &#x20;Click on the **+ Add button** in the top-right corner of the Users section.
4. &#x20;If applicable, check or uncheck additional permissions or roles to customize the user's access.

<figure><img src="../../.gitbook/assets/image (1170).png" alt=""><figcaption></figcaption></figure>

5\.  Click on the **edit (lock)** icon next to the user for whom you want to manage roles and permissions.

<figure><img src="../../.gitbook/assets/image (1172).png" alt=""><figcaption></figcaption></figure>

6\.  This will open the **Permissions** page for the selected user.

<figure><img src="../../.gitbook/assets/image (1171).png" alt=""><figcaption></figcaption></figure>

### Assign Roles to the User

1. Navigate to the **Roles** section within the **Project Settings**.
2. Check the box next to the desired role(s) you want to assign to the user.
3. The changes are saved automatically once the roles are selected—no need to click a separate Save button.

<figure><img src="../../.gitbook/assets/image (1173).png" alt=""><figcaption></figcaption></figure>

### Grant Deploy Permissions

1. Scroll down to the Environments section.
2. Check the Deploy checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="../../.gitbook/assets/image (1176).png" alt=""><figcaption></figcaption></figure>

### ALM Integration

1. Click the **+ Add** button located in the top-right corner of the ALM Integrations section.
2. &#x20;Fill in the required details:

| Field Name                  | Description                                                               |
| --------------------------- | ------------------------------------------------------------------------- |
| Name                        | Provide a unique integration name for Jira.                               |
| Description                 | Add a description for the integration.                                    |
| External System             | Select the external system from the dropdown.                             |
| Credential                  | Select the pre-configured Jira credential from the dropdown.              |
| Host URL                    | Enter the Jira instance URL.                                              |
| Hosting Type                | Select the hosting type.                                                  |
| Boards / Filters / JQL      | Choose how you want to interact with Jira data (Boards, Filters, or JQL). |
| External Project            | Specify the Jira project key.                                             |
| Board                       | Provide the board name to sync with.                                      |
| Webhook URL                 | Copy and paste the webhook URL provided for syncing with Jira.            |
| <p><br>Disable Comments</p> | You can turn off comments within ALM Integration.                         |

<figure><img src="../../.gitbook/assets/image (1097).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}


**Note:**&#x20;

Webhook Integration supports the following:

1. Issue: create, update, and delete events
2. Sprint: create and update events
3. Further information on registering / configuring webhooks in JIRA can be found @ [https://developer.atlassian.com/server/jira/platform/webhooks/](https://developer.atlassian.com/server/jira/platform/webhooks/)
{% endhint %}

<figure><img src="../../.gitbook/assets/image (186).png" alt=""><figcaption></figcaption></figure>

### Roles

1. In the Project Settings page, navigate to the **Roles** tab. This section lists all roles configured for the project.

<figure><img src="../../.gitbook/assets/image (1179).png" alt=""><figcaption></figcaption></figure>

2. Click on a role (e.g., Demo Roles, QA Approver ) to open the **Role Actions** page.&#x20;

<figure><img src="../../.gitbook/assets/image (1181).png" alt=""><figcaption></figcaption></figure>

3. The page displays the role name and role description available for the selected role.

<figure><img src="../../.gitbook/assets/image (1178).png" alt=""><figcaption></figcaption></figure>

4. In the **Role Actions** page, switch to the **Users** tab. This displays all users currently assigned to the selected role.

<figure><img src="../../.gitbook/assets/image (1180).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The role and the role actions of the selected user under the Users tab in Project Settings match with the ones specified by the admin user while creating this specific user.
{% endhint %}
