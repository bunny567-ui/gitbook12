# Credential Management

This section explains how to configure and manage credentials required for integrating **ReleaseOwl with SAP Cloud Platform Integration (CPI)**. Credential management ensures secure communication between ReleaseOwl and SAP systems using both **system-level** and **user-level authentication mechanisms**.

## CPI (Cloud Platform Integration)

The CPI requires credentials to secure integration scenarios and enable internal SAP communications. It supports the following credential types:

* **System-to-system authentication** (Service Keys)
* **User-based authentication** (Web Authentication)

## System-to-System Authentication ( Service Keys)

Service Keys are used for automated, system-level authentication. They allow ReleaseOwl to communicate securely with SAP Integration Suite without any user interaction.

ReleaseOwl requires a **Process Integration Runtime (PIR)** instance in SAP BTP to manage and deploy CPI artifacts. Two PIR service plans are required:

* **API Plan** – for programmatic API access
* **IFLOW Plan** – for managing and testing iFlows

### 1.  **API Plan** – for programmatic API access

**Purpose:**\
This instance enables **programmatic access via APIs** for integration, deployment, and artifact management tasks.

#### **Steps:**

1. Log in to your SAP BTP Cockpit.
2. Navigate to your Global Account, then select the required Subaccount.
3. From the left navigation menu, go to Instances and Subscriptions.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FUT7hY8QW2SESG2LRE3ER%252Fimage.png%3Falt%3Dmedia%26token%3Da9ab0b09-9b18-4e83-853a-7e64f8c008d6&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=95d6209e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Click Create.
5. In the "**New Instance or Subscription**" wizard:

* **Service**: Select SAP Process Integration Runtime
* **Plan**:  Choose the API plan
* **Runtime Environment**: Select Cloud Foundry
* **Space**: Select your development space.
* **Instance Name**: Enter a name of your choice

6. Click **Next**, then **Create**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2526592735-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FsYuNJuZFJFC32XbiuvZf%252Fuploads%252FIM8ZwGl8fOcA5jUeFYgC%252Fimage.png%3Falt%3Dmedia%26token%3D07cf3701-6387-4f01-b336-f88b10bdfb99&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=47edfe6a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** The `api` plan provides programmatic access to the SAP Process Integration Runtime, allowing you to connect via APIs for integration tasks.
{% endhint %}

#### Assign Required Roles

In the **Parameters** step, assign the required roles based on the target environment.

**For Non-Production Environments**, add the following roles:

| Role                           | Description                                                                                                                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **WorkspacePackagesRead**      | Provides read access to CPI artifacts such as **iFlow, Script Collection, Message Mapping, and Value Mapping**.                                                     |
| **WorkspacePackagesConfigure** | Allows configuration of artifact settings, such as **iFlow configuration parameters**.                                                                              |
| **WorkspacePackagesEdit**      | Enables creation and modification of artifacts such as **iFlow, Script Collection, and Message Mapping**. For **Value Mapping**, it supports only initial creation. |
| **WorkspaceArtifactsDeploy**   | Grants permission to deploy artifacts to runtime, including **iFlow, Script Collection, Message Mapping, and Value Mapping**.                                       |
| **MonitoringDataRead**         | Provides access to message processing logs and monitoring data for **iFlow, SOAP, REST, and OData APIs**.                                                           |
| **MessagePayloadsRead**        | Allows users to view message payloads in monitoring.                                                                                                                |
| **TraceConfigurationRead**     | Provides access to view the current tracing configuration.                                                                                                          |
| **TraceConfigurationEdit**     | Allows modification of tracing settings, including enabling trace configuration.                                                                                    |

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**For Production Environments**, add the following roles to enable deployment access

| Role                           | Description                                                                                                                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **WorkspacePackagesRead**      | Provides read access to CPI artifacts such as **iFlow, Script Collection, Message Mapping, and Value Mapping**.                                                     |
| **WorkspacePackagesConfigure** | Allows users to configure artifact settings, such as **iFlow configuration parameters**.                                                                            |
| **WorkspacePackagesEdit**      | Enables creation and modification of artifacts such as **iFlow, Script Collection, and Message Mapping**. For **Value Mapping**, it supports only initial creation. |
| **WorkspaceArtifactsDeploy**   | Grants permission to deploy artifacts to runtime, including **iFlow, Script Collection, Message Mapping, and Value Mapping**.                                       |
| **MonitoringDataRead**         | Provides access to message processing logs and monitoring data for **iFlow, SOAP, REST, and OData APIs**.                                                           |
| **MessagePayloadsRead**        | Allows users to view message payloads in monitoring.                                                                                                                |

<figure><img src="../../../.gitbook/assets/image (26) (1).png" alt=""><figcaption></figcaption></figure>

#### Create Service Key (for `api` plan)

After the instance is created:

1. Locate the newly created **API instance**.
2. Click the **Actions** menu (**...**) for the instance.
3. Select **Create Service Key**.

<figure><img src="../../../.gitbook/assets/image (1808).png" alt=""><figcaption></figcaption></figure>

4. Enter a service key name of your choice.
5. Leave the parameters field blank.
6. Click **Create**.

<figure><img src="../../../.gitbook/assets/image (1809).png" alt=""><figcaption></figcaption></figure>

7. Open the newly created **Service Instance**.
8. Locate the created **Service Key**.

<figure><img src="../../../.gitbook/assets/image (1815).png" alt=""><figcaption></figcaption></figure>



9. Click **View Credentials** to access the generated authentication details. The following details will be displayed:

* **Client ID**
* **Client Secret**
* **Token URL**

10. These credentials are required for registering the SAP CPI (API access) credential in **ReleaseOwl**.

<figure><img src="../../../.gitbook/assets/image (1805).png" alt=""><figcaption></figcaption></figure>

#### Register **SAP CPI (API Access)** Credential in ReleaseOwl

Credential registration enables secure communication between **ReleaseOwl** and **SAP CPI environments.**&#x20;

**✅ Steps:**

1. Log in to the **ReleaseOwl Platform**.
2. From the Administration menu, go to **Credential Manager**.
3. Click **Register Credential**.
4. Fill in the details:
   * **Credential Name:** Any identifiable name for the credential.
   * **Credential Type:** Select **SAP Cloud Environment**.
   * **Scope** – Select the scope of the credential:
     * **Global** – Visible to all users.
     * **Private** – Visible only to the user who created it.
   * **Authentication Type:** Select OAuth2
   * **Client ID:** Provide the details from the above created **API service key**.
   * **Client Secret:** Provide the details from the above created **API service key**.
   * **Token URL:** Provide the details from the above created **API service key**.
5. Click **Save**.
6. The credential will now appear in your **Credentials List** and will be used for the registering the CPI environment.

<figure><img src="../../../.gitbook/assets/image (1833).png" alt=""><figcaption></figcaption></figure>

### **2. IFLOW Plan** – for managing and testing iFlows

This is used for managing and testing **integration artifacts (iFlows)**.

#### **✅ Steps:**

1. Navigate to your **Subaccount** and select **Instances and Subscriptions**.
2. Click **Create**.
3. In the **New Instance or Subscription** wizard, provide the following details:

* **Service** – Select **SAP Process Integration Runtime**
* **Plan** – Choose **IFLOW**
* **Runtime Environment** – Select **Cloud Foundry**
* **Space** – Select the appropriate space
* **Instance Name** – Enter a name of your choice

<figure><img src="../../../.gitbook/assets/image (1811).png" alt=""><figcaption></figcaption></figure>

4. Click **Next** and then **Create**.

<figure><img src="../../../.gitbook/assets/image (1042).png" alt=""><figcaption></figcaption></figure>

#### Create Service Key (for `IFLOW` plan)

The IFlow plan service key is required to execute test cases from ReleaseOwl.

After the instance is created:

1. Locate the newly created **API instance**.
2. Click the **Actions** menu (**...**) for the instance.
3. Select **Create Service Key**.

<figure><img src="../../../.gitbook/assets/image (1812).png" alt=""><figcaption></figcaption></figure>

4. Enter a service key name of your choice.
5. Leave the parameters field blank.
6. Click **Create**.

<figure><img src="../../../.gitbook/assets/image (1813).png" alt=""><figcaption></figcaption></figure>

7. Click **View Credentials** to access the generated authentication details. The following details will be displayed:
   * **Client ID**
   * **Client Secret**
   * **Token URL**
8. These credentials are required for registering the SAP CPI (Iflow access) credential in **ReleaseOwl**.

<figure><img src="../../../.gitbook/assets/image (1044).png" alt=""><figcaption></figcaption></figure>

#### Register **SAP CPI Credential (Iflow)**  in ReleaseOwl

Credential registration enables secure communication between **ReleaseOwl** and **SAP CPI environments.**&#x20;

**Steps:**

1. Navigate to Credential Manager from the Administration menu in the ReleaseOwl Platform.
2. Click Register Credential.
3. Fill in the following details:
   * **Credential Name:** Any identifiable name for the credential.
   * **Credential Type:** Select SAP Cloud Environment.
   * **Scope** – Select the scope of the credential:
     * **Global** – Visible to all users.
     * **Private** – Visible only to the user who created it.
   * **Authentication Type**: Select OAuth2
   * **Client ID:** Provide the details from the above created IFLOW service key.
   * **Client Secret:** Provide the details from the above created IFLOW service key.
   * **Token URL:** Provide the details from the above created IFLOW service key.
4. Click **Save**.
5. The new credential will now appear in the Credentials List and will be used for the registering the CPI environment.

<figure><img src="../../../.gitbook/assets/image (1834).png" alt=""><figcaption></figcaption></figure>

## **User-based Authentication** (Web Authentication)

**ReleaseOwl** supports different web authentication methods and it is necessary for deploying certain artifact types, such as value mapping, REST, SOAP, and OData APIs. It is also essential for executing test cases associated with the artifacts&#x20;

The supported authentication methods are:

1. SAP Cloud Identity Services-
2. SAP Passport
3. Ping Identity&#x20;

### **1. SAP Cloud Identity Services – Identity Authentication (IAS)**&#x20;

#### **Prerequisites**&#x20;

1. A technical user must be created and available for use in IAS. &#x20;
2. Trust must be established with SAP Identity Authentication Service (IAS). &#x20;
3. Conditional Authentication must be set up.&#x20;

If trust is not already established, follow the steps below:

#### **SAP Cloud Identity Service: Create IAS Instance**

1. Navigate to **Instances & Subscriptions** in your SAP BTP subaccount.
2. Click on the **Create** button.
3. In the **Service** field, select **Cloud Identity Services**.
4. In the **Plan** field, choose **Default** under **Subscriptions**, then click **Next**.
5. Click **Create** to provision the instance.

<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Activate Administrator Account**

1. An **activation email** will be sent to the registered email address.
2. Open the email and click **Activate Account**.
3. Set your password and click on **Continue.**

<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Establish Trust Configuration**&#x20;

To establish trust between the subaccount and the Identity Provider:

* Navigate to the **Security** section in your SAP BTP subaccount.
* Select **Trust Configuration**.
* Click on **Establish Trust**.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fz0fV6pOQUYL4hel73sOp%252Fimage.png%3Falt%3Dmedia%26token%3D5f2e4468-75f3-4114-9cef-18a1e781922b&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=9ecb7158&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Select the Tenant**

* Choose the **subscribed tenant** from the list.
* Click **Next** to create the trust configuration.
* Click **Finish** to complete and create the trust configuration.

<div><figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure></div>

#### **Origin Key Configuration**

* Locate the generated **Origin Key** in the Trust Configuration table you have created.
* Copy the **Origin Key** for use in ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Configure Conditional Authentication

1. Log in to **SAP Cloud Identity Services**.
2. Navigate to **Applications & Resources**.
3. Select "**Applications**."
4. Open the **SAP BTP application** associated with your tenant.

<figure><img src="../../../.gitbook/assets/image (1830).png" alt=""><figcaption></figcaption></figure>

5. Go to the **Trust** section.
6. Navigate to **Conditional Authentication**.

<figure><img src="../../../.gitbook/assets/image (1831).png" alt=""><figcaption></figcaption></figure>

6. In the **Default Authenticating Identity Provider** field, select "**Identity Authentication."**
7. Click **Save** to apply the configuration.

<figure><img src="../../../.gitbook/assets/image (1832).png" alt=""><figcaption></figcaption></figure>

8. Create authentication rules to configure access for the technical user. &#x20;
9. If third-party identity providers are being used, separate authentication rules can also be configured based on the user type. &#x20;

**Example:**&#x20;

* One rule can be created to allow the technical user to authenticate through Identity Authentication. &#x20;
* Another rule can be created to allow business users to authenticate through a third-party identity provider such as Microsoft. &#x20;

<figure><img src="../../../.gitbook/assets/image" alt=""><figcaption></figcaption></figure>

#### Assign Role Collections&#x20;

To create and assign a role collection for the required environment access, follow these steps:

1. Navigate to **Security → Role Collections**.
2. Click **Create**.
3. Enter a name for the role collection and click **Create**.

<figure><img src="../../../.gitbook/assets/image (1797).png" alt=""><figcaption></figcaption></figure>

4. Search for the newly created role collection.
5. Select the role collection name.
6. Click **Edit**.
7.  Add the required roles based on your environment type:

    **For Non-Production Environments**, add the following roles:

| Role                         | Description                                                                                                                 |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **WorkspacePackagesRead**    | Provides read access to CPI artifacts such as **SOAP, REST, and OData APIs**.                                               |
| **WorkspacePackagesEdit**    | Enables creation and modification of artifacts such as **SOAP, REST, and OData APIs**, including **Value Mapping updates**. |
| **WorkspaceArtifactsDeploy** | Grants permission to deploy **SOAP, REST, and OData API artifacts**.                                                        |
| **TraceConfigurationRead**   | Provides access to view the current tracing configuration.                                                                  |
| **TraceConfigurationEdit**   | Allows modification of tracing settings, including enabling trace configuration.                                            |

<figure><img src="../../../.gitbook/assets/image (11) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**For Production Environments**, add the following roles:

| Role                         | Description                                                                                                                 |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **WorkspacePackagesRead**    | Provides read access to CPI artifacts such as **SOAP, REST, and OData APIs**.                                               |
| **WorkspacePackagesEdit**    | Enables creation and modification of artifacts such as **SOAP, REST, and OData APIs**, including **Value Mapping updates**. |
| **WorkspaceArtifactsDeploy** | Grants permission to deploy **SOAP, REST, and OData API artifacts**.                                                        |

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

8. Click **Save** to apply the changes.

#### Configure Role Attributes

* If you do not want to create a [**Role Collection**](credential-management.md#assign-role-collections), use the **Configure Role Attributes** method described below to assign the required roles.
* Click **Edit**.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FQW4csOsTAKJeEFrGVsyq%252Fimage.png%3Falt%3Dmedia%26token%3D8e7c4214-95df-4bdd-8137-f7fd24aabcec&#x26;width=768&#x26;dpr=3&#x26;quality=100&#x26;sign=31946591&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### Configure  Attribute Value

* In **SAP Cloud Identity Services**, navigate to **Applications & Resources** and select your **SAP BTP Subaccount Application**.
* Go to the **Trust** tab and scroll to the **Attributes** section.
* Under **Self-defined Attributes**, configure the **email** attribute with:
  * **Source:** Identity Directory
  * **Value:** Email
* Click **Save**.

<figure><img src="../../../.gitbook/assets/image (1798).png" alt=""><figcaption></figcaption></figure>

#### **Configure Role Attributes**

* In the same **Trust Configuration** screen, scroll to **Attribute Mappings**.
* Click the **"+"** button to add a new mappings.
* Assign the **iadv-content-developer** role only if **SAP Integration Advisor** functionality is required. This role is not mandatory for standard integration scenarios and should be assigned only when Integration Advisor are being used.

| Role                              | Attribute | Operator | Value                         |
| --------------------------------- | --------- | -------- | ----------------------------- |
| PI\_Integration\_Developer        | email     | equals   | Email ID of the service user  |
| <p><br>iadv-content-developer</p> | email     | equals   | Email ID of the Service User  |

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Ensure the email used in role mapping matches the email maintained in SAP Cloud Identity Services.
{% endhint %}

#### Register SAP Cloud Identity Service Credential in Releaseowl

1. Log in to **ReleaseOwl**.
2. Go to **Administration → Credential Manager**.
3. Click on **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4.  Enter the following information:

    * **Credential Type:** SAP IS Web Authentication
    * **User Name:** Cloud Identity Service Username
    * **Password:** Cloud Identity Service Password

    <figure><img src="../../../.gitbook/assets/image (1800).png" alt=""><figcaption></figcaption></figure>


5. **Idp Metadata URL**: To obtain the **IdP Metadata URL**, follow these steps:

* Log in to **SAP Cloud Identity Services**.
* Go to **Applications & Resources.**
* Select **Tenant Settings**.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Open the **OpenID Connect Configuration** section.
* Click on **Show Discovery Endpoint**.
* You will be redirected to a new page.
* Copy the **URL** from the browser address bar — this is your **IdP Metadata URL**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. Paste the copied URL into the **IdP Metadata URL** field in ReleaseOwl.
7. **Origin Key Configuration :** Enter the copied **Origin Key** value in the **Origin Key** field in ReleaseOwl by following the [**Origin Key configuration**](credential-management.md#origin-key-configuration) steps provided above.
8. Click **Save**.

{% hint style="info" %}
**Note : Origin Key** and **IdP Metadata URL** are required only when multiple logon options are enabled in the BTP trust configuration.
{% endhint %}

### 2. **SAP Passport**&#x20;

It enables secure authentication and establishes trusted communication between SAP internal systems and SAP Integration Suite. It ensures system-to-system trust and protects data exchanged across integrated SAP landscapes.

#### Steps to Create SAP Passport

1. Go to **SAP for Me**.
2. Navigate to the **SAP Passport** page (reference link: [_SAP Passport_](https://me.sap.com/app/sappassport)).
3. Enter your **S-User password** when prompted.
4. Click on the **Apply for SAP Passport**.

<figure><img src="../../../.gitbook/assets/image (1640).png" alt=""><figcaption></figcaption></figure>

5. Give your SAP Passport **Password** in that box, then click on **Apply** button your SAP Passport will created.

<figure><img src="../../../.gitbook/assets/image (1638).png" alt=""><figcaption></figcaption></figure>

6. After successful creation, click **Download the SAP Passport**.
7. The passport will be downloaded in **.pfx** format to your system.

<figure><img src="../../../.gitbook/assets/image (1641).png" alt=""><figcaption></figcaption></figure>





#### Register SAP Passport Credential in ReleaseOwl

1. Go to **Credential Manager** in ReleaseOwl.
2. Click **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (1642).png" alt=""><figcaption></figcaption></figure>

3. Fill in the following details:

* **Credential Type:** SAP Passport
* **Password:** Enter the **SAP Passport Password** you provided during the apply process
* **Origin Key**:  For **SAP Passport**, use the **default Identity Provider Origin Key** available in the SAP BTP Trust Configuration.
  1. Locate the default Identity Provider entry.
  2. Copy the corresponding **Origin Key**.
  3. Paste this value into the **Origin Key field in ReleaseOwl**.

<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

* **Certificate:** Upload your downloaded **SAP Passport (.pfx)**

{% hint style="info" %}
**Note:** You **must** keep using the PFX if the server requires client certificate authentication.
{% endhint %}

4. Save the credential.

<figure><img src="../../../.gitbook/assets/image (1802).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :** For role assignment, follow the[ **Role Collection** ](credential-management.md#assign-role-collections)configuration steps provided above.
{% endhint %}

**Assign Role Collections to Users**

After creating the required role collections and assigning the necessary roles, complete the following steps to assign the role collection to a user:

1. In the SAP BTP Cockpit, navigate to:\
   **Security → Users**
2. Select the required user from the **Users** list.
3. On the right-side panel, click the **Role Collections** tab.
4. Click the **three-dot menu (⋯)** in the Role Collections section.
5. Select **Assign Role Collection**.

<figure><img src="../../../.gitbook/assets/image (1803).png" alt=""><figcaption></figcaption></figure>

6. Search for the required role collection that was created earlier.
7. Select the appropriate role collection.
8. Click **Assign** to grant the role collection to the user.

<figure><img src="../../../.gitbook/assets/image (1804).png" alt=""><figcaption></figcaption></figure>

### 3. Ping Identity

Ping Identity enables secure authentication and establishes trusted communication between applications and identity providers using industry-standard protocols such as **OAuth 2.0** and **OpenID Connect (OIDC)**. It ensures secure user and system authentication, supports single sign-on (SSO), and protects access to applications by issuing tokens that contain verified user identity and authorization claims.

#### Prerequisites

Before configuring the integration, ensure that the following prerequisites are completed:

1. Ensure that the **Cloud Identity Services** subscription is active in your SAP BTP subaccount.
2. To establish trust between the subaccount and the Identity Provider, follow the process outlined [above](credential-management.md#establish-trust-configuration).

#### Create Application in PingOne

1. Create your Ping Identity account using the provided[ URL](https://www.pingidentity.com/en/try-ping.html) and log in to **PingOne**.
2. From the left-hand menu, navigate to **Applications**. In the Applications section, click on the **+ (Add Application)** button.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Enter a name of your choice for the application and select the application type based on your requirement, such as **SAML Application** or **OIDC Web App**. For this setup, select **OIDC Web App** and click **Save**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Toggle the application **ON** and navigate to the **Attribute Mappings** tab.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. Click on **Add Mapping**. For the **PingOne** attribute, select **Email Address**, then click **Save**.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Configure Identity Provider in SAP Cloud Identity Services

Follow the steps below to configure an Identity Provider using **Ping Identity (OIDC)** in **SAP Cloud Identity Services (IAS)**.

1. Log in to **SAP Cloud Identity Services**.
2. Navigate to **Applications & Resources**.
3. Open the **SAP BTP application** associated with your tenant.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Configure Conditional Authentication

1. Go to the **Trust** section.
2. Navigate to **Conditional Authentication**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. In the **Default Authenticating Identity Provider** field, select **Ping OIDC**.
4. Click **Save** to apply the configuration.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Create a Corporate Identity Provider**

* Navigate to **Identity Providers** and select **Corporate Identity Providers**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Click on the **+ Create** button.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Enter a name of your choice and select the **Identity Provider Type** as **OpenID Connect compliant**.
* Click **Create** to complete the setup.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Open the newly created Identity Provider.
* Go to the **Trust** section.
* Select **OpenID Connect Configuration**.

<figure><img src="../../../.gitbook/assets/image (1733).png" alt=""><figcaption></figcaption></figure>

**To configure the Discovery URL:**

1. Log in to **Ping Identity** and open the application you created earlier.
2. Navigate to the **Overview** section.
3. Copy the **OIDC Discovery Endpoint**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Paste the copied endpoint into the **Discovery URL** field in OpenID Connect Configuration.

<figure><img src="../../../.gitbook/assets/image (1715).png" alt=""><figcaption></figcaption></figure>

**Configure authentication details:**

1. Under **Client Authentication**, select **Client Secret in Authorization Header**.

<figure><img src="../../../.gitbook/assets/image (1716).png" alt=""><figcaption></figcaption></figure>

2. Log in to **Ping Identity** and open the application you created earlier.
3. Navigate to the **Configuration** section.
4. Copy the **Client ID and Client Secret**.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. Paste the **Client ID** and **Client Secret** obtained from the Ping Identity application.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Click the **Load** button. Once the configuration details are loaded successfully, the **Validate** button will be enabled.&#x20;

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Copy the **OIDC Callback URL**. Then navigate to the application you created and open it. Go to the **Configuration** section and click **Edit**.&#x20;

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Paste the **OIDC Callback URL** into the **Redirect URL** field, and then click **Save** to apply the changes.

<figure><img src="../../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Validate the Configuration

1. Click on the **Validate** button.

<figure><img src="../../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. If the configuration is correct, validation will succeed and you will see the confirmation screen (as shown in the image below)



<figure><img src="../../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Configure Identity Provider using Ping Identity (SAML) in SAP Cloud Identity Services

Follow the steps below to configure **Ping Identity as a SAML Identity Provider** in SAP Cloud Identity Services.

**Log in to SAP Cloud Identity Services**

1. Log in to **SAP Cloud Identity Services**.
2. Navigate to **Applications & Resources**.
3. Select "**Applications**."
4. Open the **SAP BTP application** associated with your tenant.

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Configure Conditional Authentication

1. Go to the **Trust** section.
2. Navigate to **Conditional Authentication**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. In the **Default Authenticating Identity Provider** field, select **Oping Saml.**
4. Click **Save** to apply the configuration.

<figure><img src="../../../.gitbook/assets/image (1718).png" alt=""><figcaption></figcaption></figure>

**Download Metadata from SAP Cloud Identity Services**

1. Navigate to **Applications & Resources**.
2. Select **Tenant Settings**.

<figure><img src="../../../.gitbook/assets/image (1719).png" alt=""><figcaption></figcaption></figure>

3. Go to **Authentication**.
4. Navigate to **Single Sign-On**.
5. Click **Download Metadata File**.
6. This metadata file will be used to configure the application in **Ping Identity**.

<figure><img src="../../../.gitbook/assets/image (1721).png" alt=""><figcaption></figcaption></figure>

**Create Application in Ping Identity**

1. Log in to **Ping Identity**.
2. From the left-hand menu, navigate to **Applications**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Click the **+ (Add Application)** button.
4. Enter a **Name** for the application.
5. Select **Application Type** based on your requirement.
6. For this setup: Select **SAML Application**
7. Click **Configure**

<figure><img src="../../../.gitbook/assets/image (1722).png" alt=""><figcaption></figcaption></figure>

**Configure SAML Settings in Ping Identity**

During SAML configuration, choose **one of the following options**.

**Option 1: Import Metadata File**

1. Select **Import Metadata**.
2. Click **Select File**.
3. Upload the **metadata file downloaded from SAP Cloud Identity Services**.

<figure><img src="../../../.gitbook/assets/image (1723).png" alt=""><figcaption></figcaption></figure>

4. Click **Save.**

<figure><img src="../../../.gitbook/assets/image (1724).png" alt=""><figcaption></figcaption></figure>

**Option 2: Import Metadata from URL**

1. In **SAP Cloud Identity Services**, navigate to:
   * **Authentication**
   * **Single Sign-On**
2. Open **OpenID Connect Configuration**.
3. Click **Show Discovery Endpoint**.
4. Copy the **metadata URL**.

<figure><img src="../../../.gitbook/assets/image (1725).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1726).png" alt=""><figcaption></figcaption></figure>

5. Paste the URL into the **Import from URL** field in **Ping Identity**.

<figure><img src="../../../.gitbook/assets/image (1727).png" alt=""><figcaption></figcaption></figure>

* Toggle the application **ON** and navigate to the **Attribute Mappings** tab.

<figure><img src="../../../.gitbook/assets/image (1730).png" alt=""><figcaption></figcaption></figure>

* Click on **Add Mapping**. For the **PingOne** attribute, select **Email Address**, then click **Save**.

<figure><img src="../../../.gitbook/assets/image (1731).png" alt=""><figcaption></figcaption></figure>

#### **Create a Corporate Identity Provider**

* Navigate to **Identity Providers** and select **Corporate Identity Providers**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Click on the **+ Create** button.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Enter a name of your choice and select the **Identity Provider Type** as **SAML 2.0 compliant**.
* Click **Create** to complete the setup.

<figure><img src="../../../.gitbook/assets/image (1732).png" alt=""><figcaption></figcaption></figure>

* Go to the **Trust** section.
* Select **SAML 2.0 Configuration**.

<figure><img src="../../../.gitbook/assets/image (1734).png" alt=""><figcaption></figcaption></figure>

**Upload Metadata from Ping Identity**

1. Log in to **Ping Identity**.
2. Navigate to the **Application Overview** section.
3. Scroll down and **Download the Metadata file**.

<figure><img src="../../../.gitbook/assets/image (1736).png" alt=""><figcaption></figcaption></figure>

**Upload Metadata File**

1. In **SAP Cloud Identity Services**, click the **Browse** button.
2. Select the **downloaded metadata file**.
3. Upload the file.

<figure><img src="../../../.gitbook/assets/image (1739).png" alt=""><figcaption></figcaption></figure>

**Configure Metadata URL**

1. In **Ping Identity**, copy the **IdP Metadata URL**.

<figure><img src="../../../.gitbook/assets/image (1737).png" alt=""><figcaption></figcaption></figure>

* Paste the URL into the **Metadata URL field** in **SAP Cloud Identity Services**.

<figure><img src="../../../.gitbook/assets/image (1735).png" alt=""><figcaption></figcaption></figure>



* Click **Save** to complete the configuration.

<figure><img src="../../../.gitbook/assets/image (1738).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** For **Ping Identity** configuration, ensure that the **email** attribute is mapped to **Email Address** in the application attribute mappings. Additionally, verify that the email used in role mapping matches the service user email configured in Ping Identity to ensure proper role assignment and authentication.

* For role assignment, follow the[ **Role Collection** ](credential-management.md#assign-role-collections)configuration steps provided above.
{% endhint %}
