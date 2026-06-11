# Manage Roles

The Manage Roles feature in the **Administration View** allows administrators to create, edit, and delete roles to manage user privileges within the platform.

#### Create Role

To create a new role:

1. Click on the **Create Role** button located at the top right corner of the screen.
2. Fill in the required details, such as the **Role Name** and **Description**.
3. Click **Save** to create the new role.

<figure><img src="../../../.gitbook/assets/image (1161).png" alt=""><figcaption></figcaption></figure>

4. Duplicate role names are not allowed. If the role name already exists, you will be prompted to enter a unique name.

<figure><img src="../../../.gitbook/assets/image (1162).png" alt=""><figcaption></figcaption></figure>

5. The newly created role will appear in the list of available roles.

<figure><img src="../../../.gitbook/assets/image (1015).png" alt=""><figcaption></figcaption></figure>

### Assign Role Actions

Role Actions define the permissions and access levels associated with a role. To assign the role actions to an existing role:

1. Click the **Edit** icon next to the role name.

<figure><img src="../../../.gitbook/assets/image (1163).png" alt=""><figcaption></figcaption></figure>



2. The **Role Actions** screen is displayed.

<figure><img src="../../../.gitbook/assets/image (1949).png" alt=""><figcaption></figcaption></figure>

#### Role Actions

The **Role Actions** screen allows administrators to define and manage permissions assigned to a role. Users assigned to a role inherit all permissions configured for that role, enabling controlled access to specific features and operations within the platform. Permissions are grouped into functional categories to simplify role management.

#### Transport Management

Transport Management permissions control the creation, modification, synchronization, and deployment of SAP transports.

| Permission                        | Description                                                                                            |
| --------------------------------- | ------------------------------------------------------------------------------------------------------ |
| **Create Transport**              | Allows users to create new transport requests within a project.                                        |
| **Edit Transport**                | Allows users to modify transport details and configurations.                                           |
| **Release Transport**             | Allows users to release transports for deployment or promotion.                                        |
| **Import Transport**              | Allows users to import transports into target environments.                                            |
| **Sync Transports From SAP**      | Allows users to synchronize transport information directly from connected SAP systems.                 |
| **Manage Critical Objects**       | Allows users to manage and review critical objects contained within transports.                        |
| **Retrofit Transports**           | Allows users to perform retrofit activities across system landscapes.                                  |
| **Remove Transport From Project** | Allows users to remove transport requests that are associated with a project.                          |
| **Promote Transports**            | Allows users to promote transport requests through configured release pipelines and deployment stages. |
| **Import via ToC**                | Allows users to import transport requests using Transport of Copies (ToC).                             |

<figure><img src="../../../.gitbook/assets/image (1950).png" alt=""><figcaption></figcaption></figure>

#### Change Management

Change Management permissions control sprint management and user story administration.

| Permission                                | Description                                                                |
| ----------------------------------------- | -------------------------------------------------------------------------- |
| **Create/Edit Sprint**                    | Allows users to create new sprints and modify existing sprint details.     |
| **Sync Sprints**                          | Allows users to synchronize sprint information from integrated systems.    |
| **Cancel Sprint**                         | Allows users to cancel active or planned sprints.                          |
| **Create/Edit User Stories**              | Allows users to create and update user stories.                            |
| **Sync User Stories**                     | Allows users to synchronize user stories from external tools such as Jira. |
| **Update User Story Status**              | Allows users to modify the status of user stories during execution.        |
| **Promote User Stories**                  | Allows users to promote user stories through defined release stages.       |
| **Change Release Pipeline of User Story** | Allows users to modify the release pipeline associated with a user story.  |

<figure><img src="../../../.gitbook/assets/image (1951).png" alt=""><figcaption></figcaption></figure>

#### CPI Management

CPI Management permissions control SAP Cloud Integration artifact management and deployment activities.

| Permission                                  | Description                                                                        |
| ------------------------------------------- | ---------------------------------------------------------------------------------- |
| **Add/Remove Packages from Project**        | Allows users to associate or remove CPI packages from projects.                    |
| **Sync CPI Artifacts from CPI Environment** | Allows users to synchronize integration artifacts from connected CPI environments. |
| **Assign User Story to CPI Artifact**       | Allows users to link user stories with CPI artifacts for traceability.             |
| **Edit iFlow Configuration**                | Allows users to modify iFlow configuration settings.                               |
| **Download CPI Artifact**                   | Allows users to download CPI artifacts from the environment.                       |
| **Rollback CPI Deployment**                 | Allows users to revert previously deployed CPI artifacts.                          |
| **Generate CPI Testcases**                  | Allows users to create test cases for CPI artifacts.                               |
| **Update CPI Testcases**                    | Allows users to modify existing CPI test cases.                                    |
| **Run CPI Testcases**                       | Allows users to execute CPI test cases and review results.                         |

<figure><img src="../../../.gitbook/assets/image (1952).png" alt=""><figcaption></figcaption></figure>

#### SAC Network Item

SAC Network Item permissions manage integration with SAP Analytics Cloud network items.

| Permission                                         | Description                                                                                         |
| -------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Sync SAC Network Item from SAP Analytics Cloud** | Allows users to synchronize SAC network items from SAP Analytics Cloud.                             |
| **Assign User Story to SAC Network Item**          | Allows users to associate user stories with SAC network items for change tracking and traceability. |

<figure><img src="../../../.gitbook/assets/image (1953).png" alt=""><figcaption></figcaption></figure>

#### Pipelines

Pipeline permissions control build pipeline management activities.

| Permission                          | Description                                                                                                              |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Create Build Pipeline**           | Allows users to create build pipelines.                                                                                  |
| **Edit Build Pipeline**             | Allows users to modify pipeline configurations.                                                                          |
| **Run Build Pipeline**              | Allows users to execute build pipelines.                                                                                 |
| **Delete Build Pipeline**           | Allows users to remove build pipelines from the project.                                                                 |
| **Archive/Active Build Pipeline**   | Allows users to archive build pipelines that are no longer required and reactivate archived build pipelines when needed. |
| **Create Release Pipeline**         | Allows users to create release pipelines for managing artifact promotion and deployment workflows across environments.   |
| **Edit Release Pipeline**           | Allows users to modify the configuration, stages, and settings of existing release pipelines.                            |
| **Run Release Pipeline**            | Allows users to execute release pipelines and initiate the configured deployment process.                                |
| **Delete Release Pipeline**         | Allows users to permanently remove release pipelines that are no longer required from the platform.                      |
| **Abort Release Pipeline**          | Allows users to stop an in-progress release pipeline execution before completion.                                        |
| **Archive/Active Release Pipeline** | Allows users to archive build pipelines that are no longer required and reactivate archived build pipelines when needed. |

<figure><img src="../../../.gitbook/assets/image (1954).png" alt=""><figcaption></figcaption></figure>

#### Release Management

Release Management permissions control release package administration and deployment readiness activities.

| Permission                                     | Description                                                                                                                     |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| **Create Release Package**                     | Allows users to create release packages for organizing and managing deployment-ready artifacts.                                 |
| **Edit Release Package**                       | Allows users to modify the details and configuration of existing release packages.                                              |
| **Delete Release Package**                     | Allows users to permanently remove release packages from the platform.                                                          |
| **Lock Release Package**                       | Allows users to lock release packages to prevent further modifications and ensure deployment readiness.                         |
| **Unlock Release Package**                     | Allows users to unlock release packages that are currently locked or restricted for modifications.                              |
| **Remove Release Package**                     | Allows users to remove a release package from its associated project or release context.                                        |
| **Change Release Pipeline of Release Package** | Allows users to modify the release pipeline associated with a release package and assign it to a different deployment workflow. |

<figure><img src="../../../.gitbook/assets/image (1955).png" alt=""><figcaption></figcaption></figure>

#### Test Automation

Test Automation permissions control test configuration and execution activities.

| Permission                    | Description                                                 |
| ----------------------------- | ----------------------------------------------------------- |
| **Create Test Configuration** | Allows users to create automated test configurations.       |
| **Edit Test Configuration**   | Allows users to modify existing test configurations.        |
| **Run Test Configuration**    | Allows users to execute automated test configurations.      |
| **Delete Test Configuration** | Allows users to remove test configurations from the system. |

<figure><img src="../../../.gitbook/assets/image (1956).png" alt=""><figcaption></figcaption></figure>

4\. Once all role actions are configured as required, click the **Save** button at the top right corner of the screen.

<figure><img src="../../../.gitbook/assets/image (1164).png" alt=""><figcaption></figcaption></figure>

### **Notification Bar in ReleaseOwl**

To keep users informed and up to date, **ReleaseOwl** includes a **Notification Bar** feature that displays important system messages directly within the application interface.

<figure><img src="../../../.gitbook/assets/image (18) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

