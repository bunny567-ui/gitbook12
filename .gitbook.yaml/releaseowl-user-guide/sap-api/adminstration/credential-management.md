# Credential Management

To enable secure integration between **ReleaseOwl** and **SAP API Management**, credentials must be registered within ReleaseOwl’s Credential Manager. This process ensures authenticated access to the SAP API Portal for deploying and promoting API artifacts as part of DevOps pipelines.&#x20;

### Step-by-Step Guide: Registering Credentials in ReleaseOwl

**1. Navigate to Credential Manager**

* From the Administration menu, go to **Credential Manager**.
* Click **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**2. Provide Credential Details**

* **a. Credential Name**: Enter any identifiable name for the credential.
* **b. Credential Type**: Select **API Management**.
*   **c. Authentication Type:**  You have **two options** to register your credentials:

    **Option A: Upload Credentials File**

    * Click the **Browse** button.
    * Upload the credentials file downloaded from **SAP BTP Cockpit** (API Management Service).

    **Option B: Manual Entry**

    * If choosing **Manual Entry**, provide the required details from the **API service key** created in **SAP BTP Cockpit**. (The steps to create and extract the API service key are explained below.)

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Steps to Retrieve API Management Details from SAP BTP Cockpit

To retrieve the **Client ID**, **Client Secret**, and **Token URL** for SAP API Management integration, follow these steps:

#### 3. Access the SAP BTP Cockpit

1. Go to the **SAP BTP Cockpit** and log in with your credentials.
2. In the **SAP BTP Cockpit**, navigate to **Instances and Subscriptions**.
3. Click on the **Create** button.
4. Fill in the necessary details as follows:
   * **Service**: API Management, API Portal
   * **Plan**: `apiportal-apiaccess`
   * **Runtime Environment**: Cloud Foundry
   * **Space**: Dev
   * **Instance Name**: Enter a name of your choice

<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### 4. Create a Service Key

1. After the instance is created, click the **three-dot menu (⋮)** next to it.
2. Select **"Create Service Key"**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Enter a **name** for the key (e.g., `api-access-key`) and click **Create**.
4. Once created, click on the key to view credentials like `clientid`, `clientsecret`, and `url` — used for API authentication.

<figure><img src="../../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Steps to Complete Credential Registration in ReleaseOwl

**5. Enter Service Key Details in ReleaseOwl**

* Use the copied details from the service key:
  * **d. Client ID**: Paste the Client ID.
  * **e. Client Secret**: Paste the Client Secret.
  * **f. Token URL**: Paste the Token URL.

**6. Save Credential**

* Click **Save**.
* The credential will appear in the **List of Credentials**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
