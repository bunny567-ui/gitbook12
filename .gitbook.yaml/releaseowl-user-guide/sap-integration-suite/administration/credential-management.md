# Credential Management

### Step-by-Step Guide: Registering Credentials in ReleaseOwl

A **Process Integration Runtime (PIR)** instance is required in **SAP BTP** for ReleaseOwl to securely manage and deploy **CPI artifacts** across environments. The setup involves creating PIR instances with two different plans — **api** and **IFLOW** — followed by credential registration in ReleaseOwl.

### A. Create a PIR Instance with Plan: `api`

This instance enables **programmatic access via API** for integration tasks.

#### **Steps:**

1. Log in to your SAP BTP Cockpit.
2. Navigate to your **Global Account > Subaccount**.
3. Go to **Instances and Subscriptions** from the left menu.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FUT7hY8QW2SESG2LRE3ER%252Fimage.png%3Falt%3Dmedia%26token%3Da9ab0b09-9b18-4e83-853a-7e64f8c008d6&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=95d6209e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Click on **Create**.
5. In the "**New Instance or Subscription**" wizard:

* **Service**: SAP Process Integration Runtime
* **Plan**: `api`
* **Runtime Environment**: Cloud Foundry
* **Space**: Select your development space (e.g., `dev`)
* **Instance Name**: Choose a name like `CPI_API_Instance`

6. Click **Next**, then **Create**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FIM8ZwGl8fOcA5jUeFYgC%252Fimage.png%3Falt%3Dmedia%26token%3D07cf3701-6387-4f01-b336-f88b10bdfb99&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=47edfe6a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The `api` plan provides programmatic access to the SAP Process Integration Runtime, allowing you to connect via APIs for integration tasks.
{% endhint %}

### Assign Required Roles

In the **Parameters** step, assign the following roles to allow artifact management:

| **Role**                     | **Description**                                   |
| ---------------------------- | ------------------------------------------------- |
| `MessagePayloadsRead`        | Read message payloads in the integration runtime. |
| `MonitoringDataRead`         | View monitoring data for integration flows.       |
| `TraceConfigurationEdit`     | Edit tracing configurations.                      |
| `TraceConfigurationRead`     | View current tracing configuration.               |
| `WorkspaceArtifactsDeploy`   | Deploy artifacts from workspace to runtime.       |
| `WorkspacePackagesConfigure` | Configure packages, parameters, and dependencies. |
| `WorkspacePackagesRead`      | Read-only access to integration packages.         |
| `WorkspacePackagesEdit`      | Modify and configure integration packages.        |

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FQeZkcua5pYBQBiksaMC7%252Fimage.png%3Falt%3Dmedia%26token%3D476837b5-932e-4bed-bf70-61c9bbdf6797&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a4526b6f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Create Service Key (for `api` plan)

After instance creation:

1. Go to **Instances and Subscriptions**.
2. Expand your newly created `api` instance.
3. Click **Create Service Key**.
4. Enter a name (e.g., `cpi-api-key`) and leave parameters blank.
5. Click **Create**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FQtdh3ftS2qBadEGGv2VP%252Fimage.png%3Falt%3Dmedia%26token%3Dee6c05f2-0af7-4a7f-bc69-28e6941c6a20&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=30ea3cb7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

6. Click **View Credentials** to retrieve:

* **Client ID**
* **Client Secret**
* **Token URL**

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252F1XSUCq1nxBsbL8WaXGIo%252Fimage.png%3Falt%3Dmedia%26token%3Dd2feabe3-64ba-4ef6-8274-c68fe9b874b7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2b1c4184&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### &#x20;B. Create a PIR Instance with Plan: `IFLOW`

This is used for managing and deploying **integration artifacts (iFlows)**.

#### **✅ Steps:**

1. Go to your **SAP BTP Cockpit**.
2. Select your **subaccount** that hosts SAP CPI.
3. Go to **Services > Service Marketplace**.
4. Select **SAP Process Integration Runtime** → Click **Create**.
5. Fill in the following:
   * **Service**: SAP Process Integration Runtime
   * **Plan**: `IFLOW`
   * **Runtime Environment**: Cloud Foundry
   * **Space**: Provide the appropriate space (e.g., `dev`)
   * **Instance Name**: (e.g., `CPI_IFLOW_Instance`)

<figure><img src="../../../.gitbook/assets/image (1041).png" alt=""><figcaption></figcaption></figure>

6. Click **Next** and then **Create**.

<figure><img src="../../../.gitbook/assets/image (1042).png" alt=""><figcaption></figcaption></figure>

### Create Service Key (for `IFLOW` plan)

1. Navigate to **Instances and Subscriptions**.
2. Locate the `IFLOW` instance.
3. Click **Actions > Create Service Key**.
4. Enter a name for the key (e.g., `cpi-iflow-key`) → Click **Create**.

<figure><img src="../../../.gitbook/assets/image (1043).png" alt=""><figcaption></figcaption></figure>

5. Click on the service key name to view the key details.
6. You will need these values when setting up ReleaseOwl credentials.

<figure><img src="../../../.gitbook/assets/image (1044).png" alt=""><figcaption></figcaption></figure>

### Step 2: Register Credentials in ReleaseOwl

Credential registration enables secure communication between **ReleaseOwl** and **SAP CPI** environments.

#### A. Register SAP CPI Credential (API Access)

**✅ Steps:**

1. Log in to the **ReleaseOwl Platform**.
2. Go to **Administration > Credential Manager**.

<figure><img src="../../../.gitbook/assets/image (1404).png" alt=""><figcaption></figcaption></figure>

3. Click **Register Credential**.
4. Fill in the details:
   * **Credential Name:** Any identifiable name for the credential.
   * **Authentication Type:** Select OAuth2
   * **Client ID:** Provide the details from the above created API service key.
   * **Client Secret:** Provide the details from the above created API service key.
   * **Token URL:** Provide the details from the above created API service key.
5. Click **Save**.

The credential will now appear in your list and can be used in pipelines and deployments.

<figure><img src="../../../.gitbook/assets/image (18) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### B. Register SAP CPI Credential (IFLOW Access)

This step allows ReleaseOwl to securely interact with CPI for **artifact deployment and management** via the IFLOW plan.

**✅ Steps:**

1. Navigate to **Credential Manager** from the **Administration** menu in the ReleaseOwl Platform.
2. Click **Register Credential**.
3. Set the **Credential Type** to **SAP Cloud Environment**.
4. Fill in the following details:
   * **Credential Name**: Enter a meaningful name (e.g., `CPI IFLOW Credential`)
   * **Authentication Type**: Select **OAuth2**
   * **Client ID:** Provide the details from the above created IFLOW service key.
   * **Client Secret:** Provide the details from the above created IFLOW service key.
   * **Token URL:** Provide the details from the above created IFLOW service key.
5. Click **Save**.
6. The new credential will now appear in the **List of Credentials** and can be used in Release Pipelines for IFLOW deployments.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
