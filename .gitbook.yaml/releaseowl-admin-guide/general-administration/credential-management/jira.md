# Jira

ReleaseOwl supports multiple credential types for registration. To register a **Jira Credential,** follow these steps:

1. Click on the **"Register Credential"** button.

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Fill out the credential form with the following details:

* **Credential Name:** Enter your preferred name for the credential.
* **Credential Type**: Jira
* **Scope** – Select the scope of the credential:
  * **Global** – Visible to all users.
  * **Private** – Visible only to the user who created it.
* **Authentication Type**: Select the authentication type as theOAuth2
* **Client ID and Client Secret:** Paste the Client ID and Client Secret obtained from the OAuth2 integration you created in the Atlassian Developer Console.
* **Jira URL**: [https://api.atlassian.com/](https://api.atlassian.com/)
* **Proxy Type**: Select None
* **Hosting Type** : Select **Cloud**.

3. Click **Save** to register the credential.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fa8ORQ0Jc1JVYY0EftAD2%252Fimage.png%3Falt%3Dmedia%26token%3Dfada48ab-8264-4aba-9e66-b43094a1fb2b&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=c2b13514&#x26;sv=2" alt="" height="820" width="1895">

4. After clicking the _**Save**_ button, the _**Generate Token**_ button will appear.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F21jBAFGkJB5EmE2IAWrW%252Fimage.png%3Falt%3Dmedia%26token%3Dcc78d5f2-5fa8-465e-85a2-254423b97235&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=7ccd8d9a&#x26;sv=2" alt="" height="853" width="1913">

5. Use this button to verify that the entered credentials are correct. If the token is generated successfully, the connection is validated.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FpCyN4U7d82R9aL5BSAVp%252Fimage.png%3Falt%3Dmedia%26token%3Dedb91afa-c5a3-4ead-ab9a-15b0f69f6383&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=53dc7092&#x26;sv=2" alt="" height="846" width="1905">

**B. Registering Jira using Basic Authentication**

**Steps to Generate API Token in Jira**

1. Log in to your Jira account.
2. Go to Account Settings, then select Security.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FFAe60JNu3t4lsQtE8WQ9%252Fimage.png%3Falt%3Dmedia%26token%3D984fb6fb-6524-4a07-8b05-bffe26bae3a2&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=9bdb8074&#x26;sv=2" alt=""><figcaption></figcaption></figure>

3. Click on **Create and manage API tokens**.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F8NkwpHonuiYh0VV45Taf%252Fimage.png%3Falt%3Dmedia%26token%3Dd31130ea-40ec-45d2-8ba0-8af600b73b82&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=cd0775c1&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Click Create API Token, provide a token name, and click **Create**.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FFw1zDgJcCxrWYb9r2oxQ%252Fimage.png%3Falt%3Dmedia%26token%3D6ee608ad-6b21-4548-9e67-897399893a52&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=df3965fd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. Copy the generated **API** token.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FS6iQPNQZnr5zd4LOW7aN%252Fimage.png%3Falt%3Dmedia%26token%3D905889a7-e9db-45a8-9937-b1fdd4b3724c&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=7818cc38&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Register API Token in ReleaseOwl**

1. Open the ReleaseOwl Dashboard.
2. Navigate to Administration, then select **Credential Manager**.
3. Click on **Register Credential**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FbE4NmF9jYdyybUbwOBgY%252Fimage.png%3Falt%3Dmedia%26token%3Dde5b7706-2fa7-4a4a-b2eb-eebff9deeb5c&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=4ea2fbf3&#x26;sv=2" alt="" height="906" width="1912">

4. Fill in the form with the following details:

* **Credential Name:** Enter your preferred name for the credential.
* **Credential Type:** Jira
* **Authentication Type:** Basic
* **Username:** Your Jira account username (usually an email address)
* **Password or API Token:** Paste the copied API token
* **Jira URL:** [https://saparate.atlassian.net](https://saparate.atlassian.net/)
* **Proxy Type**: Select None

5. Click Save to register the credential.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FV2NXQDix7tPMr1iyWYgf%252Fimage.png%3Falt%3Dmedia%26token%3De693dc89-4320-4c21-8a00-f7c9f7e50e4b&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=d63b6110&#x26;sv=2" alt="" height="872" width="1916">

6. After saving, a success message will confirm that the credential has been created.
7. Open the newly created credential.
8. Click on _**Validate**_ to verify the configuration. If the validation is successful, the connection is established successfully.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FkiaNoYJoFBTnQj7IffDC%252Fimage.png%3Falt%3Dmedia%26token%3D67a1e841-d119-4ad9-9085-d12b62b6eca0&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=cfae741a&#x26;sv=2" alt="" height="835" width="1905">
