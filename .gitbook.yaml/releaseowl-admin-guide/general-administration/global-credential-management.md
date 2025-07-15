# Global Credential Management

There are several third-party sites and applications that can interact with Release Owl, like artifact repositories, cloud-based storage systems, services etc. The admin can configure credentials in the application for use by Release Owl. Once the user adds/configures the credentials in Release Owl, the credentials can be used by Pipeline projects to interact with the 3rd party applications.

## **Registering the Credential Manager**

1. **Accessing the Credential Manager**:
   * Admin users can switch to the **Administration View** to access the Credential Manager.

<figure><img src="../../.gitbook/assets/image (337).png" alt=""><figcaption></figcaption></figure>

* Click the **Credential Manager** menu option on the left-hand pane to view the list of registered credentials.

<figure><img src="../../.gitbook/assets/image (1381).png" alt=""><figcaption></figcaption></figure>

**Show** : The **Show** dropdown is used to **filter the credential list** based on specific credential types or categories. This helps users quickly view only the relevant credentials among possibly many saved credentials. For example, you might be able to filter by:

* **Jira** – Only show credentials related to Jira integrations.
* **SAP Cloud Environment** – Show only SAP BTP credentials.
* **Ui Path** – Show credentials used for automation purposes.

**Search** : The **Search** field allows users to perform a **keyword-based search** to find a specific credential by its name or a part of its name. This is particularly useful when there are many credentials registered, making it difficult to manually scroll and locate a specific one.

2. **Registering a New Credential**:

* To add a new credential, click **Register Credential**, available on the right-hand panel.
* The following screen will be displayed:

<figure><img src="../../.gitbook/assets/image (339).png" alt=""><figcaption></figcaption></figure>

## **Credential Types**

ReleaseOwl supports various credential types for registration. Below, we will explore each type in detail.

### **Version Control**

1. Click on the **"Register Credential"** button.
2. Fill in the required fields:
   * **Credential Name**: Enter a name of your choice.
   * **Credential Type**: Select **Version Control**.
   * **Username**: Enter your GitHub/Bitbucket username.
   * **Password**: Enter your GitHub/Bitbucket password.
3. Save the configuration to enable access to your GitHub/Bitbucket account.

<figure><img src="../../.gitbook/assets/image (340).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
For information on setting up the tokens in GITHub, please refer to the link -[https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
{% endhint %}

{% hint style="info" %}
For information on setting up the tokens in BitBucket, please refer to the link - [https://confluence.atlassian.com/bitbucketserver072/personal-access-tokens-1005335924.html](https://confluence.atlassian.com/bitbucketserver072/personal-access-tokens-1005335924.html)
{% endhint %}

### **Azure DevOps**

1. Click on the **"Register Credential"** button.
2. Fill in the required fields:
   * **Credential Name**: Enter a name of your choice.
   * **Credential Type**: Select **Azure DevOps**.
   * **Username**: Enter your Azure DevOps username.
   * **Token**: Provide your Azure DevOps personal access token (PAT).
   * **Host URL**: Enter the Azure DevOps organization URL (e.g., `https://dev.azure.com/)`.
3. Save the configuration to enable access to your Azure DevOps account.

<figure><img src="../../.gitbook/assets/image (341).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
For information on setting up the tokens in Azure DevOps, please refer to the link -[https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops\&tabs=Windows](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops\&tabs=Windows)
{% endhint %}

### **SAP Cloud Environment**

#### Credential Registration for SAP Cloud Environment.

1. Click on the **"Register Credential"** button.
2. Fill in the required fields:
   * **Credential Name**: Enter a name of your choice.
   * **Credential Type**: Select **SAP Cloud Environment**.
   * **Authentication Type**: Choose either **Basic** or **OAuth2**.
     *   If **Basic** is selected:

         * Provide your **Username** and **Password** (SAP BTP credentials).

         <figure><img src="../../.gitbook/assets/image (342).png" alt=""><figcaption></figcaption></figure>


     * If **OAuth2** is selected:
       * **Client ID**: Provide the details from the created API service key in the SAP BTP cockpit.
       * **Client Secret**: Provide the details from the created API service key in the SAP BTP cockpit.
       * **Token URL**: Provide the details from the created API service key in the SAP BTP cockpit.
3. Click save.
4. The credential will appear in the List of Credentials.

<figure><img src="../../.gitbook/assets/image (344).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
OAuth 2 provides better security than basic authentication as the initial requests for credentials are made under the SSL protocol and its access object is a transitory token.

&#x20;For more detailed guidance on creating service instances and service keys, please refer to the following resource: [Creating Service Instance and Service Key for Inbound Authentication | SAP Help Portal](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/creating-service-instance-and-service-key-for-inbound-authentication)&#x20;
{% endhint %}

### **SAP HANA XSA Environment**

1. Click on the **"Register Credential"** button.
2. Fill in the required fields:
   * **Credential Name**: Enter a name of your choice.
   * **Credential Type**: Select **SAP HANA XSA Environment**.
   * **Username**: Enter your **SAP BTP** username.
   * **Password**: Enter your **SAP BTP** password.
3. Click **Save**.
4. The credential will appear in the **List of Credentials**.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **SonarQube On-Prem**

1. Click on the **"Register Credential"** button.
2. Fill in the required fields:
   * **Credential Name**: Enter a name of your choice.
   * **Credential Type**: Select **Static Code Analysis -SonarQube** .
   * **Username**: Enter your SonarQube username.
   * **Token**: Provide your SonarQube authentication token.
   * **Host URL**: Enter the URL of your SonarQube instance (either On-Premise or Cloud).
   * **Hosting Type**: Choose either **On-Premise** or **Cloud**, depending on your SonarQube setup.
3. Save the changes to configure and enable access to your SonarQube On-Prem account.

<figure><img src="../../.gitbook/assets/image (345).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Further information on getting the user token for SonarQube can be found @[https://docs.sonarqube.org/6.7/UserToken.html](https://docs.sonarqube.org/6.7/UserToken.html)
{% endhint %}

### **Transport Manager Credential**

1. **Click on the "Register Credential"** butto&#x6E;**.**
2. **Fill in the required fields:**
   * **Credential Type**: Select **Transport Manager Credential** from the dropdown.
   * **Credential Name**: Provide any name of your choice.
   * **Username**: Enter your username for the Transport Domain Controller system.
   * **Password**: Provide the password associated with your username.
3. **Click Save** to finalize the setup and enable access to your Transport Domain Controller system.\


<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **JIRA**

1. Click on the **"Register Credential"** butto&#x6E;**.**
2. Fill in the required fields:
   * **Credential Name**: Enter a name of your choice .
   * **Credential Type**: Select **Jira** from the dropdown.
   * **Authentication Type**: Choose either **Basic** or **OAuth2**.
3.  If **Basic** is selected:

    * **Username**: Provide the username associated with the credential (e.g., Jira account username).
    * **Password/API Token**: Enter the password or API token for authentication with the chosen system.
    * **Jira URL**: Provide the Jira instance URL, such as: `https://Saparate.atlassian.net`.
    * **Proxy Type**: Select the proxy type for communication .

    <figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>


4. If OAuth2 is selected:
   1. **Client ID**: Obtain the Client ID from the **Atlassian Developer Console**.
   2. **Client Secret**: Obtain the Client Secret from the **Atlassian Developer Console**
   3. **Jira URL**: Provide the Jira instance URL, such as: `https://Saparate.atlassian.net`.
   4. **Proxy Type**: Select the proxy type for communication .
5. **Click Save** button to save the credentials.

<figure><img src="../../.gitbook/assets/image (349).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
For information on setting up the tokens in JIRA, please refer to the link - [https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-admin-guide/integrations/jira-cloud](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-admin-guide/integrations/jira-cloud)
{% endhint %}

### **ServiceNow**

1. **Click on the "Register Credential" button.**
2.  **Fill in the following fields:**

    * **Credential Name**: Enter a name for your reference in ReleaseOwl.
    * **Credential Type**: Select **ServiceNow**.
    * **Authentication Type**: Choose either:
      * **OAuth2**: For token-based authentication.
      * **Basic Authentication**: For username and password-based access.
    * **Instance URL**: Enter your ServiceNow hosting URL.



<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **For  OAuth2 Authentication**

1. Log in to your ServiceNow account.
2. Navigate to **ALL** and search for **Application Registry**.
3. Click on **Application Registry**.

<figure><img src="../../.gitbook/assets/image (324).png" alt=""><figcaption></figcaption></figure>

4. Locate and click on **ReleaseOwl** in the list of OAuth Registries.
5. View the **Client ID** and **Client Secret** associated with ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (327).png" alt=""><figcaption></figcaption></figure>

6. Copy the **Client ID** and **Client Secret** and paste them into the corresponding fields in the **Register Credential** form in ReleaseOwl under **OAuth2 Authentication**.
7. Click the **Save** button.

<figure><img src="../../.gitbook/assets/image (328).png" alt=""><figcaption></figcaption></figure>

8. Click **Generate Token**.
9. A popup will appear prompting you to enter your ServiceNow **username** and **password**.
10. Enter your credentials and click the **Generate** button.



<figure><img src="../../.gitbook/assets/image (329).png" alt=""><figcaption></figcaption></figure>

3. The generated token will be available in the **Manage Tokens** section under **ALL** in the ServiceNow website.

<figure><img src="../../.gitbook/assets/image (330).png" alt=""><figcaption></figcaption></figure>

#### **For  Basic Authentication**

1. Log in to your ServiceNow instance.
2. Click the **Request Instance** button.

<figure><img src="../../.gitbook/assets/image (331).png" alt=""><figcaption></figcaption></figure>

3. You will receive an email containing the instance details.
4. In the email, locate the section containing your **username** and **password** details.

<figure><img src="../../.gitbook/assets/image (332).png" alt=""><figcaption></figcaption></figure>

5. Copy these credentials and paste them into the corresponding fields in the **Register Credential** form in ReleaseOwl under **Basic Authentication**.

<figure><img src="../../.gitbook/assets/image (333).png" alt=""><figcaption></figcaption></figure>

### **Ui path**

1. In the **Credential Manager**, click on **Register Credential**.&#x20;
2. **Fill in the Credential Details**:&#x20;
   1.  Enter the following details: &#x20;

       1. **Credential Name**: Enter a name for your credential.&#x20;
       2. **Credential Type**: Select the appropriate credential type.&#x20;
       3. **Token URL**: Enter the following URL: [https://account.uipath.com](https://account.uipath.com/).&#x20;

       <figure><img src="../../.gitbook/assets/image (313).png" alt=""><figcaption></figcaption></figure>
3. **Obtain Client ID and Client Secret**:&#x20;
   1. Log in to your **UiPath Orchestrator** account.&#x20;
   2.  Click on your **profile icon** (usually in the top-right corner) and select **Preferences.**

       <figure><img src="../../.gitbook/assets/image (315).png" alt=""><figcaption></figcaption></figure>
   3.  In **Preferences**, go to the **Privacy & Security** section.&#x20;

       <figure><img src="../../.gitbook/assets/image (316).png" alt=""><figcaption></figcaption></figure>
   4. Click on **View API Access**.&#x20;
4.  Here, you will find your **User Key**, which acts as both the **Client ID** and **Client Secret**.&#x20;

    <figure><img src="../../.gitbook/assets/image (317).png" alt=""><figcaption></figcaption></figure>
5. **Copy and Paste Credentials**:&#x20;
   6.  Copy the **Client ID** and **Client Secret** from the **View API Access** section in UiPath. &#x20;

       <figure><img src="../../.gitbook/assets/image (321).png" alt=""><figcaption></figcaption></figure>
   7. Return to the Register Credential page in ReleaseOwl.
   8. Paste the Client ID and Client Secret into the appropriate fields.
6. Click **Save** to register the credential.&#x20;

<figure><img src="../../.gitbook/assets/image (320).png" alt=""><figcaption></figcaption></figure>

### **Docusign**

1. Click on Credential Manager and then Register Credential.

<figure><img src="../../.gitbook/assets/image (295).png" alt=""><figcaption></figcaption></figure>

2. Fill in the fields:

* Credential Name: Enter a reference name of your choice.
* Credential Type: Choose DocuSign.

<figure><img src="../../.gitbook/assets/image (296).png" alt=""><figcaption></figcaption></figure>

**Retrieve Client ID and Secret**

1. Log in to DocuSign and click the “**Admin**”button.

<figure><img src="../../.gitbook/assets/image (297).png" alt=""><figcaption></figcaption></figure>

2. Navigate to Integrations and select Apps and Keys.

<figure><img src="../../.gitbook/assets/image (298).png" alt=""><figcaption></figcaption></figure>

3. Click Add App and Integration Key.

<figure><img src="../../.gitbook/assets/image (299).png" alt=""><figcaption></figcaption></figure>

4. Copy the Integration Key which is nothing but the client id

<figure><img src="../../.gitbook/assets/image (300).png" alt=""><figcaption></figcaption></figure>

5. Click on the “**Add Secret Key**” button which is nothing but the Client Secret

<figure><img src="../../.gitbook/assets/image (301).png" alt=""><figcaption></figcaption></figure>

6. Set the Redirect URI to:

* https://na3.releaseowl.com/rateloginserver/api/oauth/accesstoken

7. Check all allowed HTTP methods and click Save.

<figure><img src="../../.gitbook/assets/image (302).png" alt=""><figcaption></figcaption></figure>

&#x20;

**Save Credentials in ReleaseOwl**

1. &#x20;After creating the app successfully, click on the Actions button, then select Edit.

&#x20;

<figure><img src="../../.gitbook/assets/image (304).png" alt=""><figcaption></figcaption></figure>

2\.  In the Apps and Keys section, locate:

* **API Account ID**: This is the Account ID.
* **Account Base URL**: This is the API Host URL.
* Copy these URLs to paste them into the credential manager.

<figure><img src="../../.gitbook/assets/image (306).png" alt=""><figcaption></figcaption></figure>

&#x20;

3\.  Use the following URLs:

* **Token URL**: The DocuSign URL with /oauth/token.
* **Authorization URL**: The DocuSign URL with /oauth/auth.

4. Copy all the credentials, paste them into the Register Credential, and click the Save button.

<figure><img src="../../.gitbook/assets/image (309).png" alt=""><figcaption></figcaption></figure>

**Generate a Token**

1. In Credential Manager, select the created credential.
2. Click Generate Token to verify if the entered credentials are correct.

<figure><img src="../../.gitbook/assets/image (310).png" alt=""><figcaption></figcaption></figure>

### **CRT**

1. Click on the **"Register Credential"** button.
2. Fill in the required fields:

* **Credential Name**: Enter a name of your choice.
* **Credential Type**: Select **CRT.**
* **Username**: Enter your CRT username.
* **Personal Access key :** Provide the required access token ( found in your CRT account).

<figure><img src="../../.gitbook/assets/image (226).png" alt=""><figcaption></figcaption></figure>

### 4Me

Follow these steps to register your 4Me credentials in the system:

1. Click on the "Register Credential" button.&#x20;
2. Fill in the Required Fields

| **Field**           | **Description**                                                |
| ------------------- | -------------------------------------------------------------- |
| **Credential Name** | Enter a name of your choice.                                   |
| **Credential Type** | Select **4Me** from the list.                                  |
| **Account**         | Enter **WDC**.                                                 |
| **Access Token**    | Provide the required access token (found in your 4Me account). |
| **GraphQL URL**     | Enter: `https://graphql.4me.demo.com`                          |
| **4Me API URL**     | Enter: `https://api.4me-demo.com`                              |

<figure><img src="../../.gitbook/assets/image (172).png" alt=""><figcaption></figcaption></figure>

### Freshservice

#### **1. Open the Credential Registration Page**

* Click on the **"Register Credential"** button.

**2. Fill in the Required Fields**

| **Field**               | **Description**                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------ |
| **Credential Name**     | Enter a name of your choice.                                                         |
| **Credential Type**     | Select **Freshservice** from the list.                                               |
| **Authentication Type** | Select **Basic** authentication.                                                     |
| **API Key**             | Enter your Freshservice API key.                                                     |
| **Password**            | Enter the associated password.                                                       |
| **Instance URL**        | Enter your Freshservice instance URL (e.g., https://\<yourdomain.freshservice.com>). |

<figure><img src="../../.gitbook/assets/image (505).png" alt=""><figcaption></figcaption></figure>

### **Others**

1. Click on the **"Register Credential"** button.
2. **Fill in the required fields:**
   * **Credential Type**: Select **Others** for any basic authentication not covered by the available options.
   * **Credential Name**: Provide any name of your choice (e.g., "Custom Access").
   * **Username**: Enter your username for the required account.
   * **Password**: Enter the password associated with your username.
3. **Click Save** to finalize the setup and enable access to your required account.

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Edit**

You can edit the credentials by clicking on the registered credential. This will allow you to make and save any necessary changes.

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Delete**

You can delete any credential by clicking the delete icon seen against that credential.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note: Edit** and **Delete** options are available only for the users with appropriate user roles.
{% endhint %}
