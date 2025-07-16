# gCTS Merge

**gCTS Merge Configurations**

This feature allows you to define merge configurations between two Git-enabled SAP systems using gCTS (Git-enabled Change and Transport System). It helps in synchronizing and merging branches across different systems within your transport landscape.

To create a merge configuration, the following fields are used:

* **Name**: A unique name for the merge configuration.

**Source Configuration**:

* **GCTS Environment**: Select the source environment from the dropdown.
* **Domain Controller**: Automatically populated based on the selected environment.
* **System ID**: Automatically populated based on the environment.
* **GCTS Repo**: Select the source repository.
* **Branch**: Choose the source branch to be compared or merged.

**Target Configuration**:

* **GCTS Environment**: Select the target environment from the dropdown.
* **Domain Controller**: Automatically populated based on the selected environment.
* **System ID**: Automatically populated based on the environment.
* **GCTS Repo**: Automatically populated based on the source repository selection.
* **Branch**: Choose the target branch into which changes will be merged.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Once all required fields are filled, click **Save**. A success message will be displayed confirming that the configuration has been created successfully..

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Executing the Merge**

To initiate the merge process:

1. Click on the **Actions** button (`...`) next to the desired merge configuration.
2. Select **Start Merge** to begin the merge process based on the defined configuration.

<figure><img src="../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Viewing Merge Configuration Details**

By clicking into an existing merge configuration, you can view the following details:

* **Source System ID**
* **Target System ID**
* **Source Branch**
* **Target Branch**
* **Created By**
* **Created On**
* **Merge Status**

<figure><img src="../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Viewing Merged Files**

To inspect the files involved in the merge:

1. Click on the **Actions** button (`...`) for the configuration.
2. Select **View Files**.

<figure><img src="../../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. This will redirect you to the corresponding **GitHub** repository, where you can review the status of the merged files.

<figure><img src="../../.gitbook/assets/image (7) (1) (1).png" alt=""><figcaption></figcaption></figure>
