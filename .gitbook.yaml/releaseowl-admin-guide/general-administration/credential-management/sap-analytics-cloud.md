---
hidden: true
---

# SAP Analytics Cloud

ReleaseOwl supports multiple credential types for registration. To register a SAP Analytics Cloud credential, follow these steps:

1. Click on the **"Register Credential"** button.

<figure><img src="../../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

2. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **SAP Analytics Cloud**.
* **Scope** – Select the scope of the credential:
  * **Global** – Visible to all users.
  * **Private** – Visible only to the user who created it.

3. To obtain the **Client ID**, **Client Secret**, **Authorization URL**, and **Token URL**, follow the steps explained below.

<figure><img src="../../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

### SAP Analytics Cloud&#x20;

* Log in to your SAP Analytics Cloud (SAC) instance.
* In the SAC home screen, go to **System** > **Administration**.

<div align="center"><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Ffq2XIs9sRMsyeLZT2yso%252Fimage.png%3Falt%3Dmedia%26token%3Dc476ecfa-918e-4485-b225-a40a076a5cab&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=60521ce3&#x26;sv=2" alt="" height="917" width="1905"></div>

* In the **Administration** panel, select the **App Integration** tab.
* Click on **Add OAuth Client**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FqCVgAPv1XO4WpfGL65XX%252Fimage.png%3Falt%3Dmedia%26token%3D9b27dad6-fdbd-4aae-8fae-8ce388f14aea&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=4f2f6c2e&#x26;sv=2" alt="" height="916" width="1919">

* Provide a **Name** for the client.
* Enter the **Redirect URI** (callback URL) as required.
* Click **Add** to create the client.

{% hint style="info" %}
**Note :** Upon creation, the **Client ID** and **Client Secret** will be generated. Save these credentials securely
{% endhint %}

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fz2YBtQGwwRDhwIjvbKOx%252Fimage.png%3Falt%3Dmedia%26token%3D03d0fd46-0a81-4128-bee8-fa5fbe94aaab&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=f57cea30&#x26;sv=2" alt="" height="905" width="1915">

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FXrW9BaZUWJjBLyUGGoPt%252Fimage.png%3Falt%3Dmedia%26token%3Df13873d7-86b0-4423-ac59-a02b4d382a72&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=ca9bf1ce&#x26;sv=2" alt="" height="861" width="996">

* The **Authorization URL** and **Token URL** can be found outside the OAuth Clients section under the **App Integration** or **OAuth Configuration** area.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FELH86LJs25TZAFHBq4VY%252Fimage.png%3Falt%3Dmedia%26token%3D2b0fda46-995b-47f8-bd11-54f10df08d5d&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=c3656780&#x26;sv=2" alt="" height="747" width="1608">

*   In the Credential Manager, provide the following details:

    * **Client ID**
    * **Client Secret**
    * **Authorization URL**
    * **Token URL**

    <img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FXicvzPEvMFlUf7drFHG2%252Fimage.png%3Falt%3Dmedia%26token%3Db3311216-f517-4203-a1d0-32e45017db5d&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=e427c5ca&#x26;sv=2" alt="" height="904" width="1896">
* Click **Save** to store the credential configuration.
* After the credential is successfully saved, the **Generate Token** button will be displayed.
* Click **Generate Token** to initiate token generation and validate the configured credentials.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FvY7WvDZ8UXLLnlyvEaBs%252Fimage.png%3Falt%3Dmedia%26token%3D4a49be49-5439-4868-8161-468133569c21&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=721abfbc&#x26;sv=2" alt="" height="897" width="1896">

* This process verifies whether the provided credentials can successfully establish a connection with the authentication server.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F5VEmClzTEXYgsXFYJMTn%252Fimage.png%3Falt%3Dmedia%26token%3D39cc468e-2eac-46d3-9948-61451d30d0fd&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=357de5f&#x26;sv=2" alt="" height="723" width="1520">
