# Tosca Integration

This guide will help you integrate Tosca test automation with the ReleaseOwl dashboard to enhance your testing and release management workflows. With this integration, you can seamlessly monitor and manage test automation processes, gain better insights, and automate key tasks in your release pipeline.

### Prerequisites

Before starting, ensure the following prerequisites are met:

1. **Tosca Setup**: Tosca is installed and operational in your testing environment.
2. **ReleaseOwl Configuration**: ReleaseOwl is installed and configured for your project.
3. **Shared Environment**: RO Agent and Tosca are installed on the same machine.

## Steps for Integration

### 1. RO Agent Setup

The RO Agent is a standalone application that facilitates communication between Tosca and ReleaseOwl. It executes jobs on behalf of ReleaseOwl, including Tosca test case executions.

1. Obtain the RO Agent as a zip file from the ReleaseOwl package.
2. Extract the zip file to a directory of your choice.
3. Run the appropriate script to launch the RO Agent:
   * **For Windows**: Execute the `.bat` file.
   * **For Linux/Mac**: Execute the `.sh` file.

### 2. Configuring the RO Agent

#### **2.1. Create a New RO Agent Configuration**

1. Navigate to the **Administration** section in ReleaseOwl.
2. Go to the **RO Agents** page.
3. Click **Register RO Agent**.

<figure><img src="../../../.gitbook/assets/image (544).png" alt=""><figcaption></figcaption></figure>

**2.2. Fill in the Required Details**

Provide the following information to complete the configuration:

* **Name**: Enter a meaningful name for your RO Agent Configuration.
* **Host URL**: Provide the URL of the RO Agent, which begins with `http` or `https`.
* **Security Key**: Locate the `agent.properties` file in the RO Agent directory and copy the Security Key value from there.

<figure><img src="../../../.gitbook/assets/image (543).png" alt=""><figcaption></figcaption></figure>

### 3. Test Configuration

Setting up the test configuration allows the ReleaseOwl application to run Tosca test automation with the specified parameters from the specified path through the RO Agent.

#### **3.1. Create a New Test Configuration**

1. In **Project View**, navigate to **Test Configuration**.
2. On the displayed page, click **Create Test Configuration**.

<figure><img src="../../../.gitbook/assets/image (542).png" alt=""><figcaption></figcaption></figure>

#### **3.2. Fill in the Test Configuration Details**

* **Name**: Enter a meaningful name for the test configuration.
* **Test System**: Select **Tosca** as the Test System.
* **Test Type**:
  * **Local**: Standalone setup.
  * **Distributed**: Clustered setup.
* **Tosca Client Path**: Provide the fully qualified path to the Tricentis Tosca CI Client directory. This path must exist on the agent.
* **Test Events**: Specify the TestEvents you want to execute, separated by semicolons. Use the name or system ID to identify them.
* **Configuration File**: Specify the complete path to a file that contains the parameters for the test run.
* **RO Agent**: Select the RO Agent where the current test should be executed.

<figure><img src="../../../.gitbook/assets/image (541).png" alt=""><figcaption></figcaption></figure>

3. Click the **Submit** button. After submission, a Tosca configuration path is created.
4. Click the **Run** button to initiate the test execution. A confirmation message will indicate whether the test execution was successful.

<figure><img src="../../../.gitbook/assets/image (540).png" alt=""><figcaption></figcaption></figure>

### 4. Viewing Test Runs and Reports

1. To view the test runs, navigate to the **Test Configuration** screen and click **View Test Runs** against the desired Test Configuration.
2. The test runs and their results, along with **Logs** and **Reports**, will be displayed.

<figure><img src="../../../.gitbook/assets/image (539).png" alt=""><figcaption></figcaption></figure>

3. Click on **Logs** to view the logs.

<figure><img src="../../../.gitbook/assets/image (538).png" alt=""><figcaption></figcaption></figure>

4. Click on **Reports** to view detailed insights, including:

* Total number of tests executed.
* Success rate.
* Failure count.
* Time taken for test case execution.

<figure><img src="../../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
