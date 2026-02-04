# Integration Environment Registration

To register the SAP Integration Environment, you must first register the CPI credential. Follow the[ link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-integration-suite/administration/credential-management)and complete the credential setup.

## CPI Environment Registration <a href="#pdf-page-della43ge2ynalx23r7p-cpi-environment-registration" id="pdf-page-della43ge2ynalx23r7p-cpi-environment-registration"></a>

&#x20;**Purpose** :Enable communication with the CPI Environments.

1. Navigate to **Environments** from the **Administration** menu.
2. Select CPI environment and click on register **CPI** environment.
3. Provide the following details:

| **Field**                               | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                                | Enter a unique name for the SAP CPI Environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Auth Type**                           | Select the authentication type: **Basic Auth** or **OAuth2**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **API URL**                             | Provide the **API URL** for connecting to the SAP CPI Environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Enable Test Automation** _(Optional)_ | Toggle to enable or disable test automation capabilities.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **IFLOW OAuth Credential**              | Select the OAuth credentials used for IFLOW authentication.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **IFLOW URL**                           | Enter the IFLOW URL from the service key.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **SSO URL**                             | Provide the Single Sign-On (SSO) URL for authentication. _**Note**_**: The setup process is outlined in the section below.**                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **IDP Auth Email Address / Group Name** | The group name or email address configured in the '**Value**' section under **User Groups** or **Attribute Mappings** should also match the corresponding group or email configuration in the IDP Auth Email Address/Group Name within the ReleaseOwl CPI environment registration page.                                                                                                                                                                                                                                                                                            |
| **Integration Advisor**                 | Enable Integration Advisor to provide the Host URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Host URL**                            | The host URL is the base address of your SAP Integration Suite instance. _(Example: https://\<subdomain>.integrationsuite-\<region>.cfapps.\<domain>.hana.ondemand.com)_                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Enable Git** _(Optional)_             | Enable this option to integrate Git with the environment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Git Credential**                      | Select the credential for accessing the Git repository.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Repository URL**                      | Provide the Git repository URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Branch**                              | Specify the branch to be used for the integration.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Environment Type**                    | Select the environment type (e.g., **Dev**, **QA**, **Prod**).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Web Authentication**                  | <p>There are <strong>three authentication types</strong> available for CPI Web Authentication in ReleaseOwl:</p><ol><li><strong>None</strong> – No authentication is required.</li><li><strong>Custom Identity Provider (Custom IdP)</strong> – Authentication is performed using a customer-configured Identity Provider.</li><li><strong>SAP Cloud Identity Provider</strong> – Authentication is performed using SAP Cloud Identity Services (IAS).</li><li><strong>SAP Passport</strong> – Authentication is performed using browser-based SAP Passport certificates.</li></ol> |

<figure><img src="../../../.gitbook/assets/image (1649).png" alt=""><figcaption></figcaption></figure>

### Custom Identity Provider (IDP) Setup and Configuration <a href="#pdf-page-della43ge2ynalx23r7p-toc190778976" id="pdf-page-della43ge2ynalx23r7p-toc190778976"></a>

A Custom IDP (Identity Provider) must be configured to allow secure authentication and authorization for users who interact with the Integration Suite (CPI) instance through ReleaseOwl.

**Use Case:** This is particularly useful for executing test cases, simulation testing and updating value mappings as part of the pipeline.

#### Steps to Configure a Custom Identity Provider (IDP)

A **Custom Identity Provider (IDP)** is required for deploying certain artifact types—such as **Value Mapping**, **REST**, **SOAP**, and **OData APIs**—as well as for executing test cases associated with these artifacts via ReleaseOwl.

1. **Download SAP BTP SAML Metadata**

* Navigate to the **Security** section of your SAP BTP Subaccount.
* Go to **Trust Configuration**.
* Click **Download SAML Metadata** to download the BTP metadata file.

<figure><img src="../../../.gitbook/assets/image (1100).png" alt=""><figcaption></figcaption></figure>

2. **Extract the SAP BTP SSO URL**

* Open the downloaded SAML metadata XML file in a text editor (e.g., Notepad++, VS Code, or a browser).
* Search for the `<AssertionConsumerService>` tag.
* In this tag, locate the **Location** attribute. The value of this attribute is your **SAP BTP SSO URL**.

<figure><img src="../../../.gitbook/assets/image (1099).png" alt=""><figcaption></figcaption></figure>

* Copy the extracted **SSO URL**.
* Paste it into the **SSO URL** field in the **SAP CPI Environment**.

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

* For the **IDP Auth Email Address/Group Name** field, enter the **exact value that your Identity Provider sends in the SAML/OIDC assertion** for the user.
* This value must match the **group name or email address defined in the&#x20;**_**Value**_**&#x20;field** of the **User Groups** or **Attribute Mappings** configuration in your IDP.\
  ReleaseOwl (or SAP BTP) uses this returned attribute value to validate user authorization.
* Refer to the _**Assign Role Collections**_**&#x20;section** to ensure that the mapped group/attribute is correctly linked to the required role collections.

<figure><img src="../../../.gitbook/assets/image (1652).png" alt=""><figcaption></figcaption></figure>

* After entering all the required details, click **Save**. Once saved, a **Test** button will appear. Use this button to verify whether the provided credentials and configuration are correct. Click **Test** to validate the connection.

<figure><img src="../../../.gitbook/assets/image (1653).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1654).png" alt=""><figcaption></figcaption></figure>

* Upon successful validation, a **Download** option will be available to download the **tenant-specific metadata** and the **SAP CPI environment descriptor file**.

<figure><img src="../../../.gitbook/assets/image (1494).png" alt=""><figcaption></figcaption></figure>

3. **Create Trust Configuration in SAP BTP**

* Return to **Trust Configuration** in the SAP BTP Cockpit.
* Click **New Trust Configuration** and select **New** **SAML Trust Configuration**.

<figure><img src="../../../.gitbook/assets/image (1103).png" alt=""><figcaption></figcaption></figure>

* Upload the **ReleaseOwl CPI Environment metadata XML** file.
* **Uncheck** the option **"Available for User Logon"** to prevent this IDP from appearing on the SAP login screen.
* Click **Save**.

<figure><img src="../../../.gitbook/assets/image (1495).png" alt=""><figcaption></figcaption></figure>

4. **Assign Role Collections (Choose One of the Methods Below)**

To assign role collections, you can choose **one** of the following methods:

**Method 1: Assign Role Collections using User Groups**

* Open the newly created **Custom IDP for Applocations** and click **Edit**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Go to the **User Groups** section and Click the **"+"** button to add a new mapping.
* Configure the mappings like the example below:

| Role Collection            | Attribute | Operator | Value      |
| -------------------------- | --------- | -------- | ---------- |
| PI\_Integration\_Developer | Groups    | equals   | group name |

**Method 2: Assign Role Collections using Attribute Mapping (Email-Based)**

* In the same **Trust Configuration** screen, scroll to **Attribute Mappings**.
* Click the **"+"** button to add a new mapping.
* Define mappings like this:

| Role Collection            | Attribute    | Operator | Value                                 |
| -------------------------- | ------------ | -------- | ------------------------------------- |
| PI\_Integration\_Developer | emailAddress | equals   | The email ID of the **service user**  |

**Method 3: Configure Custom Role Collection Mappings for the IdP**

You can configure granular permissions by creating the custom role collection with the below required roles:

| **Custom Role Collection**                       | **Required Roles**                                                                                            |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| Roles required for ReleaseOwl CPI test generator | <p></p><ul><li>Trail-content-adminstrator</li><li>PI_Integration_Developer</li><li>PI_Administrator</li></ul> |

<figure><img src="../../../.gitbook/assets/image (1607).png" alt=""><figcaption></figcaption></figure>

6. The group name or email address configured in the '**Value**' section under **User Groups** or **Attribute Mappings** should match the corresponding group or email configuration in the **IDP Auth Email Address/Group Name** on the ReleaseOwl CPI environment registration page.

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

### SAP Cloud Identity Provider

ReleaseOwl seamlessly integrates with **SAP Cloud Identity Services** to support secure authentication and identity management across deployment pipelines. To register the SAP Cloud Identity environment, you must first register the Cloud Identity credential. Follow the[ link](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-integration-suite/administration/credential-management) and complete the credential setup.

### **Trust Configuration in SAP BTP**

1. Go to **Trust Configuration** in your SAP BTP subaccount.
2. Click on **Establish Trust**.

<figure><img src="../../../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

#### **Configure Trust**

1. Select your **Cloud Identity Service tenant** → click **Next**.

<figure><img src="../../../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

2. Select your **Cloud Identity Service domain** → click **Next**.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

3. Under **Configuration Parameters**:
   * Set **Origin Key = sap.custom**
   * Click **Next** and then **Finish**.

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

#### **OpenID Connect Settings**

1. &#x20;A new trust configuration will be created using the origin key `sap.custom` with the OpenID Connect (OIDC) protocol.

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

2. In the **Parameters** section, enable **Available for User Logon.**&#x20;

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

3. Navigate to **Attribute Mappings** and fill in the required mappings:

| **Related Role**                                                                                                      | **Attribute Name** | **Value**                         | **Operator** |
| --------------------------------------------------------------------------------------------------------------------- | ------------------ | --------------------------------- | ------------ |
| <ul><li>Trail-content-adminstrator<br></li><li>PI_Integration_Developer</li><li>PI_Administrator</li></ul><p><br></p> | email              | Your Cloud Identity Service email | equals       |

4. Click **Save** to update the configuration.

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

### **Access Applications**

1. Log in to your **Cloud Identity Service tenant**.
2. Navigate to **Applications & Resources → Applications**.

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

3. A new bundled application will be automatically created and associated with the trust configuration and linked to the corresponding SAP BTP subaccount.

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

#### **Configure Single Sign-On**

1. Open the newly created application.
2. Go to **Single Sign-On → Subject Name Identifier**.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Configure as follows:

* **Source (Primary):** Identity Directory
* **Attribute (Primary):** Email
* **Source (Fallback):** Identity Directory
* **Attribute (Fallback):** Email

4. Click on the **Save** button.&#x20;

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Configure Conditional Authentication**

1. Go to **Trust** → **Conditional Authentication**.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Set **Default Identity Provider = Identity Authentication**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Environment Registration

1. Go to the SAP CPI Environment and click on the **Register SAP CPI Environment**.&#x20;

<figure><img src="../../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

2. **Web Authentication:** Select **SAP Cloud Identity Provider**.
3. **Credential:** Choose the **SAP Cloud Identity Credential** that you registered earlier.
4. Click on the **Create** button.

<figure><img src="../../../.gitbook/assets/image (1650).png" alt=""><figcaption></figcaption></figure>

### SAP Passport

ReleaseOwl seamlessly integrates with **SAP Passport** to enable secure certificate-based authentication for SAP CPI environments. To register the SAP Passport–based authentication, you must first generate your SAP Passport and register it as a credential in ReleaseOwl. Follow the [link](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-integration-suite/administration/credential-management) and complete the credential setup.

### Environment Registration

1. Go to the SAP CPI Environment and click on the **Register SAP CPI Environment**.&#x20;
2. Click on **Register SAP CPI Environment**.

<figure><img src="../../../.gitbook/assets/image (1644).png" alt=""><figcaption></figcaption></figure>

3. Under **Web Authentication**, select **SAP Passport**.
4. Under **Credential**, select the **SAP Passport Credential** you created earlier.
5. Click on the **Create** button to complete the configuration.

<figure><img src="../../../.gitbook/assets/image (1651).png" alt=""><figcaption></figcaption></figure>

### Adding Environments to Project

* To add environments to project, follow the [link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-admin-guide/general-administration/project-management)and complete the setup.

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
**Note :** On clicking Permissions in the above screen, one can know the actions that the user role can perform each for the available features such as Transport Management, Change Management, Pipelines, Release Management.
{% endhint %}

