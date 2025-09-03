# RO Agents

The RO Agent is a standalone application designed to facilitate communication between integrations (such as Tosca) and ReleaseOwl. It executes various jobs on behalf of ReleaseOwl, including test case executions (e.g., Tosca).

## Steps to Set Up the RO Agent:

1. **Obtain the RO Agent**: Download the RO Agent as a ZIP file from the ReleaseOwl package.
2. **Extract the ZIP File**: Extract the contents to a directory of your choice.
3. **Launch the RO Agent**:
   * **For Windows**: Run the `.bat` file.
   * **For Linux/Mac**: Run the `.sh` file.

### Configuring the RO Agent

Follow these steps to configure the RO Agent

**1. Create a New RO Agent Configuration**

* Navigate to the **Administration** section in ReleaseOwl.
* Go to the **RO Agents** page.
* Click **Register RO Agent** to begin the setup process.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### 2. Fill in the Required Details

To complete the configuration, provide the following information:

* **Name**\
  Enter a meaningful name for your RO Agent configuration.
* **Host URL**\
  Specify the URL of the RO Agent. The URL should begin with `http` or `https`.
* **Security Key**\
  Open the `agent.properties` file located in the RO Agent directory. Copy the value of the **Security Key** and paste it here.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



