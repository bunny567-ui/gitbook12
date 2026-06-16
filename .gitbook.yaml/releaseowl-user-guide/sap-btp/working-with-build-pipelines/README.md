# Working with Build Pipelines

**Build**

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

#### **Build Pipelines** <a href="#pdf-page-hbalethepy3zsklyalpx-build-pipelines" id="pdf-page-hbalethepy3zsklyalpx-build-pipelines"></a>

1. Navigate to the **Build Pipelines** section and click on **New** **Build Pipeline**.

<figure><img src="../../../.gitbook/assets/image (1959).png" alt=""><figcaption></figcaption></figure>

2. The **New Build Pipeline** window is displayed, providing the following options:

* **Create New Build Pipeline** – Create a new pipeline from scratch.
* **Import Build Pipeline** – Import an existing pipeline configuration.

3. Select the desired option.
4. Click **Create** to proceed with the selected action.

<figure><img src="../../../.gitbook/assets/image (1961).png" alt=""><figcaption></figcaption></figure>

5. Enter a unique and meaningful name for the Build Pipeline in the **Build Pipeline Name** field.
6. Click **Step 2** to proceed to the next stage of the pipeline configuration.

<figure><img src="../../../.gitbook/assets/image (1962).png" alt=""><figcaption></figcaption></figure>

**Repository Configuration**

1. **Repository URL**: Enter the repository URL (for example, GitHub, GitLab, or Bitbucket).
2. **SCM Credentials**: Select the required source control credentials from the drop-down list.
3. **Branch**: Select the branch to be used for the build process (for example, **QA**, **Master**, or **Dev**).
4. **Version Control System**: Select the repository type (for example, **GitHub**, **GitLab**, or **Bitbucket**).
5. After entering the required details, click **Step 3** to continue.

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

**Builder Section**

1. **Build Type**: Automatically populated based on the selected project configuration.
2. **Build Tool Version**: Select the required build tool version.
3. **Max # of Builds to Keep**: Specify the maximum number of build records to retain. It is recommended to set this value to **30** to preserve recent build history and prevent excessive storage consumption in Jenkins.
4. After completing the configuration, click **Step 4** to proceed.

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

**Scheduler Section**&#x20;

Configure the pipeline execution and notification settings:

1. **Scheduler**: Select how the Build Pipeline should be triggered:

* **Manual** – The pipeline is executed manually by a user.
* **Schedule** – The pipeline is executed automatically based on a predefined schedule.
* **Webhook** – The pipeline is triggered automatically when events occur in the source code repository, such as code commits or pull requests.

2. After selecting the required scheduler option, click **Step 5** to continue.

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

**Environment**

Configure the deployment environment for the Build Pipeline:

1. **Development Environment** – Select the required SAP BTP environment from the drop-down list. The available environments are those that have been previously registered in ReleaseOwl through the SAP BTP Environment registration process
2. After selecting the required development environment, click **Step 6** to continue.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

**Notification**

1. **Notification Emails**: Enter one or more email addresses to receive build status notifications, including build success, failure, and other pipeline-related updates.
2. After entering the required notification email addresses, click step 7 to continue

<figure><img src="../../../.gitbook/assets/image (15) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Tool Integrations**

1. **Static Code Analysis**

Use Static Code Analysis tools, such as **SonarQube**, to perform code quality checks during the build process.

* **Enable Static Code Analysis**.
* **Credentials**: Select the appropriate credential from the drop-down list. The available credentials are those that have been previously registered in the **ReleaseOwl Credentials** section.
* **ESL Lint**: Enable ESLint to analyze code for coding standard violations, syntax issues, and potential errors. Any ESLint validation failures detected during the build process are displayed in the **Static Code Analysis** results.&#x20;

2. **Malware Scan**

Configure malware scanning to detect potential security threats in the application artifacts.

* Ensure that the **Malware Scan** option is available in the **Tool Integrations** stage.
* Select the **Malware Scan** checkbox to enable malware scanning.
* **Credentials**: Select the registered credential from the drop-down list.
* **Timeout**: Specify the timeout duration for the malware scan process.

3. **SAP CVE Scan**

CVE scans identify any vulnerable versions of libraries used in your **CAP application** by checking known vulnerabilities.

* Enable the option for **SAP CVE Scan**.

<figure><img src="../../../.gitbook/assets/image (1964).png" alt=""><figcaption></figcaption></figure>

**Configure CVE Settings**

1. In the **Project Settings**, go to the **CVE** section.
2. Enter the necessary details:

* **CVE ID**: Enter the CVE ID (e.g., CVE-2023-50422) associated with the vulnerability.
* **Library Name**: Specify the name of the affected library.
* **Versions**: Provide the version(s) of the library that are vulnerable.

3. Click **Save** to ensure the scan is correctly set up.

<figure><img src="../../../.gitbook/assets/image (1969).png" alt=""><figcaption></figcaption></figure>

4. After configuring the required tool integrations, click **Save** to finalize the Build Pipeline configuration

<figure><img src="../../../.gitbook/assets/image (1970).png" alt=""><figcaption></figcaption></figure>

**Actions Button**

After clicking **Save**, the new Build Pipeline is created and appears in the Build Pipelines list.

The **Actions** menu provides the following options:

**Edit :**  Use **Edit** to modify the existing build pipeline configuration. This option allows you to update details such as the repository, branch, build type, schedules, or any pipeline-related settings. Any changes made are applied to the existing Build Pipeline.

**Commits :** Use **Commits** to view the list of source code commits associated with the Build Pipeline. This helps track the changes included in each build execution.

**Save as:**  Use **Save As** to create a copy of an existing Build Pipeline. The copied pipeline can then be modified independently without affecting the original pipeline.

**Archive :** Use **Archive** to deactivate a Build Pipeline. Archived pipelines are retained in the system for reference purposes but are removed from active use and cannot be executed until restored.

**Export Build Pipeline :** Use **Export Build Pipeline** to export the Build Pipeline configuration. The exported file can later be imported using the **Import Build Pipeline** option available when creating a new Build Pipeline, allowing the same configuration to be reused across projects or environments.

<figure><img src="../../../.gitbook/assets/image (1971).png" alt=""><figcaption></figcaption></figure>

**Run the Build Pipeline**

1. Click on the **Build Now** button to run the pipeline.

<figure><img src="../../../.gitbook/assets/image (1965).png" alt=""><figcaption></figcaption></figure>

2. Once the pipeline runs, click the arrow button next to it to view the results.

<figure><img src="../../../.gitbook/assets/image (1966).png" alt=""><figcaption></figcaption></figure>

3. The results display the status of various stages such as **Build** and **Prepare**.
4. Key details include:
   * **Status**: Indicates whether the result was successful or failed.
   * **Timestamp**: Shows the date and time the stage was performed.
   * **Duration**: Displays the time taken to complete the stage.

<figure><img src="../../../.gitbook/assets/image (1967).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:**  You can now access build log information even after the logs have expired. This allows you to review past build activities for better tracking and understanding of your deployment history.
{% endhint %}

