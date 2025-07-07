# Working with Build Pipelines

### **Build** <a href="#pdf-page-hbalethepy3zsklyalpx-build" id="pdf-page-hbalethepy3zsklyalpx-build"></a>

The Build section in ReleaseOwl enables developers to create MTAR artifacts and validate changes thoroughly for early feedback.

### **Build Pipeline (SAP BTP)** <a href="#pdf-page-hbalethepy3zsklyalpx-build-pipeline-sap-btp" id="pdf-page-hbalethepy3zsklyalpx-build-pipeline-sap-btp"></a>

#### **Artifact**

An artifact is a folder or a zip file containing files needed during the deployment of software to an environment.

#### **Build Pipeline**

A pipeline is the sequence of activities executed one at a time in the form of a workflow configured in your Continuous Integration and Delivery (CI/CD) platform. A Build Pipeline is used to generate artifacts from the source code. Build Pipelines can be created and run with ReleaseOwl. It fetches the source from the GIT Repository and packages the application as an MTA artifact.

#### **MTA (Multitarget Application)**

An MTA is logically a single application consisting of multiple related and interdependent parts, called modules. These modules are:

* Developed using different technologies.
* Designed to run on different target runtime environments.
* Managed with a single, consistent lifecycle.

{% hint style="info" %}
**Note:** For more details on SAP BTP App Development, refer to the following link: [**SAP BTP App Development - Multitarget Application**](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/d04fc0e2ad894545aebfd7126384307c.html?q=Multitarget%20Application)
{% endhint %}

### **MTAR File Generation**

The MTA archive builder is a standalone command-line tool that builds a deployment-ready MTAR (`.mtar`) file from the artifacts of an MTA project according to the project’s MTA development descriptor (`mta.yaml` file).

### **Key Points about MTAR File Generation**:

1. The build process and the resulting MTA archive depend on the target platform.
2. The supported platforms currently by ReleaseOwl are:
   * **SAP BTP**
   * **SAP HANA Extended Application Services (XSA), Advanced Model Environment**

### **Prerequisites** <a href="#pdf-page-hbalethepy3zsklyalpx-prerequisites" id="pdf-page-hbalethepy3zsklyalpx-prerequisites"></a>

1. Create new project of type SAP BTP (MTAR) or SAP HANA XSA (MTAR)
2. Register BTP Credentials and BTP Environment with ReleaseOwl before starting to work with Build Pipelines.

### **Steps to Register Credentials** <a href="#pdf-page-hbalethepy3zsklyalpx-steps-to-register-credentials" id="pdf-page-hbalethepy3zsklyalpx-steps-to-register-credentials"></a>

1. **Access the Credential Manager**
   * In the administration view, navigate to the **Credential Manager**.
   * Click on **Register Credential**.
2.  **Fill in the Credential Details**

    * **Credential Name**: Enter a name of your choice.
    * **Credential Type**: Choose **SAP Cloud Environment**.
    * **Authentication Type**: Select either **Basic** or **Authentication**.
    * **Username**: Enter your SAP BTP Username.
    * **Credentials**: Use your SAP BTP password.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FdoXkEEdIlP43w27qJWvB%252Fimage.png%3Falt%3Dmedia%26token%3D1c025a6a-a926-4d6c-b474-73da94212de7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=15df08a0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Steps to Register an SAP Cloud Environment**

1.  **Navigate to SAP Cloud Environment**

    * Go to **Environments** and click on **SAP Cloud Environment**.
    * Select **Register SAP Cloud Environment**.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F3smNg0ewTtULrVH2GEfQ%252Fimage.png%3Falt%3Dmedia%26token%3Ded392743-c212-498b-a059-3d575b920cdf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9526be65&#x26;sv=2" alt=""><figcaption></figcaption></figure>
2. **Fill in the Required Details**
   * **Name**: Enter a reference name of your choice.
   * **Region**: Select the appropriate region.
   * **API Endpoint**: Automatically populates based on the selected region.
   * **Credential Name**: Select the registered credential from the drop-down menu.
   * **Org**: The organization will auto-populate in the drop-down menu.
   * **Space**: The space will also auto-populate in the drop-down menu.
   * **Environment**: Choose the desired environment (e.g., dev, QA, etc.).
3. **Save the Details**
   * Once all fields are filled, click on the **Save** button.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FQa5appKMjpT4uoKOVPaG%252Fimage.png%3Falt%3Dmedia%26token%3De3d3678c-0a37-491d-8166-4ce1d89c042d&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=46dc56d6&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Steps to Create a New Project**

1.  **Create a New Project**

    * Go to **Projects** and click on **Create New Project**.
    * Fill in the required details:
      * **Name**: Enter a project name of your choice.
      * **Prefix Type**: Auto-populates from the project prefix.
      * **Project Type**: Select **SAP BTP Project**.
    * Click on the **Save** button.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F4sm7Z1YpjiHJt7WnRKsN%252Fimage.png%3Falt%3Dmedia%26token%3Db97a271f-1e4d-4470-be0c-6c137445af73&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ac087060&#x26;sv=2" alt=""><figcaption></figcaption></figure>
2.  **Access Project Settings**

    * Locate the newly created project.
    * Click on the three-dot menu (•••) and select **Project Settings**.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FIIpLT8iJxXkHC5HB34M6%252Fimage.png%3Falt%3Dmedia%26token%3Dfafe2a50-4d70-4cda-8b35-f49ada8259bf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=52347d7c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Configure the Environment**

1.  **Add Environment to the Project**

    * In **Project Settings**, go to the **Environments** section.
    * Click on the **Add** button.
    * From the drop-down menu, select the environment for the BTP project.
    * Check the **Source** option.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FVVNAawpguPw9YJjsbBRR%252Fimage.png%3Falt%3Dmedia%26token%3Dba2fcdd2-a9ea-4834-937b-c00bf5a23023&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=86b423a2&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Assign Permissions to Users**

1.  **Assign User Permissions**

    * Go to the **Users** section.
    * Click on the **Lock** button to assign permissions to users.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F2hs3hKsrDIAH4KBKdzRL%252Fimage.png%3Falt%3Dmedia%26token%3Da3e2b84b-e879-40df-9f0b-f725b45a81bf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=eb6a796e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Deployment (Optional)**

1.  **Enable Deployment**

    * If deployment is required, select the **Deploy** checkbox.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FTAhykU38PxJCiWdDBxGA%252Fimage.png%3Falt%3Dmedia%26token%3Dd6f99137-127c-4a22-a729-c3be6076ef46&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1f27534f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Change Management**

1.  **Add a User Story**

    * Go to the **Change Management** section.
    * Click on **User Story** and fill in the necessary details.
    * Click on the **Save** button.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FfNvmRF0ZW2KyRCreKI2S%252Fimage.png%3Falt%3Dmedia%26token%3Dd805255e-9cf5-494d-ab62-9af7eb5b18d7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=12f35731&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Build Pipelines** <a href="#pdf-page-hbalethepy3zsklyalpx-build-pipelines" id="pdf-page-hbalethepy3zsklyalpx-build-pipelines"></a>

1.  **Create a Build Pipeline**

    * Navigate to the **Build Pipelines** section and click on **Create Build Pipeline**.
    * Enter the **Build Pipeline Name** and assign **Labels** for filtering.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FF5v1mEe1No66rVLiPMOf%252Fimage.png%3Falt%3Dmedia%26token%3De97ad56e-ae3b-48e1-abfc-927225de2a2f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4cef185e&#x26;sv=2" alt=""><figcaption></figcaption></figure>
2.  **Repository Configuration**

    * Enter the **Repository URL** (e.g., Bitbucket or other platforms).
    * Select the **SCM Credentials** from the drop-down menu.
    * Choose the branch (e.g., QA, Master, or Dev).



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FzEKr9QfbG5WHz4zvZSMR%252Fimage.png%3Falt%3Dmedia%26token%3D678ea5b8-a0d6-43b8-b5fa-d3f9c04fc45e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=8cbde49d&#x26;sv=2" alt=""><figcaption></figcaption></figure>
3.  **Builder Section**

    * **Build Type**: Automatically populated.
    * **Build Tool Version**: Select the required version.
    * **Max # of Builds to Keep**: Set to 30 to store the latest versions and avoid storage issues in Jenkins.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FiS5tNKbj5qCUXoQ3t5zQ%252Fimage.png%3Falt%3Dmedia%26token%3D7df782b3-554f-4f92-9da8-ae6a316ba235&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5f920f5b&#x26;sv=2" alt=""><figcaption></figcaption></figure>
4. **Scheduler**
   * Choose from **Manual**, **Schedule**, or **Webhook** options.
5.  **Notification Emails**

    * Enter email addresses to receive notifications.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fzwu6OAkLwVmvX3StsVMt%252Fimage.png%3Falt%3Dmedia%26token%3D9c498313-0708-4e03-af11-5d5e950e24ce&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2a52ac5b&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Tool Integrations** <a href="#pdf-page-hbalethepy3zsklyalpx-tool-integrations" id="pdf-page-hbalethepy3zsklyalpx-tool-integrations"></a>

**Static Code Analysis**

* Enable tools like **SonarQube** for code quality checks.

**Malware Scanning**

The purpose of a malware scan is to scan business documents for any potential threats. To perform a malware scan, you need to register the necessary credentials and configure it in your build pipeline.

### **Steps to Perform Malware Scanning**

**Step 1: Register the Necessary Credentials**

1.  **Navigate to the Administration View**

    * Open the **Administration** section of the application.
    * Click **Register Credential** to create a new credential entry.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FYcvgrCOeUJS9h0KRBIe7%252Fimage.png%3Falt%3Dmedia%26token%3Db89a4213-be0d-4674-afcc-72a58bfcdeea&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=469bdfe7&#x26;sv=2" alt=""><figcaption></figcaption></figure>
2.  **Enter the Required Details**

    * **Credential Name**: Provide a meaningful name, such as "**Malware Scanner.**"
    * **Credential Type**: Select **Malware** from the dropdown options.



    <figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

    *   **Obtain Credentials**:

        * Log in to your **SAP BTP Cockpit**.
        * Navigate to **Services** and open the **Service Marketplace**.
        * Search for "**Malware**" and click **Create** to create an instance.

        <figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



        * Once created, go to **Instances and Subscriptions** to view the malware scan service.
        * Click **View Credentials** to copy the URL, username, and password.



        <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FR9XmVCIu5Kx9lcATvlAs%252Fimage.png%3Falt%3Dmedia%26token%3Dcd1f7f9e-bbcd-4cf3-ae37-bb05338f8b0a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=7198401a&#x26;sv=2" alt=""><figcaption></figcaption></figure>
3.  **Save the Credentials**

    * Paste the copied details into the **Credential Manager**.
    * Click **Save** to register the credentials successfully.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FTt9xRZre9iGTFfGKFjXD%252Fimage.png%3Falt%3Dmedia%26token%3D68d6b932-2a4d-4fc6-b9e7-9aabf7be17ca&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3f40916f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Step 2: Configure the Malware Scan in the Build Pipeline**

1.  **Check the Malware Scan Stage**

    * Ensure the **Malware Scan** option is available in the **Tool Integration** stage.
    * Check the **Malware** box to enable the scan.

    <figure><img src="../../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



    * Select the **Registered Credential** from the dropdown menu.
    * Specify the timeout duration for the malware scan.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fn9O2gzbqzigxuMOASY49%252Fimage.png%3Falt%3Dmedia%26token%3Da0dbe109-3b25-4831-8f6e-29fc0d4e1eab&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4323e4ac&#x26;sv=2" alt=""><figcaption></figcaption></figure>



* Click **Save** to finalize the configuration.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FkSSgCnlu2JjS4UhgLp1E%252Fimage.png%3Falt%3Dmedia%26token%3Dde4a35ce-9fd7-4d9f-8b8f-d079012a9ed0&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=296ecb0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Step 3: Execute the Malware Scan**

1.  **Run the Build Pipeline**

    * Click on the **Build Now** button in the **Build Pipeline** to start the process.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FQHV8nViH4JYsx5wqoUI8%252Fimage.png%3Falt%3Dmedia%26token%3Dbdedafd6-6f20-4d67-9c22-6935584548fa&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1a6dd8c1&#x26;sv=2" alt=""><figcaption></figcaption></figure>
2. **View the Malware Scan Results**
   * Once the pipeline runs, click the arrow button next to the malware scan stage to view the results.
   *   Review the malware scan results, including:

       * **Status**: Indicates if the scan was successful or failed.
       * **Timestamp**: Shows when the scan was performed.
       * **Duration**: Displays how long the scan took to complete.



       <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FfwVz4AK7UOLRK5HuOues%252Fimage.png%3Falt%3Dmedia%26token%3D6a05f223-fe6d-44d8-b59a-6c4cd4e8e388&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c4bfda5&#x26;sv=2" alt=""><figcaption></figcaption></figure>
3. **Review the Malware Report**
   * Access the **Build Log** section for a detailed malware scan report.
   * If malware is detected, the log will indicate that the malware status is "**true**."

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FkQlvXj5UKRor9ljZqQK7%252Fimage.png%3Falt%3Dmedia%26token%3Dabb6da3a-9056-4502-977d-d786c73b6591&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a8fa2306&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**CVE Scan for Vulnerabilities**

**Overview**

CVE scans identify any vulnerable versions of libraries used in your **CAP application** by checking known vulnerabilities.

**Steps to Enable CVE Scan**

1. **Enable the SAP CVE Scan Option**
   * Go to the **Tool Integration** section.
   * Enable the option for **SAP CVE Scan**.
   * Click **Save** to apply the changes.
2. **Configure CVE Settings**
   * In the **Project Settings**, go to the **CVE** section.
   * Enter the necessary details:
     * **CVE ID**: Enter the CVE ID (e.g., CVE-2023-50422) associated with the vulnerability.
     * **Library Name**: Specify the name of the affected library.
     * **Versions**: Provide the version(s) of the library that are vulnerable.
   * Click **Save** to ensure the scan is correctly set up.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FMKDZDVDWK1P4sIBIPyEN%252Fimage.png%3Falt%3Dmedia%26token%3Da20f7990-659c-4278-a048-aa5f991e7ee5&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1a0ee7bc&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Running the Build Pipeline** <a href="#pdf-page-hbalethepy3zsklyalpx-running-the-build-pipeline" id="pdf-page-hbalethepy3zsklyalpx-running-the-build-pipeline"></a>

1.  **Save and Run the Build Pipeline**

    * Click on the **Save** button to create the build pipeline.
    * Click on the **Build** button to run the pipeline.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FKre6hfASy7oJXwu3joNV%252Fimage.png%3Falt%3Dmedia%26token%3D765a774a-849d-4995-89e9-b61fcf8ff1e0&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9808fa2c&#x26;sv=2" alt=""><figcaption></figcaption></figure>
2.  **View the Results**

    * Once the pipeline runs, click the arrow button next to it to view the results.



    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FGJ5q5ECNSVpNq6H3zsSb%252Fimage.png%3Falt%3Dmedia%26token%3D716e6bf8-dd78-4aa0-9a52-d3daed52b69a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=bcfdbd6&#x26;sv=2" alt=""><figcaption></figcaption></figure>
3. **Pipeline Status**
   * The results display the status of various stages such as **Build** and **Prepare**.
   *   Key details include:

       * **Status**: Indicates whether the result was successful or failed.
       * **Timestamp**: Shows the date and time the stage was performed.
       * **Duration**: Displays the time taken to complete the stage.



       <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FzBTW8fvUlVpabc9lKF48%252Fimage.png%3Falt%3Dmedia%26token%3Db61b890a-02b4-421b-9eff-71ed133ccdbe&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c7bf78ff&#x26;sv=2" alt=""><figcaption></figcaption></figure>
