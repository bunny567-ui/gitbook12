# Creation of Transports

### **Transport Management**

Transport management is used to model your change management across the landscape.

### **Creating a New Transport**

To create a new transport request, follow these steps:

1. **Select Your Project**
   * Choose the project from the dropdown menu.
   * This populates the transport requests associated with the project.
2. **Click "Create New Transport Request"**

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

3. **Fill in the Required Details**

* A new window will appear where you need to enter the transport details:

| Field                   | Description                                                                                                       |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Name**                | Provide a name for the transport request.                                                                         |
| **Description**         | Optionally add a description.                                                                                     |
| **Type**                | Select the type of transport request from the dropdown.                                                           |
| **Owner**               | SAP user with permissions to create and import transports.                                                        |
| **Dev System**          | Select the development system.                                                                                    |
| **Target System**       | The system where the transport will be imported post-release. This is auto-populated but can be modified.         |
| **User Story**          | Select the relevant development system.                                                                           |
| **Notification Emails** | Enter email addresses of people to be notified about the transport request. Separate multiple emails with commas. |
| **Tasks**               | A sub-request that is part of the transport request. Tasks can be assigned to different users.                    |

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

5. **Save and View the Transport**

* Once created, the transport request will appear on the **Transport Management** homepage.

<figure><img src="../../.gitbook/assets/image (487).png" alt=""><figcaption></figcaption></figure>

### **Sync Transports**

Syncing transports ensures the latest transport requests are fetched from the **source environment of the SAP landscape** to **ReleaseOwl**. If any modifications have been made to existing transports, those changes will also be updated.

#### **Steps to Sync Transports:**

1. Click the **Sync Transports** icon at the top right of the page.
2. The latest transport requests will be synchronized.

### **Editing a Transport**

To edit an existing transport request:

1. Select the required transport and click **Actions**.
2. Choose **Edit**.
3. In the edit window, make the necessary modifications.
4. Click **Load Objects** to fetch the list of objects included in the transport.
5. Add Tasks by clicking +users button to add any tasks for the other users to assign the task. &#x20;
6. Click **Save** to apply the changes.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### **Managing Critical Objects**

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

\


