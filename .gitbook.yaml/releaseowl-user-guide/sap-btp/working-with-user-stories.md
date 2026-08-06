# Working with User stories

User Stories support the association of one or more MTAR applications. All build, deployment, and release activities for an MTAR application are initiated from the associated User Story.

### Add MTAR Applications

To associate MTAR applications with a User Story:

1. Navigate to **Change Management** and click **User Stories**.
2. Click **Create New User Story**.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

2. Enter the required details and click **Create**.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

3. Click **Actions**, and then click **Edit**.
4. In the **MTAR Applications** section, click **Add**.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

**Step 1: MTAR Applications**

The **MTAR Applications** step displays all registered MTAR applications.

1. Select the required MTAR application.
2. Review the application details, including:
   * **Application Name**
   * **Description**
   * **Repository URL**
   * **Branching Model**
3. Click **Next**.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

**Step 2: Source Reference**

The **Source Reference** step varies depending on the branching model configured for the selected MTAR application.

1. Select one of the following options:

* **Create Feature Branch** – Creates a new feature branch for the User Story.
* **I Already Have a Feature Branch** – Uses an existing feature branch.

2. If **Create Feature Branch** is selected:

* **Feature Branch:** Enter the name of the feature branch.
* **From Branch:** Select the base branch from which the feature branch will be created.

3. Click **Create Branch**, and then click **Finish**.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

4. If **I Already Have a Feature Branch** is selected, Enter  the existing feature branch and click **Finish**.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

**Cherry Pick Model**

* If the selected MTAR application uses the **Cherry Pick Model**, the **Source Reference** step displays the commits available in the configured **Development Branch.**
* Select the required commits and click **Finish**. Only the selected commits are associated with the User Story and promoted through the release pipeline.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

#### Edit Feature Branch / Commits

You can edit the **Feature Branch** or the selected **commits** after an MTAR application has been added to the User Story.

To edit the source reference:

1. In the **MTAR Applications** section, click the **Actions** button corresponding to the required MTAR application.
2. Click **Edit Feature Branch**.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

3. Update the **Feature Branch** (for the **Feature Branch Model**) or modify the selected **commits** (for the **Cherry Pick Model**).

<div><figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure></div>

4. Click **Save** /**Add** to apply the changes.

### User Story Actions

The following actions are available on the User Story toolbar:

* **Validate** – Validates the User Story against the configured target environment and displays a **Validation Report** containing the validation results and any identified issues.
* **Promote** – Promotes the User Story to the next stage in the release pipeline.
* **Save** – Saves the changes made to the User Story. Ensure that you click **Save** before clicking **Promote**.
* **Refresh** – Refreshes the User Story and reloads the latest information.

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

* **Activity Log**- Click **Activity Log** to view the complete history of actions performed on the User Story.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

* **Release Package Details**: Click **Release Package Details** to view the release package information associated with the User Story.&#x20;
* **Export User Story** : Click **Export User Story** to export the User Story details.&#x20;

<figure><img src="../../.gitbook/assets/image (2127).png" alt=""><figcaption></figcaption></figure>

#### MTAR - Deployment Task&#x20;

**Promote** –  Click **Promote** to start the deployment process.

* If the [Release Pipeline ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/working-with-release-pipelines/use-cases/automated-mtar-deployments)includes a **Deployment** task, monitor the deployment status of the User Story.
* Click **Deploy Logs** to view the deployment details.

<div><figure><img src="../../.gitbook/assets/image (2128).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (2129).png" alt=""><figcaption></figcaption></figure></div>
