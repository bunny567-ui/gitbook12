# Release Versions

It is the process of assigning unique version names or version numbers for managing multiple product releases to help in tracking the changes, features implemented, or updates done.

#### Navigating to the Release Versions Screen <a href="#pdf-page-0ebflbp2eco5zehbqqzc-navigating-to-the-release-versions-screen" id="pdf-page-0ebflbp2eco5zehbqqzc-navigating-to-the-release-versions-screen"></a>

To navigate to the **Release Versions** page:

1. In the left navigation pane, expand **Change Management**.
2. Click **Release Versions**.

<figure><img src="../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Sync Release Versions <a href="#pdf-page-0ebflbp2eco5zehbqqzc-sync-release-versions" id="pdf-page-0ebflbp2eco5zehbqqzc-sync-release-versions"></a>

If ReleaseOwl is integrated with an external ALM system, such as **Jira**, you can synchronize release versions.

To sync release versions:

1. Create a release version in Jira.
2. Assign user stories or other issue types to the release version.
3. On the **Release Versions** page in ReleaseOwl, click **Sync Release Versions**.
4. The release version created in Jira is synchronized and displayed in ReleaseOwl.

**View User Stories for a Release Version**

* Click **Actions** and select **User Stories** against any release version.

<figure><img src="../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* The user stories that are a part of the selected **Release Version** are listed as follows:

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (11).png" alt=""><figcaption></figcaption></figure>

### **Create a Release Version** <a href="#pdf-page-0ebflbp2eco5zehbqqzc-create-a-release-version" id="pdf-page-0ebflbp2eco5zehbqqzc-create-a-release-version"></a>

1. You can also create release versions in ReleaseOwl by clicking the **Create Release Version** link in the Release Versions page.
2. Enter the required details as follows:

* **Name** – Enter a unique and descriptive name for the release version.
* **Description** – Enter a brief description of the release and its purpose.
* **Planned Date** – Select the planned release date for the version.

3. Click **Create button** to create the release version.

<figure><img src="../../.gitbook/assets/image (2019).png" alt=""><figcaption></figcaption></figure>

4. Click on the **Actions** button next to the desired Release Version.

<figure><img src="../../.gitbook/assets/image (2024).png" alt=""><figcaption></figcaption></figure>

5. Following are the actions that can performed on a release version:

| **Mark as Released**        | <p>The release version status changes to <strong>Released</strong> and <strong>Release Date</strong> appears against the record.<br><strong>Note:</strong> Once the Status changes to <strong>Released, only User Stories</strong> option is available, and the rest of the options appear disabled.</p> |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cancelled**               | <p>The release version status changes to <strong>Cancelled.</strong><br><strong>Note:</strong> Once the Status changes to <strong>Cancelled, only User Stories</strong> option is available, and the rest of the options appear disabled.</p>                                                            |
| **User Stories**            | The user can **view** the **user stories** or any issue type that are a part of the selected release version.                                                                                                                                                                                            |
| **Archived**                | The selected release version gets **archived,** and the user cannot see it in the Release Versions page.                                                                                                                                                                                                 |
| **Create  Release Package** | Creates a release package for the selected release version by bundling the associated user stories and deployment artifacts. The release package can then be used for deployment through the release pipeline.                                                                                           |

<figure><img src="../../.gitbook/assets/image (2021).png" alt=""><figcaption></figcaption></figure>

### Create Release Package

Follow the steps below to create a Release Package from a Release Version:

1. Locate the Release Version for which you want to create a Release Package.
2. Click on the **Actions** button next to the desired Release Version.
3. Choose the **Create Release Package** option from the dropdown menu.

<figure><img src="../../.gitbook/assets/image (2023).png" alt=""><figcaption></figcaption></figure>

4. **Fill in the Release Package Details:**

* **Name**: Enter a meaningful name to identify the purpose or scope of the Release Package.
* **Release Pipeline**: Select the relevant Release Pipeline. This pipeline determines the stages and environments through which the package will be deployed.

5. Click the **Save** button to complete the creation process.

<figure><img src="../../.gitbook/assets/image (2022).png" alt=""><figcaption></figcaption></figure>

6. The newly created **Release Package** will now be displayed under the **Release Packages** section on the Release Versions tab.

{% hint style="info" %}
**Note:** All user stories associated with the Release Version will be automatically added to the Release Package during creation, ensuring alignment and traceability across the deployment lifecycle
{% endhint %}

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

