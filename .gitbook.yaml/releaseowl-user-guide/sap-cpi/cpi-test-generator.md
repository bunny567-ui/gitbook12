# CPI Test Generator

The CPI Test Generator helps automate the process of testing SAP Cloud Platform Integration (CPI) Integration Flows (iFlows). It allows you to generate, execute, and review test results, making the integration testing process efficient and error-free. This guide will walk you through the steps for deploying, configuring, testing, and mocking your iFlows using the ReleaseOwl platform.

### **Prerequisites**

#### **1. SAP Process Integration Runtime Service Instance**

* Navigate to **Instances and Subscriptions** and click **Create**.

<figure><img src="../../.gitbook/assets/image (889).png" alt=""><figcaption></figcaption></figure>

* Fill in the following details:
  * **Service:** SAP Process Integration Runtime
  * **Plan:** integration-flow
  * **Runtime Environment:** Cloud Foundry
  * **Space:** Dev
  * **Instance Name:** Choose a suitable name
* Click **Next**, then **Create** to set up the instance.

<figure><img src="../../.gitbook/assets/image (890).png" alt=""><figcaption></figcaption></figure>

2. Create Service Key
3. Enable Custom Idp
4. Enable Test Automation in ReleaseOwl CPI Environment Configuration
5. Update the OAuth credentials and Instance URLs in the ReleaseOwl CPI Environment using the details from the Service Key in SAP BTP Cockpit.

<figure><img src="../../.gitbook/assets/image (891).png" alt=""><figcaption></figcaption></figure>

### **Generating Test Cases**

#### **Enable Trace in Artifact Runtime Log Configuration**

* In **SAP BTP Cockpit**, go to **Integration and APIs** and select the **iFlow** you want to test.
* Navigate to **Artifact Details** and change the **Log Level** to **Trace** to track detailed logs during testing.

<figure><img src="../../.gitbook/assets/image (892).png" alt=""><figcaption></figcaption></figure>

* Trigger the iFlow with the expected input using **Postman** or another tool.

#### **Generate Test Cases**

1. In **CPI Test Generator**, click **Generate Test Cases**.

<figure><img src="../../.gitbook/assets/image (893).png" alt=""><figcaption></figcaption></figure>

2. Select the **Artifact Name** for the iFlow.
3. After the iFlow execution, go to the **ReleaseOwl Dashboard** and click **Fetch Activity Messages**.

<figure><img src="../../.gitbook/assets/image (894).png" alt=""><figcaption></figcaption></figure>

4. This will retrieve messages from the latest iFlow execution. The first message will be the input message, and the remaining messages will be treated as output messages.

<figure><img src="../../.gitbook/assets/image (895).png" alt=""><figcaption></figcaption></figure>

4. Click the **Eye Icon** to view the messages.
5. Select the **Message Group ID** and click **Generate Test Case**.

<figure><img src="../../.gitbook/assets/image (896).png" alt=""><figcaption></figcaption></figure>

6. Enter the **Test Case Name** and **Description**, then click **OK**.

### **Executing Test Cases**

1. Click **Run** to execute the test case.

<figure><img src="../../.gitbook/assets/image (897).png" alt=""><figcaption></figcaption></figure>

2. After execution, click the **Actions button (···)** and select **Last Test Results** to view test case results.
3. You can view the executed test cases, including details such as:
   * **Run ID**
   * **Artifact Name**
   * **Environment**

<figure><img src="../../.gitbook/assets/image (898).png" alt=""><figcaption></figcaption></figure>

**Run on button:** It provides an option to select a particular environment before executing the test case.

**Test Runs:** Displays all test runs with timestamps, executed artifact versions, and environments.

**Comparing Test Run Messages**

* **Expected Output:** The message recorded during test case creation.
* **Actual Output:** The message from the current test execution.
* **Differences:** Differences between the **header** and **exchange properties** of the expected and actual messages.

<figure><img src="../../.gitbook/assets/image (899).png" alt=""><figcaption></figcaption></figure>

* The **Ignore List** allows you to exclude specific **paths, header properties, and exchange properties** (e.g., timestamps, generated IDs, etc.).

<figure><img src="../../.gitbook/assets/image (900).png" alt=""><figcaption></figcaption></figure>

### **Editing and Updating Test Cases**

* If a test case needs adjustments (e.g., missing parameters in the iFlow), click **Edit** to modify it.

<figure><img src="../../.gitbook/assets/image (901).png" alt=""><figcaption></figcaption></figure>

* If steps are added or removed in the actual iFlow, the messages in the testcase should also be updated. Click on Update Messages will execute the iFlow using the input from the testcase, which will display the latest messages from the trace.
*   The user can review these messages and update the testcase with the new message steps. Click on the Save button to save the updated messages to the testcase.



<figure><img src="../../.gitbook/assets/image (902).png" alt=""><figcaption></figcaption></figure>

#### **Active Button**

* If you need to **temporarily disable** the execution of a test case, uncheck the **Active** button.
* Once the issue is resolved, re-enable the test case by checking the **Active** button again.

### **Mock Endpoints**

* When enabled, ReleaseOwl **mocks all receiver channels** in the iFlow with **HTTPS receivers** pointing to the **ReleaseOwl mock service**.
* ReleaseOwl creates a **new iFlow** with the name **ROMOCK** and prefixes the package name with **ROMOCK**.
* The mock service simulates responses returned by external calls using recorded messages from the test case generation.
* This allows integration flow testing **without relying on actual external APIs**.

<figure><img src="../../.gitbook/assets/image (903).png" alt=""><figcaption></figcaption></figure>

### **Supported Sender Adapters**

Test cases can be executed against iFlows using the following sender adapters:

* **HTTP Adapter**
* **SOAP Adapter**
* **IDoc Adapter**
* **Process Direct Adapter**
* **JMS Adapter**

### **Running Test Cases for Process Direct and JMS Adapters**

1. **Process Direct Adapter and JMS Adapter** do not have HTTP endpoints, so test cases cannot be executed directly.
2. To test them, **import the CPI Connector Package** provided by ReleaseOwl into your **CPI tenant**.

{% file src="../../.gitbook/assets/ReleaseOwl Integrations (1).zip" %}

3. After importing the package, **deploy the iFlow artifacts** so they can have endpoints.

<figure><img src="../../.gitbook/assets/image (904).png" alt=""><figcaption></figcaption></figure>

### **Mocking Test Cases**

ReleaseOwl mocks all the receiver channels in the iFlow with https receivers pointing to ReleaseOwl mock service.

#### **Mocking Steps:**

1. **Edit the test case** and enable **Mock Endpoints** to simulate receiver endpoints using the HTTP receiver provided by ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (905).png" alt=""><figcaption></figcaption></figure>

1. **Run the test case with mock enabled.**
2. **Mock Package and iFlow:**
   * A **Mock Package** and **Mock iFlow** will be created in the **CPI tenant** with the prefix **ROMOCK**.

<figure><img src="../../.gitbook/assets/image (906).png" alt=""><figcaption></figcaption></figure>

#### **Test Results after Execution:**

* **Executed on Artifact ID:** Displays the artifact name against which the test case was executed.
* **Executed Artifact Version:** Shows the version of the artifact used for the test case execution.

<figure><img src="../../.gitbook/assets/image (907).png" alt=""><figcaption></figcaption></figure>

