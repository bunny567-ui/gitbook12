# Creation of Transports

### **Transport Management**

Transport management is used to model your change management across the landscape.

#### **Create New Transport Request**

To create a new transport request, follow these steps:

1. Click **"Create New Transport Request".**

<figure><img src="../../.gitbook/assets/image (1289).png" alt=""><figcaption></figcaption></figure>

2. **Fill in the Required Details**

* A new window will appear where you need to enter the transport details:

| Field                   | Description                                                                                                       |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Description**         | Provide a description to the transport request.                                                                   |
| **Type**                | Select the type of transport request from the dropdown.                                                           |
| **Owner**               | SAP user with permissions to create and import transports.                                                        |
| **Dev System**          | Select the development system.                                                                                    |
| **Target System**       | The system where the transport will be imported post-release. This is auto-populated but can be modified.         |
| **User Story**          | Select the relevant development system.                                                                           |
| **Notification Emails** | Enter email addresses of people to be notified about the transport request. Separate multiple emails with commas. |
| **Tasks**               | A sub-request that is part of the transport request. Tasks can be assigned to different users.                    |

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. **Save and View the Transport**

* Once created, the transport request will appear on the **Transport Management** homepage.

<figure><img src="../../.gitbook/assets/image (487).png" alt=""><figcaption></figcaption></figure>

#### **Import Settings**

This section allows you to configure how transport requests should be imported into specific environments. To define import settings, click on the **+ Add** button and select the target **environment** (e.g., `DEM.100`). You can then enable or disable specific options such as delayed import, overwrite originals, ignore repairs, and more, based on your project requirements.

<figure><img src="../../.gitbook/assets/image (1121).png" alt=""><figcaption></figcaption></figure>

### **Sync Transports**

Syncing transports ensures the latest transport requests are fetched from the **source environment of the SAP landscape** to **ReleaseOwl**. If any modifications have been made to existing transports, those changes will also be updated.

#### **Steps to Sync Transports:**

1. Click the **Sync Transports** icon at the top right of the page.
2. The latest transport requests will be synchronized.

<figure><img src="../../.gitbook/assets/image (1114).png" alt=""><figcaption></figcaption></figure>

#### Current Project Transports

There may be multiple transports listed in the Transport Management section. To work on a specific transport in your current project, click on the **Action** button next to the transport and select **Add to Project**. &#x20;

<figure><img src="../../.gitbook/assets/image (1115).png" alt=""><figcaption></figcaption></figure>

Then, check the **Current Project Transports** section, where the selected transport will be listed.

<figure><img src="../../.gitbook/assets/image (1116).png" alt=""><figcaption></figcaption></figure>

### Edit Transports

To edit an existing transport request:

1. Select the required transport and click **Actions**.
2. Choose **Edit**.

<figure><img src="../../.gitbook/assets/image (1118).png" alt=""><figcaption></figcaption></figure>

3. Click **Load Objects** to fetch the list of objects included in the transport.&#x20;
4. Click **Save** to apply the changes.

<figure><img src="../../.gitbook/assets/image (1117).png" alt=""><figcaption></figcaption></figure>

### **Manage Critical Objects**

Critical objects require **mandatory review** before they can be deployed. These objects can be managed under the **Critical Objects** section with the following options:

* **Active** → If marked active, approvals are required before deploying to the target system.
* **Whitelist** → If both **Active** and **Whitelist** are selected, the transport can be imported without additional approvals.

#### **Steps to Manage Critical Objects:**

1. Click **Manage Critical Objects**.

<figure><img src="../../.gitbook/assets/image (495).png" alt=""><figcaption></figcaption></figure>

2. A list of critical objects that require pre-approvals for release will be displayed.
3. Click **Add Critical Object**.

<figure><img src="../../.gitbook/assets/image (492).png" alt=""><figcaption></figcaption></figure>

4. Enter the necessary details and click **Save**.

<figure><img src="../../.gitbook/assets/image (493).png" alt=""><figcaption></figcaption></figure>

5. The newly added critical object will appear in the **Manage Critical Objects** section.

<figure><img src="../../.gitbook/assets/image (494).png" alt=""><figcaption></figcaption></figure>

### Export Transport Data to Excel

You can download the transport data in Excel format by clicking the **Excel Download button** in the top-right corner of the **Transport Management** section. This action will export the list of transports as an Excel file.

<figure><img src="../../.gitbook/assets/image (1119).png" alt=""><figcaption></figcaption></figure>

**External Transports**

External transports are transport requests that are created or imported manually into the SAP system. ReleaseOwl  marks these external transports with a ✓ (check mark) under the '**External**' column.

{% hint style="info" %}
**Note:** To create an external transport for a user, the **Manage External Transport** role must be assigned.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
