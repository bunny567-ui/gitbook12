# Credential Management

### Credential Registration <a href="#pdf-page-dk8rbzgxugve408ig5ly-credential-registration" id="pdf-page-dk8rbzgxugve408ig5ly-credential-registration"></a>

1. Admin users can switch to the **Administration View** to access the **Credential Manager**.
2. Click the **Credential Manager** menu option on the left-hand pane to view the list of registered credentials.

<figure><img src="../../../.gitbook/assets/image (1363).png" alt=""><figcaption></figcaption></figure>

3. To add a new credential, click **Register Credential** available on the right-hand panel, and then click on the **Register Credential** button.

<figure><img src="../../../.gitbook/assets/image (1364).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FOlQXbRau9NAUz064D5V8%252Fimage.png%3Falt%3Dmedia%26token%3D403b126d-ca63-4a3f-ab49-49cb64c161bd&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=cb343d62&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **SAP Datasphere.**

<figure><img src="../../../.gitbook/assets/image (1365).png" alt=""><figcaption></figcaption></figure>

5. For the Client ID, Secret, Token URL, and Authorization URL:
6. Log in to your **SAP Datasphere** (formerly known as SAP Data Warehouse Cloud) instance.

* Click on your **profile icon** in the top-right corner.
* Select **System** > **Administration**.

<figure><img src="../../../.gitbook/assets/image (1366).png" alt=""><figcaption></figcaption></figure>

* Navigate to the **App Integration** tab.

<figure><img src="../../../.gitbook/assets/image (1367).png" alt=""><figcaption></figcaption></figure>

7. **Add a New OAuth Client:**

* Click on **Add OAuth Client**.
* Provide a **Client Name**.
* Enter the **Redirect URI** (callback URL for your application).
* Click **Add** to register the client.

{% hint style="info" %}
**Note :** Once added, the system will generate the **Client ID** and **Client Secret**. Ensure these values are copied and stored securely.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (1368).png" alt=""><figcaption></figcaption></figure>

8. **Obtain OAuth Endpoints:**

* The **Authorization URL** and **Token URL** can be accessed from the **App Integration** section, typically shown outside the list of registered clients.

9. **Save OAuth Credentials:**

In the Credential Manager, provide the following details:

* **Client ID**
* **Client Secret**
* **Authorization URL**
* **Token URL**

<figure><img src="../../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* After entering the required information, click the **Save** button. Upon successful save, a **Generate Token** button will appear. Click this button to initiate token generation and validate the entered credentials.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* This process confirms whether the provided details can establish a successful connection with the authentication server.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
