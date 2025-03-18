# Working with Build Pipelines

### **Build**

The Build section in ReleaseOwl enables developers to create MTAR artifacts and validate changes thoroughly for early feedback.

### **Build Pipeline (SAP BTP)**

#### **Artifact**

An artifact is a folder or a zip file containing files needed during the deployment of software to an environment.

#### **Build Pipeline**

A pipeline is the sequence of activities executed one at a time in the form of a workflow configured in your Continuous Integration and Delivery (CI/CD) platform. A Build Pipeline is used to generate artifacts from the source code. Build Pipelines can be created and run with ReleaseOwl. It fetches the source from the GIT Repository and packages the application as an MTA artifact.

**MTA (Multitarget Application)**

An MTA is logically a single application consisting of multiple related and interdependent parts, called modules. These modules are:

* Developed using different technologies.
* Designed to run on different target runtime environments.
* Managed with a single, consistent lifecycle.

{% hint style="info" %}
**Note:** For more details on SAP BTP App Development, refer to the following link:\
[**SAP BTP App Development - Multitarget Application**](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/d04fc0e2ad894545aebfd7126384307c.html?q=Multitarget%20Application)
{% endhint %}

**MTAR File Generation**

The MTA archive builder is a standalone command-line tool that builds a deployment-ready MTAR (`.mtar`) file from the artifacts of an MTA project according to the project’s MTA development descriptor (`mta.yaml` file).

**Key Points about MTAR File Generation**:

1. The build process and the resulting MTA archive depend on the target platform.
2. The supported platforms currently by ReleaseOwl are:
   * **SAP BTP**
   * **SAP HANA Extended Application Services (XSA), Advanced Model Environment**

### **Prerequisites**

1. Create new project of type SAP BTP (MTAR) or SAP HANA XSA (MTAR)
2. Register BTP Credentials and BTP Environment with ReleaseOwl before starting to work with Build Pipelines.

### **Steps to Register Credentials**

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

#### **Steps to Register an SAP Cloud Environment** <a href="#steps-to-register-an-sap-cloud-environment" id="steps-to-register-an-sap-cloud-environment"></a>

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

#### **Steps to Create a New Project** <a href="#steps-to-create-a-new-project" id="steps-to-create-a-new-project"></a>

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

#### **Configure the Environment** <a href="#configure-the-environment" id="configure-the-environment"></a>

1.  **Add Environment to the Project**

    * In **Project Settings**, go to the **Environments** section.
    * Click on the **Add** button.
    * From the drop-down menu, select the environment for the BTP project.
    * Check the **Source** option.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FVVNAawpguPw9YJjsbBRR%252Fimage.png%3Falt%3Dmedia%26token%3Dba2fcdd2-a9ea-4834-937b-c00bf5a23023&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=86b423a2&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Assign Permissions to Users** <a href="#assign-permissions-to-users" id="assign-permissions-to-users"></a>

1.  **Assign User Permissions**

    * Go to the **Users** section.
    * Click on the **Lock** button to assign permissions to users.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F2hs3hKsrDIAH4KBKdzRL%252Fimage.png%3Falt%3Dmedia%26token%3Da3e2b84b-e879-40df-9f0b-f725b45a81bf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=eb6a796e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Deployment (Optional)** <a href="#deployment-optional" id="deployment-optional"></a>

1.  **Enable Deployment**

    * If deployment is required, select the **Deploy** checkbox.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FTAhykU38PxJCiWdDBxGA%252Fimage.png%3Falt%3Dmedia%26token%3Dd6f99137-127c-4a22-a729-c3be6076ef46&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1f27534f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Change Management** <a href="#change-management" id="change-management"></a>

1.  **Add a User Story**

    * Go to the **Change Management** section.
    * Click on **User Story** and fill in the necessary details.
    * Click on the **Save** button.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FfNvmRF0ZW2KyRCreKI2S%252Fimage.png%3Falt%3Dmedia%26token%3Dd805255e-9cf5-494d-ab62-9af7eb5b18d7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=12f35731&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Build Pipelines**

1.  **Create a Build Pipeline**

    * Navigate to the **Build Pipelines** section and click on **Create Build Pipeline**.
    * Enter the **Build Pipeline Name** and assign **Labels** for filtering.

    <figure><img src="../../../.gitbook/assets/image (701).png" alt=""><figcaption></figcaption></figure>
2.  **Repository Configuration**

    * Enter the **Repository URL** (e.g., Bitbucket or other platforms).
    * Select the **SCM Credentials** from the drop-down menu.
    * Choose the branch (e.g., QA, Master, or Dev).

    <figure><img src="../../../.gitbook/assets/image (702).png" alt=""><figcaption></figcaption></figure>
3.  **Builder Section**

    * **Build Type**: Automatically populated.
    * **Build Tool Version**: Select the required version.
    * **Max # of Builds to Keep**: Set to 30 to store the latest versions and avoid storage issues in Jenkins.

    <figure><img src="../../../.gitbook/assets/image (703).png" alt=""><figcaption></figcaption></figure>
4. **Scheduler**
   * Choose from **Manual**, **Schedule**, or **Webhook** options.
5.  **Notification Emails**

    * Enter email addresses to receive notifications.

    <figure><img src="../../../.gitbook/assets/image (704).png" alt=""><figcaption></figcaption></figure>

### **Tool Integrations**

#### **Static Code Analysis**

* Enable tools like **SonarQube** for code quality checks.

#### **Malware Scanning**

The purpose of a malware scan is to scan business documents for any potential threats. To perform a malware scan, you need to register the necessary credentials and configure it in your build pipeline.

**Steps to Perform Malware Scanning**

**Step 1: Register the Necessary Credentials**

1.  **Navigate to the Administration View**

    * Open the **Administration** section of the application.
    * Click **Register Credential** to create a new credential entry.

    <figure><img src="../../../.gitbook/assets/image (711).png" alt=""><figcaption></figcaption></figure>
2.  **Enter the Required Details**

    * **Credential Name**: Provide a meaningful name, such as "**Malware Scanner.**"
    * **Credential Type**: Select **Malware** from the dropdown options.

    <figure><img src="../../../.gitbook/assets/image (712).png" alt=""><figcaption></figcaption></figure>

    *   **Obtain Credentials**:

        * Log in to your **SAP BTP Cockpit**.
        * Navigate to **Services** and open the **Service Marketplace**.
        * Search for "**Malware**" and click **Create** to create an instance.

        <figure><img src="../../../.gitbook/assets/image (713).png" alt=""><figcaption></figcaption></figure>

        * Once created, go to **Instances and Subscriptions** to view the malware scan service.
        * Click **View Credentials** to copy the URL, username, and password.

        <figure><img src="../../../.gitbook/assets/image (714).png" alt=""><figcaption></figcaption></figure>
3.  **Save the Credentials**

    * Paste the copied details into the **Credential Manager**.
    * Click **Save** to register the credentials successfully.

    <figure><img src="../../../.gitbook/assets/image (715).png" alt=""><figcaption></figcaption></figure>

**Step 2: Configure the Malware Scan in the Build Pipeline**

1.  **Check the Malware Scan Stage**

    * Ensure the **Malware Scan** option is available in the **Tool Integration** stage.
    * Check the **Malware** box to enable the scan.

    <figure><img src="../../../.gitbook/assets/image (718).png" alt=""><figcaption></figcaption></figure>

    * Select the **Registered Credential** from the dropdown menu.
    * Specify the timeout duration for the malware scan.

    <figure><img src="../../../.gitbook/assets/image (717).png" alt=""><figcaption></figcaption></figure>

* Click **Save** to finalize the configuration.

<figure><img src="../../../.gitbook/assets/image (719).png" alt=""><figcaption></figcaption></figure>

**Step 3: Execute the Malware Scan**

1.  **Run the Build Pipeline**

    * Click on the **Build Now** button in the **Build Pipeline** to start the process.

    <figure><img src="../../../.gitbook/assets/image (720).png" alt=""><figcaption></figcaption></figure>
2. **View the Malware Scan Results**
   * Once the pipeline runs, click the arrow button next to the malware scan stage to view the results.
   *   Review the malware scan results, including:

       * **Status**: Indicates if the scan was successful or failed.
       * **Timestamp**: Shows when the scan was performed.
       * **Duration**: Displays how long the scan took to complete.

       <figure><img src="../../../.gitbook/assets/image (721).png" alt=""><figcaption></figcaption></figure>
3. **Review the Malware Report**
   * Access the **Build Log** section for a detailed malware scan report.
   * If malware is detected, the log will indicate that the malware status is "**true**."

<figure><img src="../../../.gitbook/assets/image (722).png" alt=""><figcaption></figcaption></figure>

#### **CVE Scan for Vulnerabilities**

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

<figure><img src="../../../.gitbook/assets/image (710).png" alt=""><figcaption></figcaption></figure>

### **Running the Build Pipeline**

1.  **Save and Run the Build Pipeline**

    * Click on the **Save** button to create the build pipeline.
    * Click on the **Build** button to run the pipeline.

    <figure><img src="../../../.gitbook/assets/image (706).png" alt=""><figcaption></figcaption></figure>
2.  **View the Results**

    * Once the pipeline runs, click the arrow button next to it to view the results.

    <figure><img src="../../../.gitbook/assets/image (707).png" alt=""><figcaption></figcaption></figure>
3. **Pipeline Status**
   * The results display the status of various stages such as **Build** and **Prepare**.
   *   Key details include:

       * **Status**: Indicates whether the result was successful or failed.
       * **Timestamp**: Shows the date and time the stage was performed.
       * **Duration**: Displays the time taken to complete the stage.

       <figure><img src="../../../.gitbook/assets/image (708).png" alt=""><figcaption></figcaption></figure>

