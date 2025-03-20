# Synchronize CPI Artifacts

**Prerequisites**

1. Register SAP BTP Credentials and SAP Integration Suite Environment with ReleaseOwl.
2. Create a new project of type SAP CPI.
3. Add the environments to the project.
4. Click Sync All Artifacts to view the list of CPI artifacts available in the project, and a set of associated actions that can be performed as shown below under **Build > SAP CPI Management**. The screen displays a list of CPI artifacts available in the project, and a set of associated actions that can be performed as shown below:\


<figure><img src="https://www.docs.releaseowl.com/assets/img/synchronize-cpi-artifacts-1.jpg" alt=""><figcaption></figcaption></figure>

**Synchronize Integration Suite Artifacts**

Click Sync All Artifacts to fetch various artifacts like IFlows, Value Maps, Packages, Configuration parameters etc. from the registered SAP CPI environment into ReleaseOwl. If there are changes made to the existing artifacts, the changes will also be updated.

Click **Sync Artifacts** to sync the CPI artifacts.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/synchronize-cpi-artifacts-2.jpg" alt=""><figcaption></figcaption></figure>

**Sync History**

With this, you can view the history of all the artifact syncs that have occurred. Click Sync History, to view the CPI sync history of this project.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/synchronize-cpi-artifacts-3.jpg" alt=""><figcaption></figcaption></figure>

**Assign User Story**

To assign a user story:

1. Select an artifact.
2. Click **Assign User story**, and from the dropdown choose one or more user stories that you want to assign to the chosen artifact.

<figure><img src="https://www.docs.releaseowl.com/assets/img/synchronize-cpi-artifacts-4.jpg" alt=""><figcaption></figcaption></figure>

**Sort**

You can sort the artifacts as per your convenience. To sort them:

1. Click the Sort icon.
2. In the page displayed, choose an option and click **OK**.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/synchronize-cpi-artifacts-5.jpg" alt=""><figcaption></figcaption></figure>

**Actions**

Multiple actions can be performed on an artifact, based on the type of artifact. These actions include – Configure, Versions and Download.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/synchronize-cpi-artifacts-6.jpg" alt=""><figcaption></figcaption></figure>

**Manage Environment Wide IFlow Configurations**

You can maintain configuration parameters for IFlows for each environment separately in ReleaseOwl. These will be updated accordingly during the deployment.

To configure an artifact:

1\. Go to the required artifact, click **Actions** and choose **Configure**.

2\. The following screen is displayed that will show various configuration parameters for the Integration Suite environments that are part of the landscape.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/synchronize-cpi-artifacts-7.jpg" alt=""><figcaption></figcaption></figure>

3\. No changes can be made to Dev environment.

4\. To make changes in any other environment, click the edit icon on the required name and make changes. Click **Save**.

### **Artifact Versions**

All the versions of a chosen artifact can be viewed. To view the versions:

1\. To view the versions, go to the required artifact, click **Actions** and choose **Versions**.

2\. The following screen is displayed showing the user different versions of the artifact.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/synchronize-cpi-artifacts-8.jpg" alt=""><figcaption></figcaption></figure>

3\. Click **Actions and** choose either **Download** or **Configure** based on the requirement.
