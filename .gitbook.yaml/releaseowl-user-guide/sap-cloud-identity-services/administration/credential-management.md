# Credential Management

Here are the following steps to create the Cloud Identity Service instance:

#### **Create Cloud Identity Service Instance**

1. Navigate to **Instances & Subscriptions** in your SAP BTP subaccount.
2. Click on the **Create** button.
3. Under the **Service** section, select **Cloud Identity Services**.
4. Choose the required **Service Plan**, and click **Next**.
5. Click **Create** to provision the instance.

<figure><img src="../../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

#### **Activate Administrator Account**

1. An **activation email** will be sent to the registered email address.
2. Open the email and click **Activate Account**.
3. Set your password and click on **Continue.**

<figure><img src="../../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

### **Trust Configuration in SAP BTP**

1. Go to **Trust Configuration** in your SAP BTP subaccount.
2. Click on **Establish Trust**.

<figure><img src="../../../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

#### **Configure Trust**

1. Select your **Cloud Identity Service tenant** → click **Next**.

<figure><img src="../../../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

2. Select your **Cloud Identity Service domain** → click **Next**.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

3. Under **Configuration Parameters**:
   * Set **Origin Key = sap.custom**
   * Click **Next** and then **Finish**.

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

4. A new trust configuration will be created with Origin Key **sap.custom**.

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

#### **OpenID Connect Settings**

1. Open your created **OpenID Connect** trust configuration.

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

2. In the **Parameters** section, enable **Available for User Logon.**&#x20;

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

3. Navigate to **Attribute Mappings** and fill in the required mappings:

| **Related Role** | **Attribute Name** | **Value**                         | **Operator** |
| ---------------- | ------------------ | --------------------------------- | ------------ |
| Role Collection  | email              | Your Cloud Identity Service email | equals       |

4. Click **Save** to update the configuration.

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

### **Cloud Identity Service Configuration**

**Access Applications**

1. Log in to your **Cloud Identity Service tenant**.
2. Navigate to **Applications & Resources → Applications**.

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

3. A new **Bundled Application** will be automatically created with the name:\
   **SAP BTP Subaccount – \<Subaccount Name>**

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

#### **Configure Single Sign-On**

1. Open the newly created application.
2. Go to **Single Sign-On → Subject Name Identifier**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Configure as follows:

* **Source (Primary):** Identity Directory
* **Attribute (Primary):** Email
* **Source (Fallback):** Identity Directory
* **Attribute (Fallback):** Email

4. Click on the **Save** button.&#x20;

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Configure Conditional Authentication**

1. Go to **Trust** → **Conditional Authentication**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Set **Default Identity Provider = Identity Authentication**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Integration with ReleaseOwl

1. Log in to **ReleaseOwl**.
2. Go to **Administration → Credential Manager**.
3. Click on **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Enter the following information:
   * **Credential Type:** SAP Cloud Identity
   * **User Name:** Cloud Identity Service Username
   * **Password:** Cloud Identity Service Password
5. Click **Save** to complete the credential registration.

<figure><img src="../../../.gitbook/assets/image (1646).png" alt=""><figcaption></figcaption></figure>
