# Docusign

ReleaseOwl supports multiple credential types for registration. To register a  **Docusign,** follow these steps:

1. Click on the **"Register Credential"** button.

<figure><img src="../../../.gitbook/assets/image (2006).png" alt=""><figcaption></figcaption></figure>

2. Fill in the fields:

* **Credential Name**: Enter a reference name of your choice.
* **Credential Type**: Choose DocuSign.
*   **Scope** – Select the scope of the credential:

    * **Global** – Visible to all users.
    * **Private** – Visible only to the user who created it.

    <img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FuVFtCnCTkcBrwLJqqKQ5%252Fimage.png%3Falt%3Dmedia%26token%3Df777e144-0675-402a-9fca-cc5dfeff2619&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=52f0b6f0&#x26;sv=2" alt="" height="880" width="1898">

**For  Client ID and Secret:**&#x20;

3. Log in to DocuSign and click the “**Admin**” button.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FWpdsO2D4C0UaJGK70trs%252Fimage.png%3Falt%3Dmedia%26token%3Dcfea1ac2-56db-4cf2-a38b-145688d00568&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=150568af&#x26;sv=2" alt="" height="417" width="940">

4. Navigate to Integrations and select Apps and Keys.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FLZz6C0RqJPdYaa4PwiQ6%252Fimage.png%3Falt%3Dmedia%26token%3D3d40b383-a100-43f4-9c95-2824b2ed2903&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=46817feb&#x26;sv=2" alt="" height="425" width="940">

5. Click Add App and Integration Key.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F9Mk8vWSBADIY6Qn0X4Lx%252Fimage.png%3Falt%3Dmedia%26token%3Dd9906ad3-020d-4d1d-945a-8fe7f107346b&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=e5fa64e&#x26;sv=2" alt="" height="476" width="940">

6. Copy the Integration Key which is nothing but the client id

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FNnSVvoclvv6iVb6Qer3J%252Fimage.png%3Falt%3Dmedia%26token%3D8e4a3e5d-c464-41cb-9375-0a689b3b922d&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=f537dae3&#x26;sv=2" alt="" height="424" width="940">

7. Click on the “**Add Secret Key**” button which is nothing but the Client Secret

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Ftv02wL0KR7lUz0w9RM7Q%252Fimage.png%3Falt%3Dmedia%26token%3D11864597-5eef-4d8a-8d35-b75fb6c714b9&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=99f167c8&#x26;sv=2" alt="" height="295" width="940">

8. Set the Redirect URI to: https://na3.releaseowl.com/rateloginserver/api/oauth/accesstoken
9. Check all allowed HTTP methods and click Save.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FpUV6k2GGVVL1kb6s1Xbe%252Fimage.png%3Falt%3Dmedia%26token%3D15c5c322-7e82-46f6-9d61-56b02ce3b06a&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=77aeb178&#x26;sv=2" alt="" height="500" width="940">

10. After creating the app successfully, click on the Actions button, then select Edit.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FsopHBWOtjSL50CxKS8uw%252Fimage.png%3Falt%3Dmedia%26token%3Db985cf11-d483-486f-8650-9fba4ea6e225&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=966b1fd6&#x26;sv=2" alt="" height="505" width="940">

**For Account ID and API Host URL** :&#x20;

1. In the Apps and Keys section, locate:

* **API Account ID**:  Copy the **API Account ID** . Use this as the **Account ID** in the Credential Manager
* **Account Base URL**: Copy the **Account Base URL**.Use this as the **API Host URL** in the Credential Manager.
* Copy these URLs to paste them into the credential manager.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FuOxuyMxNFUp2aXHc1swV%252Fimage.png%3Falt%3Dmedia%26token%3D9ccd89fa-b13c-436a-a139-bfe23445b9f2&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=49df994f&#x26;sv=2" alt="" height="505" width="940">

12. Use the following URLs:

* **Token URL**: The DocuSign URL with /oauth/token.
* **Authorization URL**: The DocuSign URL with /oauth/auth.

1. Copy all the credentials, paste them into the Register Credential, and click the Save button.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F7SkXz84Q6fjiHRk9uzFb%252Fimage.png%3Falt%3Dmedia%26token%3D2c508c13-e1f6-4764-a1ce-4fc65f030ad0&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=3c831e1c&#x26;sv=2" alt="" height="680" width="1434">

**Generate a Token**

1. In Credential Manager, select the created credential.
2. Click Generate Token to verify if the entered credentials are correct.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FAWWWiEHiwAzlmFA7PlMm%252Fimage.png%3Falt%3Dmedia%26token%3Dbb58a3ed-a658-4d30-8d0f-3110c870d189&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=919d31c&#x26;sv=2" alt="" height="723" width="940">
