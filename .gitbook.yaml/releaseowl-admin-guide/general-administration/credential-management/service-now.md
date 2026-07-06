# Service Now

ReleaseOwl supports multiple credential types for registration. To register a **Service Now** **Credential,** follow these steps:

1. Click on the **"Register Credential"** button.

<figure><img src="../../../.gitbook/assets/image (2030).png" alt=""><figcaption></figcaption></figure>

2. Fill in the fields:

* **Credential Name**: Enter a reference name of your choice.
* **Credential Type**: Select **ServiceNow**.
* **Scope** – Select the scope of the credential:
  * **Global** – Visible to all users.
  * **Private** – Visible only to the user who created it.
* **Authentication Type**: Choose either:
  * **OAuth2**: For token-based authentication.
  * **Basic Authentication**: For username and password-based access.
* **Instance URL**: Enter your ServiceNow hosting URL.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F2IodsUEXp6LwTCd9IdjF%252Fimage.png%3Falt%3Dmedia%26token%3D8195efd5-3438-4984-9b3b-47cc9f44a744&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=dbf48579&#x26;sv=2" alt="" height="858" width="1904">

**For OAuth2 Authentication**

1. Log in to your ServiceNow account.
2. Navigate to **ALL** and search for **Application Registry**.
3. Click on **Application Registry**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FTACEnPhz0BTj3ycIUedG%252Fimage.png%3Falt%3Dmedia%26token%3D771adf8a-2a8e-4a70-89bc-974f89eab595&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=cd786adb&#x26;sv=2" alt="" height="747" width="1506">

4. Locate and click on **ReleaseOwl** in the list of OAuth Registries.
5. View the **Client ID** and **Client Secret** associated with ReleaseOwl.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FxD7UV1c2yxp6sB9ZD6Sr%252Fimage.png%3Falt%3Dmedia%26token%3D2a59d855-99a7-43a7-b8ce-0edafe3b7b5d&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=4368b614&#x26;sv=2" alt="" height="729" width="1542">

6. Copy the **Client ID** and **Client Secret** and paste them into the corresponding fields in the **Register Credential** form in ReleaseOwl under **OAuth2 Authentication**.
7. Click the **Save** button.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FhhDXe4AUzJbxP3s4W7Jv%252Fimage.png%3Falt%3Dmedia%26token%3D568ac4cb-fd65-4d6d-b474-8fede13585a3&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=5ae231d3&#x26;sv=2" alt="" height="827" width="1902">

8. Click **Generate Token**.
9. A popup will appear prompting you to enter your ServiceNow **username** and **password**.
10. Enter your credentials and click the **Generate** button.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FWtvtthER80YSRxKL0vCr%252Fimage.png%3Falt%3Dmedia%26token%3D1b99b6d3-5cfb-4008-9ae3-f493b11f8b8e&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=f0d5f237&#x26;sv=2" alt="" height="219" width="854">

11. The generated token will be available in the **Manage Tokens** section under **ALL** in the ServiceNow website.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FK6GJi6FuTZROTdl07Wsy%252Fimage.png%3Falt%3Dmedia%26token%3Db1de5dfe-baf0-4f38-9937-dd0e30b3740f&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=3d46315f&#x26;sv=2" alt="" height="726" width="1574">

**For Basic Authentication**

1. Log in to your ServiceNow instance.
2. Click the **Request Instance** button.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FOBaU2dxdZ7UVS3s2RYnE%252Fimage.png%3Falt%3Dmedia%26token%3D038e1b92-e9fa-4364-a175-31a0befd06f7&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=d4e987bf&#x26;sv=2" alt="" height="616" width="1377">

3. You will receive an email containing the instance details.
4. In the email, locate the section containing your **username** and **password** details.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FIUtna7rE3pB7bdfnolhT%252Fimage.png%3Falt%3Dmedia%26token%3D5ee01a05-9c2d-44eb-b2d9-042c80e7dcee&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=d12c1190&#x26;sv=2" alt="" height="691" width="981">

5. Copy these credentials and paste them into the corresponding fields in the **Register Credential** form in ReleaseOwl under **Basic Authentication**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FjQ9cggJqJkR9c5SGtcJW%252Fimage.png%3Falt%3Dmedia%26token%3Dc6efd36b-8728-443b-8e3d-fbc326407cd3&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=6cd03e60&#x26;sv=2" alt="" height="688" width="1388">
