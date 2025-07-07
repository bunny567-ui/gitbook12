# Cloud Environment Registration

ReleaseOwl seamlessly integrates with SAP API Management to enable continuous integration and delivery of API artifacts.&#x20;

Through secure credential management and environment registration, ReleaseOwl connects directly with the API Management tenant to manage, deploy, and promote API proxies and related artifacts across development, quality, and production landscapes.

### API Environment Registration

1. Navigate to Environments from the Administration menu.
2. Select API Management and click on register API Management.
3. Provide the following details and click on **Save.**

| **Field**        | **Description**                                                |
| ---------------- | -------------------------------------------------------------- |
| Name             | Enter a unique name for the SAP API Environment.               |
| Host URL         | Copy the URL from the created SAP API Management instance.     |
| OAuth Credential | Select the OAuth credential created in the credential manager. |
| Environment Type | Select the environment type (e.g., Dev, QA, Prod).             |

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Create the Project <a href="#create-the-project" id="create-the-project"></a>

1. Go to the **Administration** page of the application.
2. Under the **Projects** section, locate the **Create New Project** button.
3. Click on the **Create New Project** button located at the top right corner.
4. A popup form titled **Create Project** will appear.
5. Enter the following details:

| **Field**          | **Description**                                                                                |
| ------------------ | ---------------------------------------------------------------------------------------------- |
| **Name**           | Provide a unique name for your project.                                                        |
| **Description**    | Optionally, add a description for better clarity.                                              |
| **Project Prefix** | Specify a prefix that aligns with your project standards. This will act as a short identifier. |
| **Project Type**   | Select **SAP CPI** as the project type.                                                        |

<figure><img src="../../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. To the right of each project, click on the **action button** (three dots).
7. Click on **Switch To Project** to navigate to the configuration page of the selected project.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F2Dn3Qm6ImFNuHL8a1e1S%252Fimage.png%3Falt%3Dmedia%26token%3De95acfbd-5890-48ca-86b3-3c0bda8f80f2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e5aadaba&#x26;sv=2" alt=""><figcaption></figcaption></figure>

8. Navigate to the **Project Settings** page. Click the **Environments** tab.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FlLnTTq33CQJypWdCloj0%252Fimage.png%3Falt%3Dmedia%26token%3D9a20a37f-6183-42ac-ba96-0e282c43d216&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b94b3af0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

9. Click **+ Add** (top-right of the **Environments** table).
10. Select the desired environment and click **Select**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FH5MQ229cbWTjicoLwGGh%252Fimage.png%3Falt%3Dmedia%26token%3Df8e09b3e-02e0-4a96-9f67-6a812e422736&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=45061be4&#x26;sv=2" alt=""><figcaption></figcaption></figure>

11. If this environment is the **source for deployments or synchronization**, check the **Source** checkbox.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F0rKjO6Md4mon3oWXf0oM%252Fimage.png%3Falt%3Dmedia%26token%3D6aa63082-9af7-44c1-9add-efae772de1f8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=918ffff3&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Manage User Roles and Permissions**

* Go to the **Users** tab.
* Click the **Edit (lock) icon** next to the user.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F1mQm9D1fEcm6N8h4BFkn%252Fimage.png%3Falt%3Dmedia%26token%3D67d2d457-66b6-405b-9d6f-77f727999312&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e651d26c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Check the **Deploy** checkbox for relevant environment(s)

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FyUKbEmsVdfHG7Cw8g1u8%252Fimage.png%3Falt%3Dmedia%26token%3D6a3c1976-1580-4051-8730-335c5ff2de2a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a17a922c&#x26;sv=2" alt=""><figcaption></figcaption></figure>
