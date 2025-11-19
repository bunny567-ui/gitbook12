# Cloud Environment Registration

### **Registering SAP On-Premise Environment**

To access the **SAP On-Premise environment** with **ReleaseOwl**, you must first register the **SAP On-Premise system login credentials**.

Follow these steps to register a new SAP On-Premise Environment:

1. In **Administration View**, go to **Environments** and select **SAP Cloud Environment**.
2. On the displayed page, click **Register Cloud Environment**.

<figure><img src="../../../.gitbook/assets/image (264).png" alt=""><figcaption></figcaption></figure>

4. Fill in the required details:&#x20;

* **Name**: Enter a name of your choice.
* **Region**: Select the region of the SAP BTP Cockpit (e.g., Singapore, USA).
* **API Endpoint**: Provide the API endpoint.
* **Credential Name**: Select the credential created in the Credential Manager.
* **Org**: This is automatically populated from the dropdown menu.
* **Space**: This is also automatically populated from the dropdown menu.
* **Environment Type**: Select the environment type of your choice.

5. Click **Save.**

<figure><img src="../../../.gitbook/assets/image (474).png" alt=""><figcaption></figcaption></figure>

### **Registering Transport Manager Credential**

1. Click on the **"Register Credential"** button.
2. Select **Credential Type** → **Transport Manager Credential**.
3. Provide the required details:
   * **Credential Name**: Enter a name of your choice.
   * **Username**: Enter your SAP Logon username.
   * **Password**: Enter your SAP Logon password.
4. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. The credential will now be available to access your **Transport Domain Controller** system.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## **Transport Domain Controller**

* Go to **Administration View**.
* Select **Transport Domain Controller**.
* Click **"Register Transport Domain Controller"** to begin registration.

<figure><img src="../../../.gitbook/assets/image (51) (1).png" alt=""><figcaption></figcaption></figure>

#### **Enter Transport Domain Controller Settings:**&#x20;

* **Name (Required)** – Enter a name for the Transport Domain Controller.
* **Proxy Type (Required)** – Choose one of the following:
  * **None**
  * **SAP Cloud Connector**

**If Proxy Type: None is selected**

The following fields appear:

* **Application Server (Required)** – Enter the **application server address**.
* **Port (Required)** – Specify the port number as defined in SAP Logon. To find the port number, go to **SAP Easy Access**, enter transaction code **SMICM**, then navigate to the **Goto** menu and select **Services**. The **HTTP port number** will be listed there.

<figure><img src="../../../.gitbook/assets/image (1111).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1110).png" alt=""><figcaption></figcaption></figure>

* **HTTPS** – Check the box if **HTTPS** is required.
* **Client ID (Required)** – Enter the **Client ID** of the Transport Domain Controller.
* **Transport Manager Credential (Required)** – Select the **automatically registered** Transport Manager credential.
* **Enable Retrofit (Source)** – Enable this option if **transport retrofit** is required.
* **Retrofit Domain Controller (Destination)** – Define the **destination retrofit domain controller**, if applicable.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**If Proxy Type: SAP Cloud Connector is selected**

The following additional fields appear:

* **Proxy URL (Required)** – Enter the **SAP BTP Proxy URL** from the **destination configuration**.
* **SAP Cloud Credentials (Required)** – Select the **automatically registered SAP Cloud credentials**.
* **Destination** – Enter the **destination name** from the **Connectivity section** of SAP BTP.
* **SAP User (Required)** – Enter the **SAP Username** from the **Destination Configuration** in the **Connectivity section** of SAP BTP.
* **Client ID (Required)** – Enter the **Client ID** of the **SAP system**.

<figure><img src="../../../.gitbook/assets/image (285).png" alt=""><figcaption></figcaption></figure>

#### **Configure System Landscape**

The **System Landscape** section allows you to define multiple systems within the transport domain.

**Columns in the System Landscape Table:**

* **System ID:** A unique identifier for the system (e.g., system code or name).
* **Client ID:** The client number associated with the system.
* **Description:** A brief description of the system (e.g., Development, QA, Production).
* **System Type:** The category of the system, such as Development, Production, or Test.
* **Type:** Specifies the system’s role or function (e.g., Customizing, Test, Production).
* **Target Group:** Defines the associated target group, if applicable.
* **Default Client :** When a system contains multiple clients, **Workbench Transport Requests** must be imported into the system’s default client ID. Usually, this default client matches the source client defined in the **Domain Controller**. However, in some cases, the system’s default client ID may differ from the Domain Controller’s source client.&#x20;
* In such cases, this checkbox is used to explicitly specify which client should be treated as the **default client** for Workbench Transport imports.

**Additional Configurations**

* If Virtual System, gCTS Generated, SAP Reference, or Non-ABAP System is selected, then the SAP User and Destination fields will be disabled.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Adding a System**

1. Click the Add System button.
2. Fill in the required details in the new row.
3. Select the appropriate System Type and Description.
4. Click Save to register the system.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Fetching Existing Systems**

* Click the Get Systems button to retrieve predefined systems linked to the transport domain.

#### **Deleting a System**

* Click the X button next to a system entry to remove it from the list.

#### **Saving Changes**

* Click Save to store modifications.
* Click Cancel to discard changes and exit the interface.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

The newly created Transport Domain Controller gets displayed in the Transport Domain Controller screen.

<figure><img src="../../../.gitbook/assets/image (52) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Create Transport Domain Controller in ReleaseOwl as per the destination created for all the dev Environment.
{% endhint %}

#### Create a New Project

1. Navigate to the **Projects** section and click on **Create a Project**.

<figure><img src="../../../.gitbook/assets/image (476).png" alt=""><figcaption></figcaption></figure>

2. Fill in the required details:
   * **Name**: Enter a project name of your choice.
   * **Project Type**: Select **SAP On-Premise**.
3. Click the **Save** button to create the project.

<figure><img src="../../../.gitbook/assets/image (477).png" alt=""><figcaption></figcaption></figure>

4. After creating the project, click on the **three-dot menu** next to the project.
5. Select **Switch On Project** to activate it.

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

6. Click on **Project Settings**, located in the top-right corner, before your account user icon.

<figure><img src="../../../.gitbook/assets/image (480).png" alt=""><figcaption></figcaption></figure>

7. Navigate to the **Environment** section.
8. Click on the **+ Add** button to add the newly created **On-Premise** environment.
9. Click on the **Select** button to confirm your choice.

<figure><img src="../../../.gitbook/assets/image (481).png" alt=""><figcaption></figcaption></figure>

10. If needed, you can set the selected environment as a **Source System** by checking the **Source** button.

<figure><img src="../../../.gitbook/assets/image (1620).png" alt=""><figcaption></figcaption></figure>
