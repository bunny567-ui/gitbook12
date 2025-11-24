# Credential Management

To integrate SAP Cloud environments with ReleaseOwl, first register the authentication credentials:&#x20;

### **Credential Registration for SAP Cloud Environment**

1. Go to the **Credential Manager** in the administration view and Click on the **"Register Credential"** button.
2. Fill in the required fields:
   * **Credential Name**: Enter a name of your choice.
   * **Credential Type**: Select **SAP Cloud Environment**.
   * **Authentication Type**: Choose either **Basic** or **OAuth2**.
3.  If Basic authentication is selecte&#x64;**:**

    * Provide your **Username** and **Password** (SAP BTP credentials).

    <figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
4. **If OAuth2 authentication is selected:**
   * **Client ID**: Enter the details from the created API service key in the SAP BTP cockpit.
   * **Client Secret**: Enter the details from the created API service key in the SAP BTP cockpit.
   * **Token URL**: Enter the details from the created API service key in the SAP BTP cockpit.

<figure><img src="../../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. Click **Save**. The credential will now appear in the **List of Credentials**.

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Registering Transport Manager Credential**

1. Click on the **"Register Credential"** button.
2. Select **Credential Type** → **Transport Manager Credential**.
3. Provide the required details:
   * **Credential Name**: Enter a name of your choice.
   * **Username**: Enter your SAP Logon username.
   * **Password**: Enter your SAP Logon password.
4. Click **Save**.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. The credential will now be available to access your **Transport Domain Controller** system.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

