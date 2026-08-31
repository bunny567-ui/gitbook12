# Datasphere Management

This section describes the process of configuring and managing **Datasphere Management** environments in **ReleaseOwl**.

### **Adding SAP Datasphere to the Project** <a href="#pdf-page-gxe94pcl07aymb35lkd4-adding-sac-environments-to-the-project" id="pdf-page-gxe94pcl07aymb35lkd4-adding-sac-environments-to-the-project"></a>

The SAP Datasphere must be registered in **Project Settings** in ReleaseOwl.

1.  **To register SAP datasphere:**

    * Go to the **Projects** drop-down at the top right corner and click **Project Settings**.
    * In **Project Settings**, navigate to **Environment**.
    * The following screen is displayed.

    <figure><img src="../../.gitbook/assets/image (2247).png" alt=""><figcaption></figcaption></figure>
2.  **Click Add** to add a new environment in ReleaseOwl.

    * In the subsequent screen, select the required environments from the list displayed.
    * Select **Source environment** and **Save** the changes.

    <figure><img src="../../.gitbook/assets/image (969).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Only the artifacts from the source are synced to ReleaseOwl.
{% endhint %}

3. The environment gets added to the corresponding project in ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (2248).png" alt=""><figcaption></figcaption></figure>

4. Click on the **Users** tab. This tab lists all existing users associated with the project.
5. Click on the **edit (lock)** icon next to the user for whom you want to manage roles and permissions.
6. This will open the **Permissions** page for the selected user.

<figure><img src="../../.gitbook/assets/image (981).png" alt=""><figcaption></figcaption></figure>

7. Under the **lock icon** button. The roles assigned to the selected user are displayed.

<figure><img src="../../.gitbook/assets/image (973).png" alt=""><figcaption></figcaption></figure>

8. Scroll down to the Environments section.
9. Check the Deploy checkbox for the relevant environment(s) to enable deploy access.

<figure><img src="../../.gitbook/assets/image (972).png" alt=""><figcaption></figcaption></figure>

### **SAP Datasphere Packages**

SAP Datasphere packages are managed in the project view under **Build → SAP Datasphere**. This page lists the packages synchronized from the source environment, and is where you sync new packages, review their versions, and maintain each package's Import Options for deployment.&#x20;

#### Viewing Packages

1. Navigate to **Build → SAP Datasphere** in the project view.
2. The package list displays all packages synced from the source environment:



| Column                       | Description                                                          |
| ---------------------------- | -------------------------------------------------------------------- |
| **Name**                     | Package name.                                                        |
| **Description**              | Package description.                                                 |
| **Version**                  | The package version (e.g., 1.0.0, 2.0.0).                            |
| **Type**                     | The item type (Package).                                             |
| **User Story**               | The user story the package is assigned to, if any.                   |
| **Created On / Modified On** | When the package was created and last modified in the source tenant. |
| **Synced By / Synced On**    | Who last synchronized the package into ReleaseOwl, and when.         |



3. Use **Search by Name** to locate a package. The list is paginated; use the sort and column settings icons to adjust the view.

<figure><img src="../../.gitbook/assets/image (2250).png" alt=""><figcaption></figcaption></figure>

#### **Actions**

1. Click **Sync Packages** (top-right) to fetch the latest packages and versions from the source environment.

<figure><img src="../../.gitbook/assets/image (2254).png" alt=""><figcaption></figcaption></figure>

2. Click **Sync History** to view the log of previous synchronization runs.

<figure><img src="../../.gitbook/assets/image (2251).png" alt=""><figcaption></figcaption></figure>

3. The **⋯** menu next to each package provides:

| Action                 | Purpose                                                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **Import Settings**    | Opens the package's Import Options (overwrite preferences, deployment preferences, and the objects in the package). |
| **Versions**           | Displays the package's available versions.                                                                          |
| **Deployment History** | Displays the package's deployment log across environments.                                                          |

<figure><img src="../../.gitbook/assets/image (2253).png" alt=""><figcaption></figcaption></figure>

#### Import Settings

The Import Settings of a package control how it is imported into the target environment during deployment.

1. Click the **⋯** menu next to the required package and select **Import Settings**.

<figure><img src="../../.gitbook/assets/image (2255).png" alt=""><figcaption></figcaption></figure>

2. The Import Options page is displayed. Click **Edit** to modify the settings.

| Option                              | Description                                                                                                                           |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **Don't overwrite objects or data** | Choose this option to avoid overwriting any existing content. Only new objects are imported.                                          |
| **Overwrite data only**             | Overwrites the data of existing objects without making changes to the structure of your models.                                       |
| **Overwrite objects and data**      | Imports all selected content; existing objects can be overwritten. Selecting this option enables the **Remote Permissions** checkbox. |

<figure><img src="../../.gitbook/assets/image (2256).png" alt=""><figcaption></figcaption></figure>

**Deployment Preferences**

| Option                  | Description                                                                                                                                                            |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Deploy after import** | When enabled, the imported objects are deployed in the target tenant immediately after the import completes. When disabled, the objects are imported but not deployed. |

<figure><img src="../../.gitbook/assets/image (2257).png" alt=""><figcaption></figcaption></figure>

