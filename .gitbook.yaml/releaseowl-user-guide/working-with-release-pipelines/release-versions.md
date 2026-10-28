# Release Versions

It is the process of assigning unique version names or version numbers for managing multiple product releases to help in tracking the changes, features implemented, or updates done.

#### Navigating to the Release Versions Screen <a href="#pdf-page-0ebflbp2eco5zehbqqzc-navigating-to-the-release-versions-screen" id="pdf-page-0ebflbp2eco5zehbqqzc-navigating-to-the-release-versions-screen"></a>

To navigate to the **Release Versions** page:

1. In the left navigation pane, expand **Change Management**.
2. Click **Release Versions**.

<figure><img src="../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Sync Release Versions <a href="#pdf-page-0ebflbp2eco5zehbqqzc-sync-release-versions" id="pdf-page-0ebflbp2eco5zehbqqzc-sync-release-versions"></a>

If ReleaseOwl is integrated with an external ALM system, such as **Jira**, you can synchronize release versions.

To sync release versions:

1. Create a release version in Jira.
2. Assign user stories or other issue types to the release version.
3. On the **Release Versions** page in ReleaseOwl, click **Sync Release Versions**.
4. The release version created in Jira is synchronized and displayed in ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

**View User Stories for a Release Version**

* Click **Actions** and select **User Stories** against any release version.

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

* The user stories that are a part of the selected **Release Version** are listed as follows:

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (22).png" alt=""><figcaption></figcaption></figure>

### **Create a Release Version** <a href="#pdf-page-0ebflbp2eco5zehbqqzc-create-a-release-version" id="pdf-page-0ebflbp2eco5zehbqqzc-create-a-release-version"></a>

A **Release Version** is a record in ReleaseOwl that contains the release name, description, status, planned date, released date, and integration system. User stories are grouped under a release version based on their Fix Version. The release package and release pipeline are linked after you create a package from the release version.

1. On the **Release Versions** page, click **Create Release Version.**

<figure><img src="../../.gitbook/assets/image (2376).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/image (2372).png" alt=""><figcaption></figcaption></figure>

### Create Release Package

Follow the steps below to create a Release Package from a Release Version:

1. To create the release package, go to the **User Stories** of the release version.

<figure><img src="../../.gitbook/assets/image (2373).png" alt=""><figcaption></figcaption></figure>

2. Add or create the release package for it. Enter:
   * **Package name** – a name of your choice for the release package.
   * **Release pipeline** – the release pipeline the package follows. Both the pipeline's ID and name are required.

<figure><img src="../../.gitbook/assets/image (2374).png" alt=""><figcaption></figcaption></figure>

4. Click the **Create** button to complete the creation process.

<figure><img src="../../.gitbook/assets/image (2022).png" alt=""><figcaption></figcaption></figure>

5. Confirm to create the package. ReleaseOwl creates the release package and links it to the release version.

{% hint style="info" %}
**Note:** All user stories associated with the Release Version will be automatically added to the Release Package during creation, ensuring alignment and traceability across the deployment lifecycle
{% endhint %}

<figure><img src="../../.gitbook/assets/image (2375).png" alt=""><figcaption></figcaption></figure>
