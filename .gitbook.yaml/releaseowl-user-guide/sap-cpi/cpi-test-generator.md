# CPI Test Generator

The CPI Test Generator helps automate the process of testing SAP Cloud Platform Integration (CPI) Integration Flows (iFlows). It allows you to generate, execute, and review test results, making the integration testing process efficient and error-free. This guide will walk you through the steps for deploying, configuring, testing, and mocking your iFlows using the ReleaseOwl platform.

### **Prerequisites** <a href="#pdf-page-ahecdlthytd4fxld4qwa-prerequisites" id="pdf-page-ahecdlthytd4fxld4qwa-prerequisites"></a>

**1. SAP Process Integration Runtime Service Instance**

* Navigate to **Instances and Subscriptions** and click **Create**.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Fill in the following details:
  * **Service:** SAP Process Integration Runtime
  * **Plan:** integration-flow
  * **Runtime Environment:** Cloud Foundry
  * **Space:** Dev
  * **Instance Name:** Choose a suitable name
* Click **Next**, then **Create** to set up the instance.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Create Service Key
3. Enable Custom Idp
4. Enable Test Automation in ReleaseOwl CPI Environment Configuration
5. Update the OAuth credentials and Instance URLs in the ReleaseOwl CPI Environment using the details from the Service Key in SAP BTP Cockpit.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Generating Test Cases** <a href="#pdf-page-ahecdlthytd4fxld4qwa-generating-test-cases" id="pdf-page-ahecdlthytd4fxld4qwa-generating-test-cases"></a>

**Enable Trace in Artifact Runtime Log Configuration**

* In **SAP BTP Cockpit**, go to **Integration and APIs** and select the **iFlow** you want to test.
* Navigate to **Artifact Details** and change the **Log Level** to **Trace** to track detailed logs during testing.
* Trigger the iFlow with the expected input using **Postman** or another tool.

<figure><img src="../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

### **Generate Test Cases**

1. In **CPI Test Generator**, click **Generate Test Cases**.
2. Select the **Artifact Name** for the iFlow.
3. After the iFlow execution, go to the **ReleaseOwl Dashboard** and click **Fetch Activity Messages**.





4. When you click on the **Test Case** button, ensure that special characters are not used in the CPI test case names.&#x20;

<figure><img src="../../.gitbook/assets/image (1083).png" alt=""><figcaption></figcaption></figure>

5. This will retrieve messages from the latest iFlow execution. The first message will be the input message, and the remaining messages will be treated as output messages.



6. Click the **Model Step Id** to view the messages.

<figure><img src="../../.gitbook/assets/image (68).png" alt=""><figcaption></figcaption></figure>

6. Select the **Message Group ID** and click **Generate Test Case**.



7. Enter the **Test Case Name** and **Description**, then click **OK**.

### **Executing Test Cases** <a href="#pdf-page-ahecdlthytd4fxld4qwa-executing-test-cases" id="pdf-page-ahecdlthytd4fxld4qwa-executing-test-cases"></a>

1. Click **Run** to execute the test case.

<figure><img src="../../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>

2. After execution, click the **Actions button (···)** and select **Last Test Results** to view test case results.
3.  You can view the executed test cases, including details such as:

    * **Run ID**
    * **Artifact Name**
    * **Environment**

    <figure><img src="../../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>

**Run on button:** It provides an option to select a particular environment before executing the test case.

**Test Runs:** Displays all test runs with timestamps, executed artifact versions, and environments.

### **Comparing Test Run Messages**

* **Expected Output:** The message recorded during test case creation.
* **Actual Output:** The message from the current test execution.
* **Differences:** Differences between the **header** and **exchange properties** of the expected and actual messages.
* **Added Label:** Indicates unmatched paths where the **expected output** is **null**, improving message comparison visibility in the test results.

<figure><img src="../../.gitbook/assets/image (1084).png" alt=""><figcaption></figcaption></figure>

* The **Ignore List** allows you to exclude specific **paths, header properties, and exchange properties** (e.g., timestamps, generated IDs, etc.).

<figure><img src="../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

#### **Editing and Updating Test Cases** <a href="#pdf-page-ahecdlthytd4fxld4qwa-editing-and-updating-test-cases" id="pdf-page-ahecdlthytd4fxld4qwa-editing-and-updating-test-cases"></a>

* If a test case needs adjustments (e.g., missing parameters in the iFlow), click **Edit** to modify it.
* If steps are added or removed in the actual iFlow, the messages in the testcase should also be updated. Click on Update Messages will execute the iFlow using the input from the testcase, which will display the latest messages from the trace.
* The user can review these messages and update the testcase with the new message steps. Click on the Save button to save the updated messages to the testcase.

<figure><img src="../../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>

**Active Button**

* If you need to **temporarily disable** the execution of a test case, uncheck the **Active** button.
* Once the issue is resolved, re-enable the test case by checking the **Active** button again.

#### **Mock Endpoints** <a href="#pdf-page-ahecdlthytd4fxld4qwa-mock-endpoints" id="pdf-page-ahecdlthytd4fxld4qwa-mock-endpoints"></a>

* When enabled, ReleaseOwl **mocks all receiver channels** in the iFlow with **HTTPS receivers** pointing to the **ReleaseOwl mock service**.
* ReleaseOwl creates a **new iFlow** with the name **ROMOCK** and prefixes the package name with **ROMOCK**.
* The mock service simulates responses returned by external calls using recorded messages from the test case generation.
* This allows integration flow testing **without relying on actual external APIs**.

<figure><img src="../../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>

#### **Supported Sender Adapters** <a href="#pdf-page-ahecdlthytd4fxld4qwa-supported-sender-adapters" id="pdf-page-ahecdlthytd4fxld4qwa-supported-sender-adapters"></a>

Test cases can be executed against iFlows using the following sender adapters:

* **HTTP Adapter**
* **SOAP Adapter**
* **IDoc Adapter**
* **Process Direct Adapter**
* **JMS Adapter**

### **Running Test Cases for Process Direct and JMS Adapters** <a href="#pdf-page-ahecdlthytd4fxld4qwa-running-test-cases-for-process-direct-and-jms-adapters" id="pdf-page-ahecdlthytd4fxld4qwa-running-test-cases-for-process-direct-and-jms-adapters"></a>

1. **Process Direct Adapter and JMS Adapter** do not have HTTP endpoints, so test cases cannot be executed directly.
2. To test them, **import the CPI Connector Package** provided by ReleaseOwl into your **CPI tenant**.

[86KBReleaseOwl Integrations.ziparchive](https://1890383800-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FDWyxe6hm5vqosFaByVgs%2Fuploads%2FSoq8ezi7D2ASogp1Jmzd%2FReleaseOwl%20Integrations.zip?alt=media\&token=ca7a467a-9cf2-4e1f-b2ba-e4e1bdbedd97)

3. After importing the package, **deploy the iFlow artifacts** so they can have endpoints.

### **Mocking Test Cases** <a href="#pdf-page-ahecdlthytd4fxld4qwa-mocking-test-cases" id="pdf-page-ahecdlthytd4fxld4qwa-mocking-test-cases"></a>

ReleaseOwl mocks all the receiver channels in the iFlow with https receivers pointing to ReleaseOwl mock service.

#### **Mocking Steps:**

1. **Edit the test case** and enable **Mock Endpoints** to simulate receiver endpoints using the HTTP receiver provided by ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

2. **Run the test case with mock enabled.**
3. **Mock Package and iFlow:**
   * A **Mock Package** and **Mock iFlow** will be created in the **CPI tenant** with the prefix **ROMOCK**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fjt6dpB8Ft6TrUofmpzX9%252Fimage.png%3Falt%3Dmedia%26token%3D60341cb7-5638-49e1-a7c1-ca8674b9653c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f89fa19a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Test Results after Execution:**

* **Executed on Artifact ID:** Displays the artifact name against which the test case was executed.
* **Executed Artifact Version:** Shows the version of the artifact used for the test case execution.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FzG3aFFSnhzgWQgQtWI1P%252Fimage.png%3Falt%3Dmedia%26token%3Ddf8679cd-f220-41eb-85e4-97f728bbaff8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4da042d7&#x26;sv=2" alt=""><figcaption></figcaption></figure>
