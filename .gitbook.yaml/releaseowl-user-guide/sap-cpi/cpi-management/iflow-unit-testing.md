# iFlow Unit Testing

The Cloud Integration Unit Test creation and execution in ReleaseOwl is achieved through Simulation feature in SAP Cloud Integration Suite: ([Simulation of an Integration Flow | SAP Help Portal](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/2e2210b6db0c4fdb937b3a57d952f582.html))\
Go to the ‘**Test Generator’** tab, input all the required details. The required details are as follows:

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



You can obtain the Start and End Sequence ID from your SAP landscape by selecting the point and copying the start and end sequence IDs.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FJgRYkAGljkRLwYsYhCp8%252Fimage.png%3Falt%3Dmedia%26token%3D4fa6e968-3759-4fbf-bdb9-2e3671a160f7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b97ce51c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

Once the test case is created, select **‘Run’.**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FT6Q1LRTseGY0KgSRTUEK%252Fimage.png%3Falt%3Dmedia%26token%3D4700fe80-ecaf-44b6-9c05-ea3d848988ef&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6370e36d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

You can click on **‘View Latest Result’** to see the latest test case report.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FckcOQcOQDHEHIEtrudVF%252Fimage.png%3Falt%3Dmedia%26token%3D109029d2-62c7-4fc2-8e0b-89817a8be477&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=30730c1a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

Here, the **Run ID** is the unique test run ID; the **Artifact Name** is the one you specify while creating the test run. The **Expected Output** is the same as specified while creating the test run, and the **Actual Output** is the output received after running the test, in which case, the Property Differences between the two are given at the bottom.&#x20;

Alternatively, you can view the ‘**Test Results**’ tab to view a history of all the test results. Here you will view a list of Run IDs that pertain to specific user stories or release packages that have been validated. A user may run group of tests together. In the case of User Stories or Release Packages, all the validation tests associated with artifacts from the selected User Story will be executed as a single suite. The below screen displays all such test execution groups.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FzggUWonEo2ebYZXka7i7%252Fimage.png%3Falt%3Dmedia%26token%3D57f72f03-4235-4465-8fd4-7e08fb583cc0&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=48eaa56d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

You can click on a **‘Run ID’** to view all the test cases that fall under that run ID. Selecting **‘Details’** will further take you back to the ‘Latest Results’ page.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FMJugjlEjHVxtNgZTJzTA%252Fimage.png%3Falt%3Dmedia%26token%3D1ef5ef59-ff47-41af-ad80-d8c5ecf50cdf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f28cd164&#x26;sv=2" alt=""><figcaption></figcaption></figure>

Apart from this, the **Test Case** can also be run via the **User Stories** tab, by clicking on the **Validate** button. When validated, all the test cases associated with the iFlow artifacts linked to the particular user story or release package you have validated will be executed.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FXpP3N2E9YGXscFKEkp8k%252Fimage.png%3Falt%3Dmedia%26token%3D1b8baac3-f5f1-4784-96aa-9d28cfcd0ec4&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f695f57f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

The **Test Results** can be viewed in the **Validation Report** generated during User Story and Release Package validation.

The Validation Report can also be viewed from the **Release Packages** tab.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fe8cdYzakUbZNhrATCUfB%252Fimage.png%3Falt%3Dmedia%26token%3D7c1384de-8aab-456b-805c-053efa690a65&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f3a0f646&#x26;sv=2" alt=""><figcaption></figcaption></figure>



