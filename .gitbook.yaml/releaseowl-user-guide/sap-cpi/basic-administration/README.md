# Basic Administration

**Registering Credential for SAP BTP**

To register credential for SAP BTP (SAP Integration Suite):

1. In Configuration, go to Credential Manager.
2. In page displayed, click Register Credential.
3. The following screen is displayed:

<figure><img src="https://www.docs.releaseowl.com/assets/img/basic-administration-1.jpg" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Scope**           | This is auto- populated                                  |
| ------------------- | -------------------------------------------------------- |
| **Credential Type** | Choose SAP Cloud Environment from the drop down          |
| **Credential Name** | Enter a Credential Name for your reference in ReleaseOwl |
| **User Name**       | Enter your username of SAP BTP account                   |
| **Password**        | Enter your password of SAP BTP account                   |

Click **Save** to register the credential.

To **Delete** a credential, go the required credential and click on the delete icon.

**Registering SAP Integration Suite Environment**

To register **SAP CPI Environment:**

1\. In Environments, go to SAP CPI Environment.

2\. A list of registered CPI environments is displayed in this page.

3\. Click Register SAP CPI Environment.

4\. The following page is displayed.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/basic-administration-2.jpg" alt=""><figcaption></figcaption></figure>

5\. Fill in the required details:

| **Name**            | Enter a name for your reference                          |
| ------------------- | -------------------------------------------------------- |
| **Credential Name** | Choose a credential from the drop down                   |
| **Host URL**        | Enter the host URL of the Integration Suite environment. |

6\. Click Save to register the environment. The registered environments are displayed.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/basic-administration-3.jpg" alt=""><figcaption></figcaption></figure>

7\. Click on the required environment to view the details.

8\. Click the edit icon to edit the registered CPI Environment.

9\. Click the delete icon to delete the required environment.

**Adding Integration Suite Environments to the Project**

For artifacts to load in SAP CPI Management page, the Integration Suite environments must be registered in Project Settings in ReleaseOwl.

To register SAP Integration Suite environment:

1\. Go to Projects drop down at the top right corner and click Project Settings.

2\. In Project Settings, go to Environment.

3\. The following screen is displayed.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/basic-administration-4.jpg" alt=""><figcaption></figcaption></figure>

4\. Click Add Environment to add a new environment in ReleaseOwl.

5\. In the subsequent screen, choose the required environment from the list displayed by selecting Source. Only the artifacts with source are synced to ReleaseOwl.

6\. The environment is added to the corresponding project in ReleaseOwl.

7\. Click Permissions (under Users tab in Project Settings), to add users that can access (read or deploy to) the registered CPI environment.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/basic-administration-5.jpg" alt=""><figcaption></figcaption></figure>

Click Permissions. The roles that are assigned to the selected user are seen.

<figure><img src="https://www.docs.releaseowl.com/assets/img/basic-administration-6.jpg" alt=""><figcaption></figcaption></figure>

On clicking Permissions in the above screen, one can know the actions that the user role can perform each for the available features such as Transport Management, Change Management, Pipelines, Release Management.
