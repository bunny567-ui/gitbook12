# BTP Applications

The **BTP Applications** module is used to manage SAP BTP applications, including support for multiple **MTA Extension (MTAEXT) files** and build tasks within Release Pipelines.

#### Create a BTP Application

1. Navigate to the **BTP Applications** section.
2. Click **New BTP Application**.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Application Details

1. Provide the following information:

* **Application Name**: Enter the name of the MTAR application.
* **Description**: Enter a brief description of the application.
* **Version Control System**: Select the version control system used to manage the application's source code.
* **Repository URL** : Enter the URL of the source code repository.

{% hint style="info" %}
**Note :** After the MTAR application is registered, the **Repository URL** cannot be modified.
{% endhint %}

* **SCM Credentials** : Select the credentials used to authenticate with the source code repository.
* **Branching Model :**  Select the branching strategy for the MTAR application.

{% hint style="info" %}
**Note :** After the MTAR application is registered, the **Branching Model** cannot be modified.
{% endhint %}

**Feature Branch Model-** When **Feature Branch Model** is selected:

* The **Create Feature Branch From Branch** field is mandatory.
* Select the base branch from which ReleaseOwl creates feature branches.
* During User Story creation, a feature branch must be associated with the MTAR application.
* All development, build, and deployment activities for the User Story use the associated feature branch.

**Cherry Pick Model-** When **Cherry Pick Model** is selected:

* The **Create Feature Branch From Branch** field is optional.
* Configure the development branch for the application.
* During User Story creation, select the required commits from the development branch and associate them with the User Story.
* Only the selected commits are included in the build and promoted through the release pipeline.
* **Build Pipeline for Dynamic Branches**  : Select the Build Pipeline to be used for **Feature Branches** and other dynamically created branches.
* **Build Pipeline for Package / Hot Fix Branches**  : Select the Build Pipeline to be used for **Package** and **Hot Fix** branches.

2. After entering all the required details, click **Create** to create the BTP Application.

<figure><img src="../../.gitbook/assets/image (2121).png" alt=""><figcaption></figcaption></figure>

#### Configure Environment Branches

1. Click the **Actions** button corresponding to the BTP Application.
2. Select **Edit**.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Click the **+ Add** button.

<figure><img src="../../.gitbook/assets/image (2122).png" alt=""><figcaption></figcaption></figure>

4. Provide the following information:

* **SAP Cloud Environment**: Select the SAP Cloud environment from the drop-down list.
* **Branch**: Enter the branch name associated with the environment.
* **Build Pipeline**: Click the search icon and select the required Build Pipeline.
* **MTA Extension File (.mtaext)**: Upload the MTA Extension file associated with the selected environment.
  * Click **Browse**.
  * Select the required **.mtaext** file downloaded from the repository.
  * Click **Upload File** to add the selected MTA Extension file.

5. The uploaded MTA Extension files are displayed in the application configuration and are used during deployment and release execution for the corresponding environment.

<figure><img src="../../.gitbook/assets/image (2124).png" alt=""><figcaption></figcaption></figure>

5. Click **Save** to add the application configuration.
6. Repeat the above steps to add additional environment configurations, if required.
7. Click **Save** to save the BTP Application and its associated configurations.

<figure><img src="../../.gitbook/assets/image (1972).png" alt=""><figcaption></figcaption></figure>

#### **Landscape configuration - CherryPick Model**

For applications using the **Cherry Pick Model**, designate one environment branch as the **Development Branch**.

**Is Dev Branch:** Enable the **Is Dev Branch** option for the environment branch that serves as the Development Branch.

When a Development Branch is configured:

* ReleaseOwl retrieves the available commits from the Development Branch.
* During User Story creation, users can select the required commits and associate them with the User Story.
* Only the selected commits are included in the build and promoted through the release pipeline.



<figure><img src="../../.gitbook/assets/image (2125).png" alt=""><figcaption></figcaption></figure>
