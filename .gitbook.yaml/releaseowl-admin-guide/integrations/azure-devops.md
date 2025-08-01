# Azure DevOps

Azure DevOps provides a comprehensive suite of tools for collaboration, agile project management, code versioning, and deployment. Integrating Azure DevOps with ReleaseOwl ensures seamless synchronization of user stories, project management tasks, and updates between both platforms.

### **Credential Configuration**

To integrate Azure DevOps with ReleaseOwl, follow these steps to create a credential:

1. **Navigate to Credential Manager**:
   * Go to **Administration** > **Credential Manager** in ReleaseOwl.
2.  **Register a Credential**:

    * Click on **Register Credential**.

    <figure><img src="../../.gitbook/assets/image (531).png" alt=""><figcaption></figcaption></figure>
3. **Fill in the Required Fields**:
   * **Credential Name**: Provide a descriptive name for the credential (e.g., "Azure DevOps Credential").
   * **Credential Type**: Choose **Azure DevOps** from the dropdown.
   * **URL**: Enter the Azure DevOps Organization URL (e.g., `https://dev.azure.com/<your-organization>`).
   * **Authentication**: Enter the required authentication parameters, such as a **Personal Access Token (PAT)**.
4.  **Save the Credential**:

    * Click **Save** to store the credential.



<figure><img src="../../.gitbook/assets/image (532).png" alt=""><figcaption></figcaption></figure>

### **Azure DevOps Project Integration**

To link an Azure DevOps project to a ReleaseOwl project, follow these steps:

1.  **Navigate to the Project Settings**:

    * Select the required project in ReleaseOwl.
    * Go to **Project Settings**.

    <figure><img src="../../.gitbook/assets/image (802).png" alt=""><figcaption></figcaption></figure>


2. &#x20;**Go to Integration Tab and Fill in the Required Fields:**
   * **Name**: Enter a name for the integration (e.g., "Azure DevOps Integration").
   * **Description**: Add a description for the integration.
   * **External System**: Select **Azure DevOps**.
   * **Credential**: Choose the previously registered Azure DevOps credential from the dropdown.
   * **Host URL**: Enter the Azure DevOps Organization URL (e.g., `https://dev.azure.com/<your-organization>`).
   * **External Project**: Select the Azure DevOps project to integrate from the list.
   * **Webhook URL**: This will be autogenerated. Copy the URL to configure a webhook in Azure DevOps.
3. **Save the Integration**:
   * Save the integration to establish the link between the Azure DevOps and ReleaseOwl projects.

<figure><img src="../../.gitbook/assets/image (803).png" alt=""><figcaption></figcaption></figure>

### **Integrating User Stories from Azure DevOps to ReleaseOwl**

ReleaseOwl supports **bidirectional integration**, allowing synchronization of user stories between Azure DevOps and ReleaseOwl.

1. **Go to the Azure DevOps Project**:
   * Navigate to the project in Azure DevOps.
2. **Sync User Stories**:
   * In ReleaseOwl, go to **Change Management** > **User Stories Menu**.
   * Click the **Sync User Stories** icon.
3.  **Complete the Sync**:

    * A pop-up will confirm when the sync is complete with the message:\
      &#xNAN;_"User Story Sync Completed."_
    * Click **OK** to finish.

    <figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Webhook Configuration in Azure DevOps**

To enable real-time updates for user stories between Azure DevOps and ReleaseOwl, configure a webhook in Azure DevOps:

1. **Navigate to Webhooks in Azure DevOps**:
   * Go to **Project Settings** > **Service Hooks** > **Webhooks**.
2. **Create a New Webhook**:
   * Click **+ Add** to create a webhook.
   * Enter the **Webhook URL** provided by ReleaseOwl in the integration settings.
3. **Set Trigger Criteria**:
   * Define the conditions under which the webhook will trigger, such as:
     * **Work Item Created**
     * **Work Item Updated**
4. **Save the Webhook**:
   * Save the configuration.

<figure><img src="../../.gitbook/assets/image (536).png" alt=""><figcaption></figcaption></figure>

### **Note**

* The webhook ensures that any updates or status changes to user stories in Azure DevOps are reflected in ReleaseOwl.
* Likewise, updates in ReleaseOwl are synchronized with Azure DevOps, making the integration fully **bidirectional**.

{% hint style="info" %}
For more details, refer to the official documentation: [Azure DevOps User Guide](https://docs.microsoft.com/en-us/azure/devops/organizations/?view=azure-devops).
{% endhint %}

