# B2B Scenarios

The Trading Partner Management (TPM) module in Releaseowl lets you synchronize, manage, version, and deploy SAP TPM artifacts across your SAP Integration Suite environments.

Releaseowl integrates with SAP Trading Partner Management to manage the deployment lifecycle of TPM artifacts. Using this module, you can synchronize the  exported Agreements and Partner Directory artifacts from a source environment, organize them into User Stories, and promote them through your Release Pipelines

## &#x20;B2B Scenarios&#x20;

Open **B2B Scenarios** within the CPI project. This screen has **three tabs**:

1. **Agreements**
2. **Partner Directory**
3. **Partner Directory Configuration**

<figure><img src="../../.gitbook/assets/image (2057).png" alt=""><figcaption></figcaption></figure>

### **1. Agreements**

This tab is used to import agreements exported from the **B2B Scenarios** application in SAP Integration Suite, allowing you to view and manage them  in ReleaseOwl.

&#x20;**Adding an Agreement**

* Click **Add Artifacts**.
* The dialog displays all agreement artifacts that have been exported from the **B2B Scenarios** application in SAP Integration Suite and are available for import.
* Select the required agreement(s) and add them to ReleaseOwl for deployment.

<figure><img src="../../.gitbook/assets/image (2058).png" alt=""><figcaption></figcaption></figure>

* Once an agreement is added, use the action options to view its details, download the artifact, and check its deployment history.

| Action                 | What it does                                                                                                |
| ---------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Details**            | Displays the details of the selected exported agreement.                                                    |
| **Download**           | Downloads the exported agreement artifact to your local machine.                                            |
| **Deployment History** | Shows the history of deployments carried out for that agreement — which environment, when, and the outcome. |



<figure><img src="../../.gitbook/assets/image (2059).png" alt=""><figcaption></figcaption></figure>

### 2. Partner Directory Data

Use this tab to view the Partner Directory data associated with Trading Partner Management (TPM).

* Click **Sync Artifacts** to synchronize Partner Directory data from the **B2B Scenarios** application in SAP Integration Suite into ReleaseOwl. Use **Search by ID** to quickly locate a specific Partner Directory ID.

<figure><img src="../../.gitbook/assets/image (2060).png" alt=""><figcaption></figcaption></figure>

* Click the **Expand** (arrow) icon to view the details of a Partner Directory entry, including the **Parameter ID**, **Value**, **Type**, and **Content Type**.
* Parameter ID entries can be of type **String** or **Binary**.
* For Parameter ID entries of type **Binary**, you can download the associated binary content.

<figure><img src="../../.gitbook/assets/image (2061).png" alt=""><figcaption></figcaption></figure>

### 3.  Partner Directory Configuration&#x20;

This is the Releaseowl-only artifact used to **group specific Partner Directory attributes together** so they can be versioned and deployed as a single unit — instead of moving every attribute one at a time.

**Create a configuration**

1. Go to the **Partner Directory Configuration** tab.

<figure><img src="../../.gitbook/assets/image (2062).png" alt=""><figcaption></figcaption></figure>

2. Click **Create Partner Directory Configuration**.
3. In the pop-up, enter:
   * **Artifact Name**
   * **Version**
4. Click **Create**. Your new configuration now appears in the configuration list.

<figure><img src="../../.gitbook/assets/image (2063).png" alt=""><figcaption></figcaption></figure>

5. Click the **Actions** button on your configuration, then choose **Edit**.

<figure><img src="../../.gitbook/assets/image (2064).png" alt=""><figcaption></figcaption></figure>

6. Click **Add**, and select the Partner Directory data (attributes/IDs) you want included.
7. Click **Save**.

<figure><img src="../../.gitbook/assets/image (2065).png" alt=""><figcaption></figcaption></figure>

8. After adding the Partner Directory entries, you can choose one of the following options:
   * **Save** – Saves the changes to the current Partner Directory Configuration.
   * **Save as Version** – Creates a new version of the Partner Directory Configuration while preserving the existing version.

<figure><img src="../../.gitbook/assets/image (2066).png" alt=""><figcaption></figcaption></figure>

**Configure:**

* To change the value of a parameter on an attribute you've already added, open the **Configure** button for that Partner Directory ID.

<figure><img src="../../.gitbook/assets/image (2067).png" alt=""><figcaption></figcaption></figure>

* Click the **Edit** (pencil) icon next to the required field.
* Update the necessary configuration parameters.
* Click **Save** to persist changes.

<figure><img src="../../.gitbook/assets/image (2068).png" alt=""><figcaption></figcaption></figure>

**Deployment History**&#x20;

* **Deployment History** : Displays the deployment history of the Partner Directory Configuration.

<figure><img src="../../.gitbook/assets/image (2069).png" alt=""><figcaption></figcaption></figure>

* **Versions** lists every version created for the configuration. From here, you can **assign a specific version to a User Story** for deployment.

<figure><img src="../../.gitbook/assets/image (2070).png" alt=""><figcaption></figcaption></figure>



