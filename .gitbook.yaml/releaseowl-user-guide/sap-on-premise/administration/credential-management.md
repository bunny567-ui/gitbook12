# Credential Management

To integrate a SAP On-Premise system with ReleaseOwl, you must first register the authentication credentials. Follow the steps below to add your SAP On-Premise credential:

### **Registering Transport Manager Credential**

1. Click on the **"Register Credential"** button.
2. Select **Credential Type** → **Transport Manager Credential**.
3. Provide the required details:
   * **Credential Name**: Enter a name of your choice.
   * **Username**: Enter your SAP Logon username.
   * **Password**: Enter your SAP Logon password.
4. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. The credential will now be available to access your **Transport Domain Controller** system.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Credential Registration for SAP BTP Environment**

&#x20;If the Cloud Connector is used to connect on-premise SAP systems to SAP BTP, then you must register an **SAP Cloud Environment credential** in ReleaseOwl. It is required because the destination pointing to the on-premise system is configured in **SAP BTP**, and ReleaseOwl must authenticate to BTP to access that destination.&#x20;

1. Go to the **Credential Manager** in the administration view and Click on the **"Register Credential"** button.
2. Fill in the required fields:
   * **Credential Name**: Enter a name of your choice.
   * **Credential Type**: Select **SAP Cloud Environment**.
   * **Authentication Type**: Choose **Basic.**
3.  &#x20;Provide your **Username** and **Password** (SAP BTP credentials).

    <figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
4. Click **Save**. The credential will now appear in the **List of Credentials**.

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



