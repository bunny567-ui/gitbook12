# Reports

The **Reports** section in the Administration View provides ready-made access reports for the tenant. These reports provide a consolidated view of **user roles and project access**, as well as the **permissions associated with each role**, eliminating the need to review access details individually through the User Management screens.

### Accessing Reports

1. Switch to the **Administration** view.
2. In the left navigation, click **Reports**.

<figure><img src="../../.gitbook/assets/image (2196).png" alt=""><figcaption></figcaption></figure>

3. The **User Permissions** tab displays **Users and Roles** and **Roles and Permissions**. The **Search by reports** bar is used to search for these by name.

<figure><img src="../../.gitbook/assets/image (2199).png" alt=""><figcaption></figcaption></figure>

### User and Roles Report

The User and Roles report lists all users along with their projects, assigned roles, and access status, providing the complete user-to-access mapping of the tenant in a single view.

| Column             | Description                                                                                                                                                                                                                                                                                                                                                            |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User**           | User name, first name, and last name.                                                                                                                                                                                                                                                                                                                                  |
| **Project**        | The project the access applies to.                                                                                                                                                                                                                                                                                                                                     |
| **Assigned Roles** | The role(s) assigned to the user in that project.                                                                                                                                                                                                                                                                                                                      |
| **Status**         | <p>The user's access status which include Active and No Access.</p><p><strong>Active:</strong> The user has working access — they are assigned to the project with role(s) or permissions.<br><strong>No Access</strong>: The user exists in the tenant but has no effective access — they are not assigned to any project (or hold no role or permissions in it).</p> |

**Summary counters** displayed at the top of the report:

| Counter                       | Description                                                                                           |
| ----------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Total Users**               | Total number of users registered in the tenant.                                                       |
| **Users with project access** | Number of users assigned to at least one project.                                                     |
| **Distinct roles in use**     | Number of different roles currently assigned to at least one user — a quick indicator of role sprawl. |
| **Users without any project** | Number of users not assigned to any project.                                                          |

<figure><img src="../../.gitbook/assets/image (2191).png" alt=""><figcaption></figcaption></figure>

**To use the report:**

1. Open the **User and Roles** report.
2. Select a **project** to filter the report to that project's users and access.
3. Get the details of the project according to the user.

<figure><img src="../../.gitbook/assets/image (2192).png" alt=""><figcaption></figcaption></figure>

4. Click **EXCEL** to download the report of that user.

<figure><img src="../../.gitbook/assets/image (2193).png" alt=""><figcaption></figcaption></figure>

### Role and Permissions

The Role and Permissions report shows every role with its modules and granted actions — the effective definition of each role, grouped and searchable

<figure><img src="../../.gitbook/assets/image (2194).png" alt=""><figcaption></figcaption></figure>

Use the **Search by roles** bar to search for a role by the name it was created with. Selecting a role displays its **modules** — the functional areas the role covers, such as API Artifact or CPI Artifact — with the granted **actions** listed under each module (for example, _Configure_ or _ImportSettings_). The report can also be downloaded using the **EXCEL** option.

<figure><img src="../../.gitbook/assets/image (2195).png" alt=""><figcaption></figcaption></figure>
