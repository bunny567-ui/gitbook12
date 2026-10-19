# Datasphere Management

This section describes the process of configuring and managing **Datasphere Management** environments in **ReleaseOwl**.

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

<figure><img src="../../.gitbook/assets/image (2352).png" alt=""><figcaption></figcaption></figure>

#### **Actions**

1. In the left menu, navigate to **Build → SAP Datasphere**.
2. **Add Packages:** To add packages, click **Add Packages**, select the required packages, and click **Save**. ReleaseOwl retrieves the available packages from the source SDS tenant and adds the selected packages to the project.
3. **Remove Artifacts:** To remove packages, select the required packages and click **Remove Artifacts**. Confirm the action if prompted. Packages associated with user stories cannot be removed until they are unlinked from the user stories.&#x20;

<figure><img src="../../.gitbook/assets/image (2353).png" alt=""><figcaption></figcaption></figure>

4. &#x20;**Sync History:** To check the results, click **Sync History**. Review the affected package names, action, status, and error details, if any, to verify the outcome of each operation.

<figure><img src="../../.gitbook/assets/image (2354).png" alt=""><figcaption></figcaption></figure>

5. The **⋯** menu next to each package provides:

| Action                 | Purpose                                                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **Import Settings**    | Opens the package's Import Options (overwrite preferences, deployment preferences, and the objects in the package). |
| **Versions**           | Displays the package's available versions.                                                                          |
| **Deployment History** | Displays the package's deployment log across environments.                                                          |
| **Sync**               | syncs the package with your SAP Datasphere tenant to fetch its latest content and version.                          |

<figure><img src="../../.gitbook/assets/image (2355).png" alt=""><figcaption></figcaption></figure>

#### Import Settings

The Import Settings of a package control how it is imported into the target environment during deployment.

1. Click the **⋯** menu next to the required package and select **Import Settings**.

<figure><img src="../../.gitbook/assets/image (2356).png" alt=""><figcaption></figcaption></figure>

2. The Import Options page is displayed. Click **Edit** to modify the settings.

| Option                              | Description                                                                                                                           |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **Don't overwrite objects or data** | Choose this option to avoid overwriting any existing content. Only new objects are imported.                                          |
| **Overwrite data only**             | Overwrites the data of existing objects without making changes to the structure of your models.                                       |
| **Overwrite objects and data**      | Imports all selected content; existing objects can be overwritten. Selecting this option enables the **Remote Permissions** checkbox. |

<figure><img src="../../.gitbook/assets/image (2357).png" alt=""><figcaption></figcaption></figure>

**Deployment Preferences**

| Option                  | Description                                                                                                                                                            |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Deploy after import** | When enabled, the imported objects are deployed in the target tenant immediately after the import completes. When disabled, the objects are imported but not deployed. |

<figure><img src="../../.gitbook/assets/image (2358).png" alt=""><figcaption></figcaption></figure>

**Configure the Environment**

* Click the **Environment** list to view **All** and the individual environments configured for the project.
* Select **All** to apply the same settings to every environment, or select an individual environment to configure its settings separately.&#x20;
* Each environment maintains its own settings, so changes to one environment do not affect the others.

<figure><img src="../../.gitbook/assets/image (2359).png" alt=""><figcaption></figcaption></figure>
