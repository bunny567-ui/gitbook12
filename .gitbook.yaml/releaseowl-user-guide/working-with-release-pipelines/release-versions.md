# Release Versions

It is the process of assigning unique version names or version numbers for managing multiple product releases to help in tracking the changes, features implemented, or updates done.

### Navigating to the Release Versions Screen <a href="#pdf-page-0ebflbp2eco5zehbqqzc-navigating-to-the-release-versions-screen" id="pdf-page-0ebflbp2eco5zehbqqzc-navigating-to-the-release-versions-screen"></a>

* To navigate to the Release Versions screen, click **Release Versions** under the **Change Management** section.
* The Release Versions screen looks as follows:

<figure><img src="../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Sync Release Versions <a href="#pdf-page-0ebflbp2eco5zehbqqzc-sync-release-versions" id="pdf-page-0ebflbp2eco5zehbqqzc-sync-release-versions"></a>

* You can sync the Release Versions from the integrated external ALM system, such as JIRA.
* Create a Version in JIRA and assign user stories or any issue type to it.
* Sync the release versions by clicking **Sync Release Versions** from the Release Versions page.
* The release version created in JIRA can now be seen in ReleaseOwl.
* Click **Actions** and select **User Stories** against any release version:

### **View User Stories for a Release Version** <a href="#pdf-page-0ebflbp2eco5zehbqqzc-view-user-stories-for-a-release-version" id="pdf-page-0ebflbp2eco5zehbqqzc-view-user-stories-for-a-release-version"></a>

* Click **Actions** and select **User Stories** against any release version:

<figure><img src="../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* The user stories that are a part of the selected **Release Version** are listed as follows:

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Create a Release Version** <a href="#pdf-page-0ebflbp2eco5zehbqqzc-create-a-release-version" id="pdf-page-0ebflbp2eco5zehbqqzc-create-a-release-version"></a>

* You can also create release versions in ReleaseOwl by clicking the **Create Release Version** link in the Release Versions page.
* Enter the required details as follows:

<figure><img src="../../.gitbook/assets/image (12) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Following are the actions that can performed on a release version:

<figure><img src="../../.gitbook/assets/image (13) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

| **Mark as Released** | <p>The release version status changes to <strong>Released</strong> and <strong>Release Date</strong> appears against the record.<br><strong>Note:</strong> Once the Status changes to <strong>Released, only User Stories</strong> option is available, and the rest of the options appear disabled.</p> |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cancelled**        | <p>The release version status changes to <strong>Cancelled.</strong><br><strong>Note:</strong> Once the Status changes to <strong>Cancelled, only User Stories</strong> option is available, and the rest of the options appear disabled.</p>                                                            |
| **User Stories**     | The user can **view** the **user stories** or any issue type that are a part of the selected release version.                                                                                                                                                                                            |
| **Archived**         | The selected release version gets **archived,** and the user cannot see it in the Release Versions page.                                                                                                                                                                                                 |

### Create Release Package

Follow the steps below to create a Release Package from a Release Version:

1. Locate the Release Version for which you want to create a Release Package.
2. Click on the **Actions** button next to the desired Release Version.
3. Choose the **Create Release Package** option from the dropdown menu.
4. **Fill in the Release Package Details:**
   * **Name**: Enter a meaningful name to identify the purpose or scope of the Release Package.
   * **Release Pipeline**: Select the relevant Release Pipeline. This pipeline determines the stages and environments through which the package will be deployed.
5. Click the **Save** button to complete the creation process.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

6. The newly created **Release Package** will now be displayed under the **Release Packages** section on the Release Versions tab.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** All user stories associated with the Release Version will be automatically added to the Release Package during creation, ensuring alignment and traceability across the deployment lifecycle
{% endhint %}

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

