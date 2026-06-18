# Project Management

Project Management in **ReleaseOwl** simplifies the planning, execution, and deployment of SAP artifacts by providing centralized control over environments, user roles, and release pipelines.

### Steps to Create a Project

1. Go to the **Administration** page.
2. Under the **Projects** section, click on the **Create New Project** button located at the top right corner.

<figure><img src="../../../.gitbook/assets/image (1866).png" alt=""><figcaption></figcaption></figure>

3. A popup form titled **Create Project** will appear.

<figure><img src="../../../.gitbook/assets/image (1867).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../../.gitbook/assets/image (1868).png" alt=""><figcaption></figcaption></figure>

## Project Management Options

To the right of each project, click the **Actions menu** (three dots) to view the available project management options.

<figure><img src="../../../.gitbook/assets/image (1871).png" alt=""><figcaption></figcaption></figure>

### **Switch To Project**

The **Switch To Project** option allows users to directly navigate from the Administration view to the selected project workspace. This helps users quickly access and manage project-specific activities without manually searching for the project.

<figure><img src="../../../.gitbook/assets/image (1873).png" alt=""><figcaption></figcaption></figure>

### **Archive**

The **Archive** option allows users to archive projects that are no longer actively used. Archived projects are retained for reference and historical purposes while being removed from the active projects list.

To view archived projects:

1. Open the **Show** dropdown at the top of the page.
2. Select **Archived**.

<figure><img src="../../../.gitbook/assets/image (1875).png" alt=""><figcaption></figcaption></figure>

To reactivate an archived project:

1. In the **Archived** section, locate the project you want to reactivate.
2. Click the **Actions menu** (three dots) next to the project.
3. Select **Activate**.

The project will be moved back to the **Active Projects** section.

<figure><img src="../../../.gitbook/assets/image (1874).png" alt=""><figcaption></figcaption></figure>

### **Delete**

The **Delete** option allows users to permanently remove a project from the application. Once deleted, the project and its associated configurations are no longer available in the system.

<figure><img src="../../../.gitbook/assets/image (1869).png" alt=""><figcaption></figcaption></figure>

### **Project Settings**

The **Project Settings** option allows users to configure and manage project-specific settings. Users can update project configurations, manage ALM integrations, maintain environment details, and modify project-related parameters based on the project requirements.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Project Settings Configuration

1. Navigate to the required project.
2.  Click on **Project Settings** to open the configuration page.  The **Project Settings** page contains multiple tabs that allow users to configure and manage different project-level settings, including:

    * **General**
    * **Environments**
    * **Users**
    * **ALM Integrations**
    * **Roles**

    Each tab provides specific configuration options related to project management and integrations.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **General Tab**

The **General** tab contains the basic project configuration details and settings. Users can configure default release pipelines, validation settings, approval workflows, and project-specific integration settings based on the selected project type.

<table><thead><tr><th width="374">Field</th><th>Description</th></tr></thead><tbody><tr><td><strong>Name</strong></td><td>Displays the project name.</td></tr><tr><td><strong>Description</strong></td><td>Provides a brief description of the project.</td></tr><tr><td><strong>Project Prefix</strong></td><td>A short identifier used for the project.</td></tr><tr><td><strong>Project Type</strong></td><td>Displays the type of project that was selected during project creation. This field is auto-populated based on the configured project type.</td></tr><tr><td><strong>Release Pipeline(default)</strong> </td><td>Specifies the default release pipeline associated with the project. The selected pipeline is used as the default pipeline for release and deployment activities within the project.</td></tr></tbody></table>

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Additional Settings**

These settings control validation and approval workflows:

**1. Attachments Mandatory for User Story Promotion**

* Enable this option to make attachments mandatory during user story promotion.
* When enabled:
  * Promotion of a user story without attachments is restricted.
  * During Change Management, an error message is displayed if attachments are missing.
  * Promotion is blocked until the required attachments are added.

**2. Do Not Approve Without Opening Task Details**

* Enable this option to require users to open and review task details before approving tasks or workflow actions.
* This helps ensure proper validation before approval.

**3. Enable User Story Component Field as Required**

* Enable this option to make the **Components** field mandatory while creating or updating a user story.
* Components can be configured at the project level and help improve categorization and organization of user stories.

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**On-Premise Integration Settings**

When the project type is selected as an **On-Premise System**, the following additional configuration options are available. These settings apply to projects integrated with on-premise systems such as SAP environments.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Set Transport Description from User Story**

* Automatically populates the transport request description using linked user story details.&#x20;
* This improves traceability and ensures consistent transport documentation.

**Enable Project Field as Required During Transport Creation**

* Enable this option to make the **Project** field mandatory during transport creation.
* This ensures accurate mapping of transports to projects and improves tracking, reporting, and auditability.

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



**SAP CPI  Integration Settings**

When the project type is selected as **SAP CPI**, the following additional configuration options are available. These settings apply to projects integrated with SAP Cloud Platform Integration (CPI) systems.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**CPI Settings**

These settings are used to configure Cloud Integration (CPI) validations and compliance checks for integration artifacts.

**CPI Validation Controls**

Projects can enable the following validations:

**Lint Validation**

* Validates integration artifacts against technical standards and best practices.
* This validation helps identify coding inconsistencies, configuration issues, and potential deployment problems before deployment.

**Design Compliance Validation**

* Validates CPI artifacts against defined design guidelines and compliance standards.
* This validation uses reports configured at the project level to ensure integration artifacts comply with organizational standards and best practices.

<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Saving the Configuration**

* Click the **Save** button located at the top-right corner of the page to apply and save all changes.

<figure><img src="../../../.gitbook/assets/image (11) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Environments

The **Environments** tab allows users to add and manage environments associated with the project.

To add an environment, follow these steps:

1. Click the **+ Add** button located at the top-right corner of the Environments table.
2. Select the required environments from the popup list.
3. If the environment will serve as the source for deployments or synchronization, enable the **Source** checkbox.
4. Click **Save** to add the environment.

The newly added environment will appear in the Environments table with details such as the environment name, type, and host URL.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Users

The **Users** tab displays all users associated with the project. Users can be added to the project, assigned roles, and granted specific permissions such as deploy access for selected environments.

To add users to the project, follow these steps:

1. Click the **+ Add** button located at the top-right corner of the Users section.
2. Select the required user(s) from the popup list.
3. Click the **Select** button to add the selected users to the project.
4. The selected users will appear in the Users table.

**Project Admin Access**

When the **Project Admin** option is selected for a user, the user is granted project-level administrative privileges. Project Administrators can perform the following actions:

* Manage project configurations.
* Add or remove users from the project.
* Assign roles and permissions.
* Configure ALM integrations.
* Grant deployment permissions for environments.
* Review and approve project tasks.

**Non-Project Admin Access**

When the **Project Admin** option is disabled and no roles are assigned, the user is granted **view-only access** to the project.

Users can view project information, including:

* User Stories
* Sprints
* Builds
* Tasks
* Deployment information
* Reports and other project-related data

{% hint style="info" %}
**Note :** If tasks are assigned directly to the user within a **Release Pipeline**, the user can view those tasks and perform the assigned approval actions, such as **Approve** or **Reject**.
{% endhint %}

**Role-Based Access**

If the **Project Admin** option is not selected, the user receives access based on the permissions defined by the assigned role.

Depending on the configured role, users may be granted permissions such as:

* Read-only access to project resources.
* Other project-specific actions defined by the role configuration.

Role-based access ensures that users can perform only the actions required for their responsibilities within the project



<figure><img src="../../../.gitbook/assets/image (1170).png" alt=""><figcaption></figcaption></figure>

5. Click the **Edit (Lock)** icon next to the user for whom you want to manage roles and permissions.

<figure><img src="../../../.gitbook/assets/image (1172).png" alt=""><figcaption></figcaption></figure>

6. This opens the **Permissions** page for the selected user, where roles and environment-specific permissions can be configured.

<figure><img src="../../../.gitbook/assets/image (1171).png" alt=""><figcaption></figcaption></figure>

**Grant Deploy Permissions**

1. Scroll down to the Environments section.
2. Check the Deploy checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="../../../.gitbook/assets/image (1176).png" alt=""><figcaption></figcaption></figure>

#### ALM Integration

The **ALM Integrations** tab is used to configure and manage integrations with Application Lifecycle Management (ALM) tools. Users can add and maintain integration details required for project-level ALM connectivity and synchronization.  To add **ALM Integration** to the project, follow these steps:

1. Click the **+ Add** button located in the top-right corner of the ALM Integrations section.
2. &#x20;Fill in the required details:

| Field Name                                   | Description                                                                         |
| -------------------------------------------- | ----------------------------------------------------------------------------------- |
| **Name**                                     | Provide a unique integration name for Jira.                                         |
| **Description**                              | Add a description for the integration.                                              |
| **External System**                          | Select the external system from the dropdown.                                       |
| **Credential**                               | Select the pre-configured credential from the dropdown.                             |
| **Host URL**                                 | Select the **Host URL** based on the external system that you want to connect with. |
| <p><br><strong>Disable Comments</strong></p> | You can turn off comments within **ALM** Integration.                               |

<figure><img src="../../../.gitbook/assets/image (1711).png" alt=""><figcaption></figcaption></figure>

#### Roles

The **Roles** tab displays all roles configured for the project. Users can view role details, manage role assignments, and configure role-based actions and permissions for project users.

To view and manage roles, follow these steps:

1. Navigate to the **Roles** tab in the **Project Settings** page.
2. This section displays all roles configured for the project.

<figure><img src="../../../.gitbook/assets/image (1179).png" alt=""><figcaption></figcaption></figure>

3. Click the **Person** icon corresponding to a role to open the **Role Actions** page.

<figure><img src="../../../.gitbook/assets/image (1181).png" alt=""><figcaption></figcaption></figure>

4. The **Role Actions** page displays the role name, description and the role actions assigned to the selected role within the project.

<figure><img src="../../../.gitbook/assets/image (1876).png" alt=""><figcaption></figcaption></figure>

5. In the **Role Actions** page, navigate to the **Users** tab.
6. This section displays all users currently assigned to the selected role.

<figure><img src="../../../.gitbook/assets/image (1180).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The role and the role actions of the selected user under the Users tab in **Project Settings** match with the ones specified by the admin user while creating this specific user.
{% endhint %}
