# CPI Test Generator

The CPI Test Generator helps automate the process of testing SAP Cloud Platform Integration (CPI) Integration Flows (iFlows). It allows you to generate, execute, and review test results, making the integration testing process efficient and error-free. This guide will walk you through the steps for deploying, configuring, testing, and mocking your iFlows using the ReleaseOwl platform.

### **Prerequisites** <a href="#pdf-page-ahecdlthytd4fxld4qwa-prerequisites" id="pdf-page-ahecdlthytd4fxld4qwa-prerequisites"></a>

**1. SAP Process Integration Runtime Service Instance**

* Navigate to **Instances and Subscriptions** and click **Create**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FpdqZ5yymXZ0kuxN4NL07%252Fimage.png%3Falt%3Dmedia%26token%3Dfc614c7d-8e85-463b-846d-2bd00b771a05&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=875ec92a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Fill in the following details:
  * **Service:** SAP Process Integration Runtime
  * **Plan:** integration-flow
  * **Runtime Environment:** Cloud Foundry
  * **Space:** Dev
  * **Instance Name:** Choose a suitable name
* Click **Next**, then **Create** to set up the instance.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F7ANMyIj6OHaZ4gv1QTqq%252Fimage.png%3Falt%3Dmedia%26token%3D2799de19-4dfe-4800-a3bf-e0844120f715&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=86c97400&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. Create Service Key
3. Enable Custom Idp
4. Enable Test Automation in ReleaseOwl CPI Environment Configuration
5. Update the OAuth credentials and Instance URLs in the ReleaseOwl CPI Environment using the details from the Service Key in SAP BTP Cockpit.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FsPsOjdkXAlBUAut4ejYM%252Fimage.png%3Falt%3Dmedia%26token%3Df4efa99d-68f0-4d7a-a13d-bd958031c85f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=aadc6a66&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Generating Test Cases** <a href="#pdf-page-ahecdlthytd4fxld4qwa-generating-test-cases" id="pdf-page-ahecdlthytd4fxld4qwa-generating-test-cases"></a>

**Enable Trace in Artifact Runtime Log Configuration**

* In **SAP BTP Cockpit**, go to **Integration and APIs** and select the **iFlow** you want to test.
* Navigate to **Artifact Details** and change the **Log Level** to **Trace** to track detailed logs during testing.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FIGqzj18WKSM2Z0XgM176%252Fimage.png%3Falt%3Dmedia%26token%3Dcb71fc06-6dec-45c6-95ab-0d1122a2dda8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=8fbcbc53&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Trigger the iFlow with the expected input using **Postman** or another tool.

### **Generate Test Cases**

1. In **CPI Test Generator**, click **Generate Test Cases**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F8yLlkR6XHboK46DAqcA7%252Fimage.png%3Falt%3Dmedia%26token%3D61841da4-2042-4b84-89e7-3f7f35e9271f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f1098b09&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. Select the **Artifact Name** for the iFlow.
3. After the iFlow execution, go to the **ReleaseOwl Dashboard** and click **Fetch Activity Messages**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FlP5HtpGquPXfLSisaDiz%252Fimage.png%3Falt%3Dmedia%26token%3Dfb894e82-71d8-4bfa-9734-a5c361f79552&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a79faf46&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. When you click on the **Test Case** button, ensure that special characters are not used in the CPI test case names.&#x20;

<figure><img src="../../.gitbook/assets/image (1083).png" alt=""><figcaption></figcaption></figure>

5. This will retrieve messages from the latest iFlow execution. The first message will be the input message, and the remaining messages will be treated as output messages.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FBEGLA3Wc3saVvJ38slEz%252Fimage.png%3Falt%3Dmedia%26token%3D076e843a-c074-4597-9de0-143ad4b96b2b&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d9433af&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. Click the **Eye Icon** to view the messages.
6. Select the **Message Group ID** and click **Generate Test Case**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FRLVN9OhfaYHHiCUStBcK%252Fimage.png%3Falt%3Dmedia%26token%3D78762627-16cb-4031-8f4f-1714b0cee225&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=bf03462&#x26;sv=2" alt=""><figcaption></figcaption></figure>

7. Enter the **Test Case Name** and **Description**, then click **OK**.

### **Executing Test Cases** <a href="#pdf-page-ahecdlthytd4fxld4qwa-executing-test-cases" id="pdf-page-ahecdlthytd4fxld4qwa-executing-test-cases"></a>

1. Click **Run** to execute the test case.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FyzxICSw9sggrSa1HfKCM%252Fimage.png%3Falt%3Dmedia%26token%3Dc14ebc20-040a-437e-b6bb-01a0e0b55f9f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5b247dcb&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. After execution, click the **Actions button (···)** and select **Last Test Results** to view test case results.
3. You can view the executed test cases, including details such as:
   * **Run ID**
   * **Artifact Name**
   * **Environment**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F3YnUwwblSLDHdoEzgD3T%252Fimage.png%3Falt%3Dmedia%26token%3Df17c3b2d-6e8c-48c0-be26-76a7df603a77&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=adbe7135&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Run on button:** It provides an option to select a particular environment before executing the test case.

**Test Runs:** Displays all test runs with timestamps, executed artifact versions, and environments.

### **Comparing Test Run Messages**

* **Expected Output:** The message recorded during test case creation.
* **Actual Output:** The message from the current test execution.
* **Differences:** Differences between the **header** and **exchange properties** of the expected and actual messages.
* **Added Label:** Indicates unmatched paths where the **expected output** is **null**, improving message comparison visibility in the test results.

<figure><img src="../../.gitbook/assets/image (1084).png" alt=""><figcaption></figcaption></figure>

* The **Ignore List** allows you to exclude specific **paths, header properties, and exchange properties** (e.g., timestamps, generated IDs, etc.).

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FfNw593v63I03OVAAheaD%252Fimage.png%3Falt%3Dmedia%26token%3D1d0ef3fa-ae60-43cd-8fe2-7a49b1a5535e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=37535525&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Editing and Updating Test Cases** <a href="#pdf-page-ahecdlthytd4fxld4qwa-editing-and-updating-test-cases" id="pdf-page-ahecdlthytd4fxld4qwa-editing-and-updating-test-cases"></a>

* If a test case needs adjustments (e.g., missing parameters in the iFlow), click **Edit** to modify it.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FMZWOXGA8BBBzmXTfCSvk%252Fimage.png%3Falt%3Dmedia%26token%3D88237571-1fcd-48c0-bd01-6b8103675f85&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3745fecd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* If steps are added or removed in the actual iFlow, the messages in the testcase should also be updated. Click on Update Messages will execute the iFlow using the input from the testcase, which will display the latest messages from the trace.
* The user can review these messages and update the testcase with the new message steps. Click on the Save button to save the updated messages to the testcase.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F1aBYKSt1qNblAFPdK494%252Fimage.png%3Falt%3Dmedia%26token%3Dec81938d-2019-4b11-990b-3a86367c96b2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9405a629&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Active Button**

* If you need to **temporarily disable** the execution of a test case, uncheck the **Active** button.
* Once the issue is resolved, re-enable the test case by checking the **Active** button again.

#### **Mock Endpoints** <a href="#pdf-page-ahecdlthytd4fxld4qwa-mock-endpoints" id="pdf-page-ahecdlthytd4fxld4qwa-mock-endpoints"></a>

* When enabled, ReleaseOwl **mocks all receiver channels** in the iFlow with **HTTPS receivers** pointing to the **ReleaseOwl mock service**.
* ReleaseOwl creates a **new iFlow** with the name **ROMOCK** and prefixes the package name with **ROMOCK**.
* The mock service simulates responses returned by external calls using recorded messages from the test case generation.
* This allows integration flow testing **without relying on actual external APIs**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FhmtIILcpTuHXdj0hZq97%252Fimage.png%3Falt%3Dmedia%26token%3D848dd989-0b81-4706-8388-bc7918c70d95&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=47c83cdd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

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

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F8li176dfvchyOBtaGHwl%252Fimage.png%3Falt%3Dmedia%26token%3D3fb760f2-b606-4be8-9a82-f3a98bef4090&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d207e4f7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### **Mocking Test Cases** <a href="#pdf-page-ahecdlthytd4fxld4qwa-mocking-test-cases" id="pdf-page-ahecdlthytd4fxld4qwa-mocking-test-cases"></a>

ReleaseOwl mocks all the receiver channels in the iFlow with https receivers pointing to ReleaseOwl mock service.

#### **Mocking Steps:**

1. **Edit the test case** and enable **Mock Endpoints** to simulate receiver endpoints using the HTTP receiver provided by ReleaseOwl.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fi8siO0LKpLwlXlAorOq8%252Fimage.png%3Falt%3Dmedia%26token%3D6270ba56-b3a0-438b-8baa-fb0a40f79c9d&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a9734739&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. **Run the test case with mock enabled.**
3. **Mock Package and iFlow:**
   * A **Mock Package** and **Mock iFlow** will be created in the **CPI tenant** with the prefix **ROMOCK**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fjt6dpB8Ft6TrUofmpzX9%252Fimage.png%3Falt%3Dmedia%26token%3D60341cb7-5638-49e1-a7c1-ca8674b9653c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f89fa19a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Test Results after Execution:**

* **Executed on Artifact ID:** Displays the artifact name against which the test case was executed.
* **Executed Artifact Version:** Shows the version of the artifact used for the test case execution.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FzG3aFFSnhzgWQgQtWI1P%252Fimage.png%3Falt%3Dmedia%26token%3Ddf8679cd-f220-41eb-85e4-97f728bbaff8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=4da042d7&#x26;sv=2" alt=""><figcaption></figcaption></figure>
