# BTP Applications

The **BTP Applications** module is used to manage SAP BTP applications, including support for multiple **MTA Extension (MTAEXT) files** and build tasks within Release Pipelines.

#### Create a BTP Application

1. Navigate to the **BTP Applications** section.
2. Click **New BTP Application**.

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### Application Details

1. Provide the following information:

* **Application Name**: Enter a unique name for the BTP Application.
* **Description**: Enter a brief description of the application.
* **Repository URL**: Enter the URL of the source code repository containing the application code.
* **SCM Credentials**: Click the search icon and select the appropriate source control credentials.
* **Version Control Platform**: Select the source control platform, such as **GitHub**, **GitLab**, or **Bitbucket**.
* **Change Transport Model**: Select the transport model that best matches your development workflow.
  * **Feature Branch Model**: Select this option when development activities are performed using feature or sprint branches. This model is typically used for ongoing development and sprint-based workflows.
  * **Cherry Pick Model**: Select this option when working with hotfixes. This model allows specific commits to be selectively transported and deployed without merging all changes from a branch.

2. After entering all the required details, click **Create** to create the BTP Application.

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

#### Configure Environment Branches

1. Click the **Actions** button corresponding to the BTP Application.
2. Select **Edit**.

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

3. Click the **+ Add** button.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

4. Provide the following information:

* **SAP Cloud Environment**: Select the SAP Cloud environment from the drop-down list.
* **Branch**: Enter the branch name associated with the environment.
* **Build Pipeline**: Click the search icon and select the required Build Pipeline.
* **Is Dev Branch**: Enable this option if the selected branch is the development branch.
* **MTA Extension File (.mtaext)**: Upload the MTA Extension file associated with the selected environment.
  * Click **Browse**.
  * Select the required **.mtaext** file downloaded from the repository.
  * Click **Upload File** to upload the selected MTA Extension file.

5. The uploaded MTA Extension files are displayed in the application configuration and are used during deployment and release execution for the corresponding environment.
6. Click **Add** to add the application configuration.
7. Repeat the above steps to add additional environment configurations, if required.

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

8. Click **Save** to save the BTP Application and its associated configurations.

<figure><img src="../../../.gitbook/assets/image (1972).png" alt=""><figcaption></figcaption></figure>
