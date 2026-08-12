# BTP Applications

The **BTP Applications** module is used to manage SAP BTP applications, including support for multiple **MTA Extension (MTAEXT) files** and build tasks within Release Pipelines.

#### Create a BTP Application

1. Navigate to the **BTP Applications** section.
2. Click **New BTP Application**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Application Details

| Field                               | Type          | Description                                                                                                                                                                                       |
| ----------------------------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Application Name                    | Text          | Unique name of the application. Read-only after creation.                                                                                                                                         |
| Description                         | Text          | Optional free-text description.                                                                                                                                                                   |
| Version Control System              | Dropdown      | The Git provider: Bitbucket, GitHub, Azure DevOps, or GitLab.                                                                                                                                     |
| Repository URL                      | Text          | URL of the application’s Git repository.                                                                                                                                                          |
| SCM Credentials                     | Picker        | The Git credential registered in Administration (§2.1).                                                                                                                                           |
| Branching Model                     | Dropdown      | Feature Branch Model or Cherry-Pick Model. Mutually exclusive and read-only after creation.                                                                                                       |
| Create Feature Branch From Branch   | Text          | The default base branch from which feature/hotfix branches are created as part of the branching strategy. This value pre-fills (and can be overridden) when a branch is created for a user story. |
| Build Pipeline for Dynamic Branches | Picker + info | The build pipeline used to build dynamic branches — e.g. hotfix branches and staging branches — that are created on the fly and do not have a fixed per-environment pipeline.                     |

* After entering all the required details, click **Create** to create the BTP Application.

<figure><img src="../../../.gitbook/assets/image (2121).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Both Application Name and Branching Model can only be set at creation time; they are greyed out (read-only) when editing an existing application.
{% endhint %}

#### Configure Environment Branches

1. Click the **Actions** button corresponding to the BTP Application.
2. Select **Edit**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. **Landscape Configuration**: The Landscape Configuration defines, for each SAP Cloud environment, which Git branch it maps to, which Build Pipeline builds it, and which MTA extension files apply. Add one row per environment (Development, QA, Production,...).
4. Click the **+ Add** button.

<figure><img src="../../../.gitbook/assets/image (2122).png" alt=""><figcaption></figcaption></figure>

**Landscape Fields:**

| Field                        | Type     | Description                                                                                                                                                                   |
| ---------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SAP Cloud Environment        | Dropdown | The target environment for this row.                                                                                                                                          |
| Build Pipeline               | Picker   | The build pipeline that builds this environment’s branch.                                                                                                                     |
| Branch                       | Text     | The Git branch mapped to this environment (e.g. dev, qa, main).                                                                                                               |
| Development Branch           | Checkbox | Marks this environment’s branch as the development branch. In the Cherry-Pick model, this is the branch from which commits are populated when adding changes to a user story. |
| MTA Extension File (.mtaext) | Upload   | Environment-specific MTA extension file(s). Use Browse… then Upload File; uploaded files appear in the list below and are applied at deployment time for this environment.    |

<figure><img src="../../../.gitbook/assets/image (2124).png" alt=""><figcaption></figcaption></figure>

5. Click **Save** to add the application configuration.

<figure><img src="../../../.gitbook/assets/image (1972).png" alt=""><figcaption></figcaption></figure>

#### **Landscape configuration - CherryPick Model**

For applications using the **Cherry Pick Model**, designate one environment branch as the **Development Branch**.

**Is Dev Branch:** Enable the **Is Dev Branch** option for the environment branch that serves as the Development Branch.

When a Development Branch is configured:

* ReleaseOwl retrieves the available commits from the Development Branch.
* During User Story creation, users can select the required commits and associate them with the User Story.
* Only the selected commits are included in the build and promoted through the release pipeline.



<figure><img src="../../../.gitbook/assets/image (2125).png" alt=""><figcaption></figcaption></figure>
