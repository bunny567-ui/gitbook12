# Test Execution Task

&#x20;ReleaseOwl can be integrated with HCL OneTest UI using which functional and web tests can be executed in any specific environment once the deployment is complete to check if the functionality is as desired. The following screen is displayed on adding a test execution task.\


<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

Fill in the required details:

| **Name**                      | Enter any name of your choice for the test execution task being created. **Note:** Only letters, numbers, underscores (\_), and periods (.) are permitted. |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Select Test Configuration** | Select appropriate test configuration from the list available that you have registered in the Test Configuration screen.                                   |
| **Description**               | Any message that is to be conveyed to the task performer can be mentioned here.                                                                            |
| **Test Execution**            | **Continue on Failure** – If selected, the Release Pipeline Execution will continue even if the test execution fails.                                      |
| **Dynamic Test Execution**    | When selected, runs tests linked to changed artifacts in the deployment (Integration Suite only)                                                           |



{% hint style="info" %}


**Note:**

1. **Any** task added can be deleted by clicking Remove
2. Please refer to **Automated CPI Deployments** and **Automated Transport Import** for information on **Deployment (CPI), Waiting for Promotion** and **Validation** tasks.
3. Please refer to **Automated MTAR Deployments, Automated CPI Deployments, Automated Transport Import** documents for their **respective Deployment** tasks.
{% endhint %}
