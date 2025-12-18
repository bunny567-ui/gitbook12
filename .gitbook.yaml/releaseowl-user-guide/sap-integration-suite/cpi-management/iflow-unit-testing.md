# iFlow Unit Testing

The Cloud Integration Unit Test creation and execution in ReleaseOwl is achieved through Simulation feature in SAP Cloud Integration Suite: ([Simulation of an Integration Flow | SAP Help Portal](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/2e2210b6db0c4fdb937b3a57d952f582.html))\
Go to the ‘**Unit Test Cases’** tab, input all the required details. The required details are as follows:

<figure><img src="../../../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

| **Name**                    | Name for identifying a test case                                                                                                                                           |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Disable Test Case:**      | During validation multiple test cases associated to CPI Artifact will be executed, if this option is selected then this test case will be ignored during group execution.  |
| **Artifact Name**           | From the lookup select the artifact for which the test case should be executed.                                                                                            |
| **Start & End Sequence ID** | These are sequence IDs which tells where to start point for execution and end point for execution. The values for these can be taken as shown in the attached screen shot. |
| **Input Headers**           | These are key - value pairs that will sent as input headers to simulation.                                                                                                 |
| **Input Properties**        | These are also key - value pairs that will be sent as input to simulation.                                                                                                 |
| **Input Payload**           | This is the payload that is sent as input to the first activity for the start sequence ID in simulation. This could be xml or Json.                                        |
| **Expected Output Payload** | This is the expected output after execution of last activity attached to end sequence ID. This could be xml or Json.                                                       |
| **Expected Output Headers** | These are the Key - value pairs that will be the output of the last activity in the simulation.                                                                            |
| **Ignore Properties**       | These are comma separated paths to ignore during comparison of input and expected output payload                                                                           |



* You can obtain the Start and End Sequence ID from your SAP landscape by selecting the point and copying the start and end sequence IDs.
* Once the test case is created, select **‘Run’.**

<figure><img src="../../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

You can click on **‘View Latest Result’** to see the latest test case report.

<figure><img src="../../../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

Here, the **Run ID** is the unique test run ID; the **Artifact Name** is the one you specify while creating the test run. The **Expected Output** is the same as specified while creating the test run, and the **Actual Output** is the output received after running the test, in which case, the Property Differences between the two are given at the bottom.&#x20;

Alternatively, you can view the ‘**Test Results**’ tab to view a history of all the test results. Here you will view a list of Run IDs that pertain to specific user stories or release packages that have been validated. A user may run group of tests together. In the case of User Stories or Release Packages, all the validation tests associated with artifacts from the selected User Story will be executed as a single suite. The below screen displays all such test execution groups.

<figure><img src="../../../.gitbook/assets/image (81).png" alt=""><figcaption></figcaption></figure>

You can click on a **‘Run ID’** to view all the test cases that fall under that run ID. Selecting **‘Details’** will further take you back to the **‘Latest Results**’ page.

<figure><img src="../../../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

Apart from this, the **Test Case** can also be run via the **User Stories** tab, by clicking on the **Validate** button. When validated, all the test cases associated with the iFlow artifacts linked to the particular user story or release package you have validated will be executed.

<figure><img src="../../../.gitbook/assets/image (83).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :** The **Test Results** can be viewed in the **Validation Report** generated during User Story and Release Package validation. The Validation Report can also be viewed from the **Release Packages** tab.
{% endhint %}





