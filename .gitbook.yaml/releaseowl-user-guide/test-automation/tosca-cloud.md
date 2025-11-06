# Tosca Cloud

### Integrating Tosca Cloud Test Automation with ReleaseOwl

This guide will help you integrate **Tosca Cloud** test automation with the **ReleaseOwl** dashboard to enhance your testing and release management workflows. With this integration, you can seamlessly monitor and manage cloud-based test automation, gain actionable insights, and automate test execution as part of your release pipeline.

### Prerequisites

Before starting, ensure the following prerequisites are met:

#### &#x20;Tosca Cloud Setup:

* A valid **Tricentis Tosca Cloud** account is available.
* You have access to the **Tricentis Cloud Platform (TCP)** to manage users and workspaces.
* Your test cases are uploaded or available in Tosca Cloud.

{% hint style="info" %}
**Note:** For more information on how to create playlists or run test cases in Tosca Cloud, please refer to the [link](https://documentation.tricentis.com/tricentis_cloud/en/content/run_tests/run_tests.htm).
{% endhint %}

### Steps for Integration

1. Go to the https://\<yourdomain>.my.tricentis.com/\_identity/apiDocs/swagger/index.html.  Here, `<yourdomain>` refers to the domain name of the account you created on **Tricentis Tosca Cloud**.
2. **Authorize and Retrieve Token URL:**
   * Click the **Authorize** button.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Copy the **token URL** displayed.

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. **Get All Applications of the Organization:**

* Scroll to the section named **Application**.
* Click on **Get all applications of the organization**.

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Click **Try it out**, then click **Execute**.
* From the response, identify and copy the **Client ID**.

<figure><img src="../../.gitbook/assets/image (8) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. **Locate the Tricentis Cloud API Application:**

* Search for the application associated with **Tricentis Cloud API**.
* Copy the **Application ID** (you’ll use this to retrieve the Client Secret).

<figure><img src="../../.gitbook/assets/image (10) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. **Retrieve the Client Secret:**

* Navigate to **List all the secrets for an application**.
* Paste the **Application ID** you copied earlier into the input field.
* Click **Try it out**, then click **Execute**.

<figure><img src="../../.gitbook/assets/image (12) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* The response will contain the **Client Secret**.

<figure><img src="../../.gitbook/assets/image (14) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. **Register Credentials in ReleaseOwl:**

* In ReleaseOwl, go to **Credential Manager**.
* Click on **Register Credential** and select the credential type as **Tosca Cloud**.

<figure><img src="../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Paste the **Client ID** and **Client Secret** into the respective fields.
* Click **Save** to complete the integration.

<figure><img src="../../.gitbook/assets/image (17) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Test Configuration

Setting up the test configuration allows the ReleaseOwl application to run **Tosca Cloud** test automation with the specified parameters from the designated playlist or execution list using cloud-based execution.

#### **Create a New Test Configuration**

1. In **Project View**, navigate to **Test Configuration**.
2. On the displayed page, click **Create Test Configuration**.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Fill in the Test Configuration Details**

* **Name:** Enter a meaningful name for the test configuration.
* **Test System:** Select **ToscaCloud** as the test system.
* **Credentials:** Select the registered Tosca Cloud credentials.
* **Tosca Cloud URL:** Enter the Tosca Cloud base URL (e.g., `https://<yourdomain>.my.tricentis.com`).
* **Workspace:** Select the appropriate workspace from the dropdown.
* **Playlists:** Choose the desired playlist(s) that contain the test cases to be executed.
* Click the **Submit** button to save the test configuration. Once submitted, a **Tosca Cloud test run** instance is created within ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* To start the execution, click the **Run** button. Upon execution, a confirmation message will appear indicating whether the test run was successfully triggered in Tosca Cloud.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Viewing Test Runs and Reports

1. To view the test runs, click **View Test Runs** against the desired Test Configuration.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. The test runs and their results, along with **Logs** and **Reports**, will be displayed.

<figure><img src="../../.gitbook/assets/image (1478).png" alt=""><figcaption></figcaption></figure>

3. **Reports**:\
   Click the **Reports** button to open the Reports section. It displays:
   * The number of playlists that contain the executed test cases.
   * The user who triggered the execution.
   * If the test cases are still in progress, they will be shown in the **Queue** stage.&#x20;

<figure><img src="../../.gitbook/assets/image (1479).png" alt=""><figcaption></figcaption></figure>

4. Once completed, the test results will appear in the **Results** section, where you can click to view details. This will redirect you to the **Tricentis Cloud Platform (TCP)** for detailed insights.

<figure><img src="../../.gitbook/assets/image (1483).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1484).png" alt=""><figcaption></figcaption></figure>

5. When you expand the side navigation bar, it shows the number of test cases.

<figure><img src="../../.gitbook/assets/image (1480).png" alt=""><figcaption></figcaption></figure>

6. Clicking on **Logs** will display the detailed logs for the selected test run.

<figure><img src="../../.gitbook/assets/image (1481).png" alt=""><figcaption></figcaption></figure>

