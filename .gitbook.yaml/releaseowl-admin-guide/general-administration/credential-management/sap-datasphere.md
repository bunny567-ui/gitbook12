# SAP Datasphere

ReleaseOwl supports multiple credential types for registration. To register a SAP Analytics Cloud credential, follow these steps:

1. Click on the **"Register Credential"** button.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

2. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **SAP Datasphere.**

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fqnb2U2JI54BlMrOGLR2o%252Fimage.png%3Falt%3Dmedia%26token%3D9456301b-87e9-4dda-9e02-c4012828e0f5&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=3d2dfbac&#x26;sv=2" alt="" height="820" width="1899">

3. For the Client ID, Secret, Token URL, and Authorization URL:
4. Log in to your **SAP Datasphere** (formerly known as SAP Data Warehouse Cloud) instance.

* Click on your **profile icon** in the top-right corner.
* Select **System** > **Administration**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F9A3Jb9kcATspJHUtVpKL%252Fimage.png%3Falt%3Dmedia%26token%3D6d6e95e0-7aae-4781-95b3-9191e7efee86&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=7c3fed56&#x26;sv=2" alt="" height="972" width="1919">

5. Navigate to the **App Integration** tab.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FGLSfDF3EfkHUelt1zKIv%252Fimage.png%3Falt%3Dmedia%26token%3D786b7f71-e696-4361-87d8-5e472a082148&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=b81c585a&#x26;sv=2" alt="" height="914" width="1912">

6. **Add a New OAuth Client:**

* Click on **Add OAuth Client**.
* Provide a **Client Name**.
* Enter the **Redirect URI** (callback URL for your application).
* Click **Add** to register the client.

{% hint style="info" %}
**Note :**&#x4F;nce added, the system will generate the **Client ID** and **Client Secret**. Ensure these values are copied and stored securely.
{% endhint %}

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fv4SWiQUhfNqeTLkNp6pQ%252Fimage.png%3Falt%3Dmedia%26token%3D5376df64-80bf-48b8-adca-302f79cd4fa4&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=c4006cba&#x26;sv=2" alt="" height="807" width="1347">

7. **Obtain OAuth Endpoints:** The **Authorization URL** and **Token URL** can be accessed from the **App Integration** section, typically shown outside the list of registered clients.
8. **Save OAuth Credentials:** In the Credential Manager, provide the following details:

* **Client ID**
* **Client Secret**
* **Authorization URL**
* **Token URL**

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F5GJ6eq9o8DDOXfZjmn3d%252Fimage.png%3Falt%3Dmedia%26token%3Dff58dbdc-e46f-4403-8959-ebe467488eb9&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=fdba2637&#x26;sv=2" alt="" height="818" width="1908">

9. After entering the required information, click the **Save** button. Upon successful save, a **Generate Token** button will appear.&#x20;
10. Click this button to initiate token generation and validate the entered credentials.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F5mWS3sdZ2B5TzHvM6Zar%252Fimage.png%3Falt%3Dmedia%26token%3Dbd6c0b73-e11e-4040-9fc5-b7be637d879c&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=e35657fa&#x26;sv=2" alt="" height="827" width="1919">

11. This process confirms whether the provided details can establish a successful connection with the authentication server.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FGZluGvZAqz4npAx9dnIE%252Fimage.png%3Falt%3Dmedia%26token%3Ddbcfc225-5bbc-465f-aa4c-54f44e76fd4d&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=4a1a9d55&#x26;sv=2" alt="" height="908" width="1907">
