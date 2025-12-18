# UiPath

Efficient integration of tools like UiPath with ReleaseOwl enhances automation and testing workflows, enabling seamless operations and better management of RPA and DevOps pipelines. This guide provides a detailed step-by-step walkthrough to help you integrate UiPath with the ReleaseOwl dashboard, from setting up UiPath Orchestrator to configuring test cases and connecting UiPath Assistant to the cloud.

### **1. Setting Up UiPath Orchestrator**

#### Step 1: Sign In to UiPath Orchestrator

* Open UiPath Orchestrator in your browser.
* Sign in using your credentials.

<figure><img src="../../.gitbook/assets/image (545).png" alt=""><figcaption></figcaption></figure>

#### Step 2: Access Orchestrator

* Click on the **Orchestrator** button located in the top-left corner of the interface.

<figure><img src="../../.gitbook/assets/image (546).png" alt=""><figcaption></figcaption></figure>

#### Step 3: Create a New Folder

* Navigate to **Tenant** in the side menu.
* Create a new folder by following the on-screen instructions.

<figure><img src="../../.gitbook/assets/image (547).png" alt=""><figcaption></figcaption></figure>

#### Step 4: Set Up an Unattended Robot

* Go to **Robots** and select **Unattended Setup**.
* Click on **Self-Hosted (Unattended Robot)** and then click **Next**.

<figure><img src="../../.gitbook/assets/image (548).png" alt=""><figcaption></figcaption></figure>

* Select **Create New Machine Template** and click **Next**.

<figure><img src="../../.gitbook/assets/image (549).png" alt=""><figcaption></figcaption></figure>

* Fill in the necessary details and click the **Next** button.

<figure><img src="../../.gitbook/assets/image (550).png" alt=""><figcaption></figcaption></figure>

#### Step 5: Configure Domain/Username and Password

* Open the **Command Prompt (CMD)** on your system.
* Type `systeminfo` to retrieve your Logon Server (Domain URL).
* Find your username in the command prompt before the `>` symbol (e.g., `C:\Users\<YourUsername>`).

<figure><img src="../../.gitbook/assets/image (551).png" alt=""><figcaption></figcaption></figure>

* Enter the following:
  * **Domain\Username:** Your domain name (from the Logon Server) and your username (from the command prompt).
  * **Windows Password:** Your system's password.
* Click the **Next** button.

<figure><img src="../../.gitbook/assets/image (552).png" alt=""><figcaption></figcaption></figure>

#### Step 6: Finalize the Robot Setup

* After clicking **Next**, select the created unattended robot account.

<figure><img src="../../.gitbook/assets/image (553).png" alt=""><figcaption></figcaption></figure>

* Click **Next**.
* Copy the **Client ID** and **Client Secret** generated in this step.
* Click the **Close** button.

<figure><img src="../../.gitbook/assets/image (554).png" alt=""><figcaption></figcaption></figure>

### **2. Installing and Using UiPath Studio**

#### Step 7: Install UiPath Studio

* Open the **App Launcher** in UiPath Orchestrator.
* Click on **Studio** and install it locally on your machine.

<figure><img src="../../.gitbook/assets/image (555).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** UiPath Studio is a powerful IDE used to design, build, and develop automation workflows for RPA.
{% endhint %}

#### Step 8: Publish Test Cases to Orchestrator

* Launch the locally installed UiPath Studio.
* Create your test cases.

<figure><img src="../../.gitbook/assets/image (558).png" alt=""><figcaption></figcaption></figure>

* Click the **Publish** button to upload the test cases to your UiPath Orchestrator cloud account.

<figure><img src="../../.gitbook/assets/image (557).png" alt=""><figcaption></figcaption></figure>

#### Step 9: Manage Test Cases in Orchestrator

* In UiPath Orchestrator, navigate to the folder you created earlier.
* Click on **Testing** to view the published test cases.

<figure><img src="../../.gitbook/assets/image (559).png" alt=""><figcaption></figcaption></figure>

#### Step 10: Create a Test Set

* Click **Add Test Set** in Orchestrator.
* Fill in the necessary details for the test set.
* Save the information.

<figure><img src="../../.gitbook/assets/image (560).png" alt=""><figcaption></figcaption></figure>

### **3. Connecting UiPath Assistant to UiPath Cloud**

#### Step 1: Open UiPath Assistant

* Open **UiPath Assistant** on your machine.
* In your UiPath Assistant account, go to **Preferences** and navigate to **Orchestrator Settings**.

<figure><img src="../../.gitbook/assets/image (561).png" alt=""><figcaption></figcaption></figure>

#### Step 2: Configure Connection Details

* Select your **Connection Type**, **Machine Name**, and **Orchestrator URL**.
* To find the Orchestrator URL:
  * Go to UiPath Orchestrator in your UiPath Cloud account.
  * Copy the URL provided (e.g., `https://cloud.uipath.com/releaijylebf/DefaultTenant/orchestrator_/monitoring/overview?tid=1972132&fid=6150923`).
  *   Modify the URL by removing everything after `orchestrator_/`, so it looks like this:

      ```
      https://cloud.uipath.com/releaijylebf/DefaultTenant/orchestrator_/
      ```

#### Step 3: Obtain and Enter Machine Key

* Go to the folder where you created the machine.

<figure><img src="../../.gitbook/assets/image (562).png" alt=""><figcaption></figcaption></figure>

* Click on the machine you created and select the three dots (**...**) (also known as the "**ellipses**" or "**more options**").

<figure><img src="../../.gitbook/assets/image (563).png" alt=""><figcaption></figcaption></figure>

* Click on **Edit Machine**.

<figure><img src="../../.gitbook/assets/image (564).png" alt=""><figcaption></figcaption></figure>

* You will see the Machine Key. Copy this key.

<figure><img src="../../.gitbook/assets/image (566).png" alt=""><figcaption></figcaption></figure>

* Paste both the **Orchestrator URL** and **Machine Key** into UiPath Assistant and click **Connect**.

<figure><img src="../../.gitbook/assets/image (567).png" alt=""><figcaption></figcaption></figure>

**Note:** UiPath Assistant is a desktop application that acts as an interface between the user and the UiPath robots running on the machine. It allows users to interact with and manage their robots, monitor running processes, and trigger automation tasks.

### **4. Integrating UiPath with ReleaseOwl**

#### Step 1: Register Credential

* **Access Credential Manager:**
  * In the **Administration** section, click on **Credential Manager**.
* **Click on Register Credential:**
  * In the Credential Manager, click on **Register Credential**.
* **Fill in the Credential Details:**
  * **Credential Name:** Enter a name for your credential.
  * **Credential Type:** Select the appropriate credential type.
  * **Token URL:** [https://account.uipath.com.](https://account.uipath.com)

<figure><img src="../../.gitbook/assets/image (569).png" alt=""><figcaption></figcaption></figure>

#### Step 2: Obtain Client ID and Client Secret

* Log in to your **UiPath Orchestrator** account.
* Click on your profile icon and select **Preferences**.

<figure><img src="../../.gitbook/assets/image (570).png" alt=""><figcaption></figcaption></figure>

* In **Preferences**, go to the **Privacy & Security** section.

<figure><img src="../../.gitbook/assets/image (571).png" alt=""><figcaption></figcaption></figure>

* Click on **View API Access**.
* Here, you will find your User Key, which acts as both the Client ID and Client Secret.

<figure><img src="../../.gitbook/assets/image (572).png" alt=""><figcaption></figcaption></figure>

#### Step 3: Register the Credential in ReleaseOwl

* Copy the **Client ID** and **Client Secret** from the View API Access section in UiPath.
* Return to the **Register Credential** page in ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (574).png" alt=""><figcaption></figcaption></figure>

* Paste the **Client ID** and **Client Secret** into the appropriate fields.
* Click **Save** to register the credential.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **5. Test Configuration in ReleaseOwl**

#### Step 1: Go to Project View

* Navigate to your **Project View** in ReleaseOwl.
* Click on **Test Configurations** and create a new test configuration.

<figure><img src="../../.gitbook/assets/image (575).png" alt=""><figcaption></figcaption></figure>

#### Step 2: Fill in Necessary Details

* Enter the required details such as **Name**, **Test System**, etc.

<figure><img src="../../.gitbook/assets/image (576).png" alt=""><figcaption></figcaption></figure>

#### Step 3: Find and Modify Orchestrator URL

* Go to UiPath Orchestrator in your UiPath Cloud account.
*   Copy the provided URL and modify it to look like this:

    ```
    https://cloud.uipath.com/releaijylebf/DefaultTenant/orchestrator_/
    ```

#### Step 4: Select Folder and Test Sets

* In the test configuration, select the appropriate **Folder** and **Test Sets**.

<figure><img src="../../.gitbook/assets/image (577).png" alt=""><figcaption></figcaption></figure>

#### Step 5: Submit and Run the Test

* Click the **Submit** button to save the test configuration.
* Click the **Run** button. A message will confirm that the test execution was successful.

<figure><img src="../../.gitbook/assets/image (578).png" alt=""><figcaption></figcaption></figure>

#### Step 6: View Test Run Details and Report

* Click on **View Test Run** to see the details of the executed test cases, including the total number of test cases run and their statuses (Passed or Failed).

<figure><img src="../../.gitbook/assets/image (579).png" alt=""><figcaption></figcaption></figure>

*   To view a detailed report, click the **Report** button. The report will include:

    * **Test set details**
    * **Start time**
    * **End time**

    <figure><img src="../../.gitbook/assets/image (580).png" alt=""><figcaption></figcaption></figure>
