# Transport Management Actions

The **Transport Management** module includes various options to manage, import, and track transport requests efficiently. Below are detailed descriptions of the key actions:

### **1. Import**

To import a transport from the source system to the target system:

1. Select the required transport request.
2. Go to **Actions** and click **Import**.
3. In **Select Target System ID**, choose an ID from the dropdown list.
4. In **User Story Status**, select a status to be applied to the user story after import.

<figure><img src="../../.gitbook/assets/image (238).png" alt=""><figcaption></figcaption></figure>

5. Click **Import** to execute the process.
6. If the transport is not attached to a user story, you can directly **select the target system ID** and click the **Import** button to import the transport from the source system to the target system.

<figure><img src="../../.gitbook/assets/image (239).png" alt=""><figcaption></figcaption></figure>

### **2. Import History**

**Import History** provides details of the target systems where the selected transport was imported.\
To view the import history of a transport:

1. Select the required transport request.
2. Go to **Actions** and click **Import History** to view past imports and their statuses.

<figure><img src="../../.gitbook/assets/image (237).png" alt=""><figcaption></figcaption></figure>

### **3. Release**

To import a transport request to the target system, follow these steps:

1. Ensure all tasks under the transport request are **released** before proceeding.
2. Once all tasks are released, the transport request itself can be released.
3. All changed objects in the transport request will be available for import into the target system.
4. **Note:** Once released, no further changes can be made to the transport request.
5. To release a transport:
   * Go to the **Transport Management** page.
   * Select the required transport request and click **Release**.
   * The transport is then released, and its **status changes to Released**.
   * You will get the **last imported system** value.

<figure><img src="../../.gitbook/assets/image (241).png" alt=""><figcaption></figcaption></figure>

### 4. Commits

The **Commits** section provides a record of all changes made to a transport request. To view commits:

1. Select the required transport request.
2. Go to **Actions** and click **Commits**.

<figure><img src="../../.gitbook/assets/image (243).png" alt=""><figcaption></figcaption></figure>

3. View the details, including:

* Branch name
* Commit ID
* Committed by
* Commit time

<figure><img src="../../.gitbook/assets/image (240).png" alt=""><figcaption></figcaption></figure>

### 5. Load Objects

To load the object, follow these steps:

1. Select the required transport request.
2. Go to **Actions** and click Load Objects.

<figure><img src="../../.gitbook/assets/image (236).png" alt=""><figcaption></figcaption></figure>

3. It will load objects from the selected transport request into the system for validation or further modifications

<figure><img src="../../.gitbook/assets/image (235).png" alt=""><figcaption></figcaption></figure>

### Remove from Project&#x20;

The **Remove from Project** option allows you to remove a transport from the **Current Project Transports** list. This is useful for managing and organizing only the relevant transports for your active project work.

<figure><img src="../../.gitbook/assets/image (1120).png" alt=""><figcaption></figcaption></figure>
