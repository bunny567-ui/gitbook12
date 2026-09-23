# Working with Build Pipelines

This section provides a comprehensive guide for configuring Projects, Build Pipelines, and Release Pipelines in **ReleaseOwl** for **SAP ABAP Cloud** environments. By following these steps, teams can ensure controlled, automated, and auditable build and deployment processes within ReleaseOwl.

### Creating a RAP Application&#xD;

1. Navigate to Build → RAP Applications and choose Create. A RAP Application represents one Git-based   &#x20;ABAP Cloud application together with its hotfix strategy, target software component, and per   &#x20;environment landscape.

<figure><img src="../../../.gitbook/assets/image (2275).png" alt=""><figcaption></figcaption></figure>

| **Field**                   | **Type** | **Description**                                                                                                                       |
| --------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------- |
|  **Name**                   | Text     | Unique name of the application. Read-only after creation.                                                                             |
| **Description**             | Text     | Optional free-text description.                                                                                                       |
| **Version Control System**  | Dropdown | The Git provider: Bitbucket, GitHub, Azure DevOps, or GitLab.                                                                         |
| **Repository URL**          | Text     | URL of the application’s Git repository.                                                                                              |
| **SCM Credentials**         | Picker   | The Git credential registered in **Administration.**                                                                                  |
| **Software Component Name** | Text     | The ABAP Cloud software component that the application’s Git repository is linked to inside the target ABAP Cloud Environment system. |

<figure><img src="../../../.gitbook/assets/image (2276).png" alt=""><figcaption></figcaption></figure>

**Landscape Configuration**

1. Click the **Actions** button corresponding to the RAP Application.
2. Select **Edit**.

<figure><img src="../../../.gitbook/assets/image (2272).png" alt=""><figcaption></figcaption></figure>

3. &#x20;The Landscape Configuration defines, for each SAP ABAP Cloud  Environment system, which Git branch it   &#x20;maps to.

| **Field**                   | **Type** | **Description**                                                                                                                                                    |
| --------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **ABAP  Cloud Environment** | Dropdown | The target ABAP Cloud Environment system for this row.                                                                                                             |
| **Branch**                  | Text     | The Git branch mapped to this environment (for example, `dev`, `qa`, or `main`).                                                                                   |
| **Development Branch**      | Checkbox | Marks this environment’s branch as the development branch. In this model, this is the branch from which commits are populated when adding changes to a user story. |

<figure><img src="../../../.gitbook/assets/image (2273).png" alt=""><figcaption></figcaption></figure>

4. Click **Add** to add the application configuration.

<figure><img src="../../../.gitbook/assets/image (2274).png" alt=""><figcaption></figcaption></figure>

