# Synchronize CPI Artifacts

### **Prerequisites**

1. Begin by registering your SAP BTP credentials and the corresponding SAP Integration Suite environment within ReleaseOwl.
2.  Navigate to the **Projects** section and create a new project.

    * **Project Type**: Select **SAP CPI**.

    <figure><img src="../../../.gitbook/assets/image (1052).png" alt=""><figcaption></figcaption></figure>
3. Once the project is created, add the registered environments to the project via **Project Settings > Environment**.

<figure><img src="../../../.gitbook/assets/image (1053).png" alt=""><figcaption></figcaption></figure>

4. Click **Sync All Artifacts** to fetch and display the available CPI artifacts within the selected project.
5. Navigate to **Build > SAP CPI Management** and click on the **actions** button to view **Sync Artifacts**.

<figure><img src="../../../.gitbook/assets/image (1054).png" alt=""><figcaption></figcaption></figure>

### **Synchronize Integration Suite Artifacts**

6. Click **Sync  Artifacts** to fetch various artifacts like IFlows, Value Maps, Packages, Configuration parameters, etc. from the registered SAP CPI environment into ReleaseOwl.
7. If there are changes made to the existing artifacts, the changes will also be updated.
8. Click **Sync Artifacts** to sync the CPI artifacts.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Sync History**

With this, you can view the history of all the artifact syncs that have occurred. Click **Sync History**, to view the CPI sync history of this project.

<figure><img src="../../../.gitbook/assets/image (1055).png" alt=""><figcaption></figcaption></figure>

### **Sort**

You can sort the artifacts as per your convenience. To sort them:

1. Click the **Sort icon**.
2.  In the page displayed, choose an option and click **OK**.\


    <figure><img src="../../../.gitbook/assets/image (1056).png" alt=""><figcaption></figcaption></figure>

### **Actions**

Multiple actions can be performed on an artifact, based on the type of artifact. These actions include – View Test Cases, Comment , Configure, Deployment History, Versions and Download.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Manage Environment Wide IFlow Configurations**

You can maintain configuration parameters for IFlows for each environment separately in ReleaseOwl. These will be updated accordingly during the deployment.

#### **To configure an artifact:**

1\. Go to the required artifact, click **Actions** and choose **Configure**.

2\. The following screen is displayed that will show various configuration parameters for the Integration Suite environments that are part of the landscape.

3\. No changes can be made to **Dev** environment.

4\. To make changes in any other environment, click the edit icon on the required name and make changes. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (1059).png" alt=""><figcaption></figcaption></figure>

### **Artifact Versions**

1\. To view the versions, go to the required artifact, click **Actions** and choose **Versions**.

<figure><img src="../../../.gitbook/assets/image (1060).png" alt=""><figcaption></figcaption></figure>

2. &#x20;The following screen is displayed showing the user different versions of the artifact.

<figure><img src="../../../.gitbook/assets/image (1061).png" alt=""><figcaption></figcaption></figure>

3. **Assign User Story** option is used to link a specific version of an artifact (such as a configuration or integration flow) to a designated User Story.
4. On clicking **Assign User Story**, the system will prompt you to:

* Select a User Story from a searchable button.&#x20;
* Associate the current version of the artifact with the selected User Story, establishing a traceable link between the artifact version and the development requirement.

<figure><img src="../../../.gitbook/assets/image (1062).png" alt=""><figcaption></figcaption></figure>



5. Click **Actions and** choose either **Download** or **Where Used List** based on the requirement.

<figure><img src="../../../.gitbook/assets/image (1063).png" alt=""><figcaption></figcaption></figure>
