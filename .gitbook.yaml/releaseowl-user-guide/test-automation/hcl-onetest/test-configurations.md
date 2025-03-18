# Test Configurations

## **HCL OneTest UI - Test Configurations with ReleaseOwl**

### **RO Agent**

RO Agent is a standalone application which executes jobs on behalf of ReleaseOwl. Currently it supports execution of HCL OneTest UI test cases. RO Agent will be given as a zip file, which can be extracted and then the .bat or .sh file can be executed.

### **RO Agent Configuration**

Create a new RO Agent.

1. In Administration, go to RO Agents.
2. In the page displayed, click Register RO Agent.

Fill in the required details.

| **Name**         | Enter the name of your choice for the RO Agent Configuration that is being created. |
| ---------------- | ----------------------------------------------------------------------------------- |
| **Host URL**     | The Host URL is the RO Agent URL that begins with http or https.                    |
| **Security Key** | Security Key value can be found in the agent.properties file.                       |

<figure><img src="https://www.docs.releaseowl.com/assets/img/test-configurations-1.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://www.docs.releaseowl.com/assets/img/test-configurations-2.jpg" alt=""><figcaption></figcaption></figure>

### **Pre-requisites**

* RO Agent and HCL OneTest UI should be installed on the same machine.

### **Test Configuration**

Setting up the test configuration allows the ReleaseOwl Application to run the HCL OneTest UI script with the specified parameters from the specified path through the RO Agent.

#### Create a new Test Configuration

1. In Project View, go to Test Configuration.
2. In the page displayed, click Create Test Configuration.

{% hint style="info" %}
**Note:** Test Configuration for Web UI and Functional Tests are to be created separately.
{% endhint %}

### **Test Configuration for Web UI Test**

<figure><img src="https://www.docs.releaseowl.com/assets/img/test-configurations-3.jpg" alt=""><figcaption></figcaption></figure>

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

### **Test Configuration for Functional Test** 

<figure><img src="https://www.docs.releaseowl.com/assets/img/test-configurations-4.jpg" alt=""><figcaption></figcaption></figure>

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
