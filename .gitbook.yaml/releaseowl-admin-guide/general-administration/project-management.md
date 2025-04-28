# Project Management

roject Management in ReleaseOwl simplifies the planning, execution, and deployment of SAP artifacts by providing centralized control over environments, user roles, and release pipelines.

### Steps to Create a Project

1. **Navigate to the Administration Page**
   * Go to the **Administration** page.
   * Under the **Projects** section, click on the **Create New Project** button located at the top right corner.
2. **Fill in the Project Details**
   * A popup form titled **Create Project** will appear.
   *   Enter the following details:

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
3. **Save the Project**
   * Once all fields are filled, click on the **Save** button to create the project.
4. **View the New Project**
   * The newly created project will be listed in the **Projects** table.
   * The table will display key details such as the project’s **name**, **type**, and **creator**.

<figure><img src="../../.gitbook/assets/image (179).png" alt=""><figcaption></figcaption></figure>

6\.  To the right of each project, click on the action button(three dots).

7\.  Click on Project Settings and this action will navigate you to the configuration page of the selected project

### General Settings Configuration

1. **Access the General Settings**
   * Navigate to the **Project Settings** page.
   * Select the **General** tab.
2. **Overview of General Settings**
   * This section contains basic information about the project, including:
     * **Name**: The project name.
     * **Description**: A brief description of the project.
     * **Project Prefix**: A short identifier for the project.
     * **Default Pipeline**: The pipeline associated with the project.
3. **Set the Default Release Pipeline**
   * In the **Release Pipeline (default)** field:
     * Click on the dropdown or the search icon to browse the list of pipelines configured for the project.
     * Select the desired pipeline to set it as the default (e.g., `DEMO-RELEASE_PIPELINE`).
     * The selected pipeline name will now appear in the field.
4. **Save Changes**
   * Click the **Save** button located at the top-right corner to apply the changes.

<figure><img src="../../.gitbook/assets/image (181).png" alt=""><figcaption></figcaption></figure>

### Environments

1. In the **Project Settings** page, navigate to the **Environments** tab.
2. This section displays all environments already associated with the project.
3. Click on the **+ Add** button in the top-right corner of the Environments table.
4. If this environment will serve as the source for deployments or synchronization, check the **Source** checkbox.
5. The newly added environment will appear in the **Environments** table with its name, type, and host URL.

<figure><img src="../../.gitbook/assets/image (182).png" alt=""><figcaption></figcaption></figure>

### Users

1. In the **Project Settings** page, click on the **Users** tab.
2. This tab lists all existing users associated with the project.
3. &#x20;Click on the **+ Add button** in the top-right corner of the Users section.
4. &#x20;If applicable, check or uncheck additional permissions or roles to customize the user's access.

<figure><img src="../../.gitbook/assets/image (183).png" alt=""><figcaption></figcaption></figure>

5\.  Click on the **edit (lock)** icon next to the user for whom you want to manage roles and permissions.

6\.  This will open the **Permissions** page for the selected user.

### Assign Roles to the User

1. **Access the Roles Section**
   * Navigate to the **Roles** section within the project settings.&#x20;
2. **Select Roles for the User**
   * Check the box next to the desired role(s) for the user.
   * The list of available roles will depend on the project configuration and environment.
3. **Understand Role Capabilities**
   * Each role comes with specific permissions and capabilities as defined by the project or organization.
   * Ensure that the roles assigned align with the user’s responsibilities within the project.
4. **Save Changes**
   * Once roles are assigned, click the **Save** button to apply the changes.

### Grant Deploy Permissions

1. Scroll down to the Environments section.
2. Locate the environment(s) where you want the user to have deploy permissions (e.g.,DEMO-CLOUD-QA).
3. Check the Deploy checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="../../.gitbook/assets/image (184).png" alt=""><figcaption></figcaption></figure>

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



<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

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
2. Click on a role (e.g., Demo Roles, QA Approver to open the Role Actions page. The page displays the name, description, and permissions available for the selected role.
3. In the Role Actions page, switch to the **Users** tab. This displays all users currently assigned to the selected role.

<figure><img src="../../.gitbook/assets/image (187).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The role and the role actions of the selected user under the Users tab in Project Settings match with the ones specified by the admin user while creating this specific user.
{% endhint %}
