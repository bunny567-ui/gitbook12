# Cloud Environment Registration

To register the SAP cloud Environment, you must first register the corresponding credential. Follow the [link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-btp/administration/credential-management) and complete the credential setup.

#### **Navigate to SAP  Cloud Environment** <a href="#pdf-page-5hkyhw0dgtvjrdeu0fx7-id-1.-navigate-to-sap-cloud-environment" id="pdf-page-5hkyhw0dgtvjrdeu0fx7-id-1.-navigate-to-sap-cloud-environment"></a>

1. In the left-hand menu, under the **Environments** section, select **SAP Cloud Environment**.

<figure><img src="../../../.gitbook/assets/image (1420).png" alt=""><figcaption></figcaption></figure>

2. Click on the **Register SAP Cloud Environment** button in the top-right corner.

<figure><img src="../../../.gitbook/assets/image (1421).png" alt=""><figcaption></figcaption></figure>

#### **Fill in the Registration Form** <a href="#pdf-page-5hkyhw0dgtvjrdeu0fx7-id-2.-fill-in-the-registration-form" id="pdf-page-5hkyhw0dgtvjrdeu0fx7-id-2.-fill-in-the-registration-form"></a>

1. Provide the following details:

* **Name**: Enter a unique name for the cloud environment&#x20;
* **Region**: Select the region where the environment is hosted
* **API Endpoint**: Enter the Cloud Foundry API endpoint URL. This value can be found in the **SAP BTP Cockpit** under the corresponding **Cloud Foundry Environment**.
* **Credential Name**: Select the credential previously registered from the dropdown list.
* **Org**: Select the correct organization from the dropdown list.
* **Space**: Select the space associated with the environment.
* **Environment Type**: Specify the environment type (e.g., `DEV`, `QA`, or `PROD`).

2. After filling in all the details, click **Save** to register the environment.
3. The newly registered environment will appear in the **List of Environments** section.

<figure><img src="../../../.gitbook/assets/image (1422).png" alt=""><figcaption></figcaption></figure>

#### Edit/Delete Environments <a href="#pdf-page-5hkyhw0dgtvjrdeu0fx7-edit-or-delete-environments" id="pdf-page-5hkyhw0dgtvjrdeu0fx7-edit-or-delete-environments"></a>

**Edit Environment**

* Click the **pencil icon** next to the environment name.
* Update the necessary details and save the changes.

<figure><img src="../../../.gitbook/assets/image (1423).png" alt=""><figcaption></figcaption></figure>

**Delete Environment**

* Click the **trash icon** next to the environment name.
* Confirm the deletion to remove the environment.

<figure><img src="../../../.gitbook/assets/image (1424).png" alt=""><figcaption></figcaption></figure>

#### **Linked Projects**

The **Linked Projects** tab displays all projects associated with the selected SAP Cloud Environment.

**Key Features**

* **Environment Usage Visibility**: View all projects that are currently using the selected environment.
* **Source Environment Identification**: Identify whether the selected environment is configured as a source environment within any project, providing better visibility into deployment and transport processes.
* This information helps administrators understand environment dependencies before making configuration changes.

<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Logs**

The **Logs** tab provides a complete audit trail of activities performed on the selected SAP Cloud Environment.

Each log entry includes:

* Action performed
* User who performed the action
* Date and time of execution

The Logs section enables administrators to track environment-related activities and maintain audit and compliance records.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

