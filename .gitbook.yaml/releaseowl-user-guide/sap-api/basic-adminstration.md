# Basic Adminstration

**1. Navigate to Credential Manager**

* From the Administration menu, go to **Credential Manager**.
* Click **Register Credential**.

<figure><img src="../../.gitbook/assets/image (657).png" alt=""><figcaption></figcaption></figure>

**2. Provide Credential Details**

* &#x20;**Credential Name**: Enter any identifiable name for the credential.
* &#x20;**Credential Type**: Select **API Management**.
* **Authentication Type**: Select **OAuth2**.
* &#x20;**Client ID, Client Secret, and Token URL**: Follow the steps below to retrieve these details.

<figure><img src="../../.gitbook/assets/image (658).png" alt=""><figcaption></figcaption></figure>

### Steps to Retrieve API Management Details from SAP BTP Cockpit

**4. Access the SAP BTP Cockpit**

* Go to the **SAP BTP Cockpit**.
* Select the **subaccount** that hosts your SAP Cloud Integration application.

**5. Create API Management Instance**

* Navigate to **Services** → **Service Marketplace**.
* Select **API Management, API portal**.
* Click **Create** and provide the following details:
  * **Service**: API Management, API portal
  * **Plan**: `apiportal-apiaccess`
  * **Runtime environment**: Cloud Foundry
  * **Space**: Provide the space name
  * **Instance name**: Enter a name for the instance.
* Click **Next**.

<figure><img src="../../.gitbook/assets/image (660).png" alt=""><figcaption></figcaption></figure>

**6. Provide Service Parameters**

*   Under the **Parameters** section, enter the following JSON string:

    ```json
    { "role": "APIPortal.Administrator" }
    ```
* Click **Create** to complete the instance creation.

<figure><img src="../../.gitbook/assets/image (661).png" alt=""><figcaption></figcaption></figure>

### Steps to Create Service Key

**7. Add Service Key**

* In the **SAP BTP Cockpit**, go to **Instances and Subscriptions**.
* Locate the instance **API Management, API portal** with the plan **apiportal-apiaccess**.
* Under the **Actions** column, choose **Create Service Key**.
* Provide a name for the service key under **Service Key Name**.
* Click **Create**.

<figure><img src="../../.gitbook/assets/image (663).png" alt=""><figcaption></figcaption></figure>

**8. Copy Service Key Details**

* Select the newly created service key to display its details.
*   Copy the following details:

    * **Client ID**
    * **Client Secret**
    * **Token URL**

    <figure><img src="../../.gitbook/assets/image (664).png" alt=""><figcaption></figcaption></figure>

### Steps to Complete Credential Registration in ReleaseOwl

**9. Enter Service Key Details in ReleaseOwl**

* Use the copied details from the service key:
  * **d. Client ID**: Paste the Client ID.
  * **e. Client Secret**: Paste the Client Secret.
  * **f. Token URL**: Paste the Token URL.

**10. Save Credential**

* Click **Save**.
* The credential will appear in the **List of Credentials**.

<figure><img src="../../.gitbook/assets/image (665).png" alt=""><figcaption></figcaption></figure>
