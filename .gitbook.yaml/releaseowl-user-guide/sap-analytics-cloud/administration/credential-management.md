# Credential Management

### Credential Registration <a href="#pdf-page-gxe94pcl07aymb35lkd4-credential-registration" id="pdf-page-gxe94pcl07aymb35lkd4-credential-registration"></a>

1. Admin users can switch to the **Administration View** to access the **Credential Manager**.
2. Click the **Credential Manager** menu option on the left-hand pane to view the list of registered credentials.

<figure><img src="../../../.gitbook/assets/image (41) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. To add a new credential, click **Register Credential** available on the right-hand panel, and then click on the **Register Credential** button.

<figure><img src="../../../.gitbook/assets/image (1343).png" alt=""><figcaption></figcaption></figure>

4. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **SAP Analytics Cloud**.

<figure><img src="../../../.gitbook/assets/image (1344).png" alt=""><figcaption></figcaption></figure>

5. For the Client ID, Secret, Token URL, and Authorization URL:

* Log in to your SAP Analytics Cloud (SAC) instance.&#x20;
* In the SAC home screen, go to **System** > **Administration**.

<figure><img src="../../../.gitbook/assets/image (25) (1) (1).png" alt=""><figcaption></figcaption></figure>

* In the **Administration** panel, select the **App Integration** tab.
* Click on **Add OAuth Client**.

<figure><img src="../../../.gitbook/assets/image (27) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Provide a **Name** for the client.
* Enter the **Redirect URI** (callback URL) as required.
* Click **Add** to create the client.

{% hint style="info" %}
**Note :** Upon creation, the **Client ID** and **Client Secret** will be generated. Save these credentials securely&#x20;
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (28) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (29) (1) (1).png" alt=""><figcaption></figcaption></figure>

* The **Authorization URL** and **Token URL** can be found outside the OAuth Clients section under the **App Integration** or **OAuth Configuration** area.

<figure><img src="../../../.gitbook/assets/image (30) (1) (1).png" alt=""><figcaption></figcaption></figure>

*   In the Credential Manager, provide the following details:

    * **Client ID**
    * **Client Secret**
    * **Authorization URL**
    * **Token URL**

    <figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
* After entering the required information, click the **Save** button. Upon successful save, a **Generate Token** button will appear. Click this button to initiate token generation and validate the entered credentials.

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* This process confirms whether the provided details can establish a successful connection with the authentication server.

<figure><img src="../../../.gitbook/assets/image (1403).png" alt=""><figcaption></figcaption></figure>

