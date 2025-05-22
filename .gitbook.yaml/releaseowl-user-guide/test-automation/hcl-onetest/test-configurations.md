# Test Configurations

## **HCL OneTest UI - Test Configurations with ReleaseOwl**

### **RO Agent**

**RO Agent** is a standalone application that executes jobs on behalf of ReleaseOwl. It currently supports the execution of **HCL OneTest UI** test cases.

The RO Agent is distributed as a ZIP file. After extraction, it can be launched using the appropriate script:

* `start.bat` (for Windows)
* `start.sh` (for Linux/macOS)

### **RO Agent Configuration**

To configure and register a new RO Agent:

1. In Administration, go to RO Agents.
2. In the page displayed, click Register RO Agent.
3. Fill in the required details.

| **Name**         | Enter the name of your choice for the RO Agent Configuration that is being created. |
| ---------------- | ----------------------------------------------------------------------------------- |
| **Host URL**     | The Host URL is the RO Agent URL that begins with http or https.                    |
| **Security Key** | Security Key value can be found in the agent.properties file.                       |

<figure><img src="../../../.gitbook/assets/image (1277).png" alt=""><figcaption></figcaption></figure>

### **Pre-requisites**

RO Agent and HCL OneTest UI should be installed on the same machine.

### **Test Configuration**

Setting up a **Test Configuration** allows the ReleaseOwl application to execute **HCL OneTest UI** scripts with specific parameters from a designated path via the **RO Agent**.

**Steps to Create a New Test Configuration**

1. **Navigate to the Project View** in ReleaseOwl.
2. Go to **Test Configuration**.
3. On the page displayed, click **Create Test Configuration**.

{% hint style="info" %}
**Note:** Test Configuration for Web UI and Functional Tests are to be created separately.
{% endhint %}

### **Test Configuration for Web UI Test**  

<figure><img src="../../../.gitbook/assets/image (1276).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**               | Enter the name of your choice for the test configuration that is being created.                                                                           |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test System**        | The Test System here is HCL OneTest UI                                                                                                                    |
| **Git Enabled**        | If Git enabled, you could access and use Git from HCL OneTest API, and the testing environment is integrated with both local and remote Git repositories. |
| **Test Type**          | Type of the test to execute. In this case, Web UI                                                                                                         |
| **Project Directory**  | The fully qualified path to HCL OneTest UI project directory. Use '\\' or '/' as the file separator. This path must exist on the agent.                   |
| **Test Suite Name**    | Name of the script to be executed without the extension.                                                                                                  |
| **VM Arguments**       | Specify Virtual Machine arguments separated by comma (,)                                                                                                  |
| **Var File**           | The complete path to the XML file that contains the variable name and value pairs.                                                                        |
| **Configuration File** | Use this option to specify the complete path to a file that contains the parameters for a test run                                                        |
| **RO Agent**           | Select the RO Agent where the current test should be executed.                                                                                            |

**Test Configuration for Functional Test**\


<figure><img src="../../../.gitbook/assets/image (1278).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**              | Enter the name of your choice for the test configuration that is being created.                                                                           |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Test System**       | The Test System here is HCL OneTest UI                                                                                                                    |
| **Git Enabled**       | If Git enabled, you could access and use Git from HCL OneTest API, and the testing environment is integrated with both local and remote Git repositories. |
| **Test Type**         | Type of the test to execute. In this case, Functional                                                                                                     |
| **Project Directory** | The fully qualified path to HCL OneTest UI project directory. Use '\\' or '/' as the file separator. This path must exist on the agent.                   |
| **Test Suite Name**   | Name of the script to be executed without the extension.                                                                                                  |
| **Iteration Count**   | The number of Dataset iterations to be run.                                                                                                               |
| **User Arguments**    | Specify additional playback arguments, if any.                                                                                                            |
| **RO Agent**          | Select the RO Agent where the current test should be executed.                                                                                            |
