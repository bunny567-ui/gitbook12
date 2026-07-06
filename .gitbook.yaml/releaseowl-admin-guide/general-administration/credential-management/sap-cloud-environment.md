# SAP Cloud Environment

ReleaseOwl supports multiple credential types for registration. To register a SAP Analytics Cloud credential, follow these steps:

1. Click on the **"Register Credential"** button.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

2. Fill in the details:
   * **Credential Name:** Any identifiable name for the credential.
   * **Credential Type:** Select **SAP Cloud Environment**.
   * **Scope** – Select the scope of the credential:
     * **Global** – Visible to all users.
     * **Private** – Visible only to the user who created it.
   * **Authentication Type:** Select OAuth2
   * **Client ID:** Provide the details from the above created **API service key**.
   * **Client Secret:** Provide the details from the below created **API service key**.
   * **Token URL:** Provide the details from the below created **API service key**.
3. Click **Save**.
4. The credential will now appear in your **Credentials List** and will be used for the registering the CPI environment.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fec1otiE9FiPwmPWbC1ca%252Fimage.png%3Falt%3Dmedia%26token%3D3013ece9-bd14-4c8f-8c91-6051fa27579a&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=d260e155&#x26;sv=2" alt="" height="581" width="1257">

ReleaseOwl requires a **Process Integration Runtime (PIR)** instance in SAP BTP to manage and deploy CPI artifacts. Two PIR service plans are required:

* **API Plan** – for programmatic API access
* **IFLOW Plan** – for managing and testing iFlows

#### 1. **API Plan** – for programmatic API access <a href="#id-1.-api-plan-for-programmatic-api-access" id="id-1.-api-plan-for-programmatic-api-access"></a>

**Purpose:** This instance enables **programmatic access via APIs** for integration, deployment, and artifact management tasks.

**Steps:**

1. Log in to your SAP BTP Cockpit.
2. Navigate to your Global Account, then select the required Subaccount.
3. From the left navigation menu, go to Instances and Subscriptions.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FUT7hY8QW2SESG2LRE3ER%252Fimage.png%3Falt%3Dmedia%26token%3Da9ab0b09-9b18-4e83-853a-7e64f8c008d6&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=95d6209e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Click Create.
5. In the "**New Instance or Subscription**" wizard:

* **Service**: Select SAP Process Integration Runtime
* **Plan**: Choose the API plan
* **Runtime Environment**: Select Cloud Foundry
* **Space**: Select your development space.
* **Instance Name**: Enter a name of your choice

6. Click **Next**, then **Create**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FIM8ZwGl8fOcA5jUeFYgC%252Fimage.png%3Falt%3Dmedia%26token%3D07cf3701-6387-4f01-b336-f88b10bdfb99&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=47edfe6a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The `api` plan provides programmatic access to the SAP Process Integration Runtime, allowing you to connect via APIs for integration tasks.<br>
{% endhint %}

**Assign Required Roles**

In the **Parameters** step, assign the required roles based on the target environment.

**For Non-Production Environments**, add the following roles:

| Role                           | Description                                                                                                                                                 |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **WorkspacePackagesRead**      | Provides read access to CPI artifacts such as iFlow, Script Collection, Message Mapping, and Value Mapping.                                                 |
| **WorkspacePackagesConfigure** | Allows configuration of artifact settings, such as iFlow configuration parameters.                                                                          |
| **WorkspacePackagesEdit**      | Enables creation and modification of artifacts such as iFlow, Script Collection, and Message Mapping. For Value Mapping, it supports only initial creation. |
| **WorkspaceArtifactsDeploy**   | Grants permission to deploy artifacts to runtime, including iFlow, Script Collection, Message Mapping, and Value Mapping.                                   |
| **MonitoringDataRead**         | Provides access to message processing logs and monitoring data for iFlow, SOAP, REST, and OData APIs.                                                       |
| **MessagePayloadsRead**        | Allows users to view message payloads in monitoring.                                                                                                        |
| **TraceConfigurationRead**     | Provides access to view the current tracing configuration.                                                                                                  |
| **TraceConfigurationEdit**     | Allows modification of tracing settings, including enabling trace configuration.                                                                            |

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FzGFTRvhrRC3Y5uurPIXU%252Fimage.png%3Falt%3Dmedia%26token%3Dfc9a6b54-fa92-4897-ab4b-ff317209fd82&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=4e4bb72a&#x26;sv=2" alt="" height="888" width="1757">

**For Production Environments**, add the following roles to enable deployment access

| Role                           | Description                                                                                                                                                 |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **WorkspacePackagesRead**      | Provides read access to CPI artifacts such as iFlow, Script Collection, Message Mapping, and Value Mapping.                                                 |
| **WorkspacePackagesConfigure** | Allows users to configure artifact settings, such as iFlow configuration parameters.                                                                        |
| **WorkspacePackagesEdit**      | Enables creation and modification of artifacts such as iFlow, Script Collection, and Message Mapping. For Value Mapping, it supports only initial creation. |
| **WorkspaceArtifactsDeploy**   | Grants permission to deploy artifacts to runtime, including iFlow, Script Collection, Message Mapping, and Value Mapping.                                   |
| **MonitoringDataRead**         | Provides access to message processing logs and monitoring data for iFlow, SOAP, REST, and OData APIs.                                                       |
| **MessagePayloadsRead**        | Allows users to view message payloads in monitoring.                                                                                                        |

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F0K6IYNkNOS1eKxIgKSj9%252Fimage.png%3Falt%3Dmedia%26token%3Df6377d98-4512-4f31-8d9e-06a056783a59&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=b0c0d8f7&#x26;sv=2" alt="" height="893" width="1892">

**Create Service Key (for `api` plan)**

After the instance is created:

1. Locate the newly created **API instance**.
2. Click the **Actions** menu (**...**) for the instance.
3. Select **Create Service Key**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FHfMo9n63GwWx3gSqMx0t%252Fimage.png%3Falt%3Dmedia%26token%3D1544b02c-f4df-4468-b295-289a41d60f7c&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=3ac06004&#x26;sv=2" alt="" height="890" width="1893">

4. Enter a service key name of your choice.
5. Leave the parameters field blank.
6. Click **Create**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FgcvpdZ6EsFSS0nPf3fvf%252Fimage.png%3Falt%3Dmedia%26token%3D6a77056f-3cf9-42bf-9934-cd390069696a&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=fe3516a5&#x26;sv=2" alt="" height="880" width="1340">

7. Open the newly created **Service Instance**.
8. Locate the created **Service Key**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fi0bCEMVVEWuzwxaqACXS%252Fimage.png%3Falt%3Dmedia%26token%3D4647e486-5163-4064-bd0f-23db158022c0&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=99cd51ba&#x26;sv=2" alt="" height="907" width="1915">

9. Click **View Credentials** to access the generated authentication details. The following details will be displayed:

* **Client ID**
* **Client Secret**
* **Token URL**

10. These credentials are required for registering the SAP CPI (API access) credential in **ReleaseOwl**.

<img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FYzwbwb4081IcWZF8sFzk%252Fimage.png%3Falt%3Dmedia%26token%3D7d10de48-734a-41f1-b005-26c38ee21a9e&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=e50b4ddc&#x26;sv=2" alt="" height="676" width="1281">
