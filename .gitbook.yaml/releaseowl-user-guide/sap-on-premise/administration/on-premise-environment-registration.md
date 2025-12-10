# On-Premise Environment Registration

Before configuring the SAP On-Premise Environment, you must first register the SAP On-Premise authentication credential. Use the [link](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-on-premise/administration/credential-management) to complete the credential setup.

## **Registering SAP On-Premise Environment**

To access the **SAP On-Premise environment** with **ReleaseOwl**, you must first register the **SAP On-Premise system login credentials**. Follow the steps below to add your SAP On-Premise Environment:

1. Go to **Administration View**.
2. Select **Transport Domain Controller**.
3. Click **"Register Transport Domain Controller"** to begin registration.

<figure><img src="../../../.gitbook/assets/image (51) (1).png" alt=""><figcaption></figcaption></figure>

### **Transport Domain Controller Settings**

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

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**If Proxy Type: SAP Cloud Connector is selected**

The following additional fields appear:

* **Proxy URL (Required)** – Enter the **SAP BTP Proxy URL** from the **destination configuration**.
* **SAP Cloud Credentials (Required)** – Select the **automatically registered SAP Cloud credentials**.
* **Destination** – Enter the **destination name** from the **Connectivity section** of SAP BTP.
* **SAP User (Required)** – Enter the **SAP Username** from the **Destination Configuration** in the **Connectivity section** of SAP BTP.
* **Client ID (Required)** – Enter the **Client ID** of the **SAP system**.

<figure><img src="../../../.gitbook/assets/image (285).png" alt=""><figcaption></figcaption></figure>

### **Configure System Landscape**

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

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Adding a System**

1. Click the Add System button.
2. Fill in the required details in the new row.
3. Select the appropriate System Type and Description.
4. Click Save to register the system.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Fetching Existing Systems**

* Click the Get Systems button to retrieve predefined systems linked to the transport domain.

#### **Deleting a System**

* Click the X button next to a system entry to remove it from the list.

#### **Saving Changes**

* Click Save to store modifications.
* Click Cancel to discard changes and exit the interface.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

The newly created Transport Domain Controller gets displayed in the Transport Domain Controller screen.

<figure><img src="../../../.gitbook/assets/image (52) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:**&#x20;

* Create Transport Domain Controller in ReleaseOwl as per the destination created for all the dev Environment.&#x20;
{% endhint %}

### Create the Project

To create a new project, follow the [link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-admin-guide/general-administration/project-management)and complete the setup.

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
