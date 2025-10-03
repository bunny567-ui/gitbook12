# Release Package Validation with Transports

Following are the actions that can be performed on every release package:

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

| Edit                  | To edit the release package                                                                                                                                                                                                                                                                                                                                                                                    |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Validate              | To trigger or initiate the validation of the package                                                                                                                                                                                                                                                                                                                                                           |
| Validation Report     | Validation Report appears enabled only upon validating the package                                                                                                                                                                                                                                                                                                                                             |
| Promote               | To trigger the associated release pipeline to promote the release package                                                                                                                                                                                                                                                                                                                                      |
| Pipeline Activity     | The view the execution status of the associated Release Pipeline upon promoting the release package.                                                                                                                                                                                                                                                                                                           |
| Lock                  | <p>To lock the release package before the execution of the release pipeline.<br>The Release Package gets automatically locked on promoting the Release Package.<br></p><p>You cannot add any user stories or transports once the release package gets locked.<br></p><p>But you can unlock if you have the required user role and need to make any changes to the Release Package in case of an emergency.</p> |
| Deployment History    | To view the deployment details such as the target environment where the deployment was done, user who has done the deployment, date done and any error message encountered.                                                                                                                                                                                                                                    |
| Audit History         | To keep track of the addition and deletion actions performed on a release package by any user.                                                                                                                                                                                                                                                                                                                 |
| Archive               | <p>To archive any release package. Once a release package is archived, you can view them under the Archived Packages.<br>By default, you can view <strong>Active Packages.</strong></p>                                                                                                                                                                                                                        |
| Release Audit Report  | You can **export the details of transports** as a **Release Audit Report**                                                                                                                                                                                                                                                                                                                                     |

### **Validation Report**

Validation report is visible only after the validation process is complete. To view the validation report:

1\. Go to a required package and click **Actions**. Click **Validation Report.**

2\. The validation report for a successful validation is displayed below.

<figure><img src="../../.gitbook/assets/image (1132).png" alt=""><figcaption></figcaption></figure>

3\. The validation report for a failed validation is displayed below:\


<figure><img src="../../.gitbook/assets/image (1130).png" alt=""><figcaption></figcaption></figure>

The following details are available in the Validation Report:

1\) **Transport Requests** – Shows the number of transport requests that are a part of the release package.

2\) **Tests Success %** – (Number of tests that were successful/Total Number of test)\*100

3\) **Code Coverage %** - Code Coverage Average for all the unit test objects.

<figure><img src="../../.gitbook/assets/image (1135).png" alt=""><figcaption></figcaption></figure>

4\) **TR Report** – By default, the user can view the TR (Transport Request) Report. It has the following checks done:

a) **Release Status Check:** This option shows the user whether the transport requests were released successfully or not. On clicking **Details**, you can view the Transport Requests that are a part of the Release Package and their Release Status.\


<figure><img src="../../.gitbook/assets/image (1133).png" alt=""><figcaption></figcaption></figure>

b) **Downgrade Protection Check:** This option is for identifying any dependencies between transports containing the same object, sub-object or customizing keys. An error is displayed when two transports with identical objects are imported in a wrong sequence.

c) **Cross Reference Check (Dependencies):** The cross-reference check is done to detect inconsistencies for objects that are referenced in transport requests.

d) **Cross Release Check (Package level checks):** For SAP standard objects, an error is displayed when a release package level is different between the source and target system for the corresponding software component.

<figure><img src="../../.gitbook/assets/image (1140).png" alt=""><figcaption></figcaption></figure>

e) **Critical Object Check:** This is to determine if transport requests contain critical transport objects, which require approval before they can be exported from the development system.

<figure><img src="../../.gitbook/assets/image (1141).png" alt=""><figcaption></figcaption></figure>

5\) **Test Execution Report –** The details of the test executed can be seen as follows:

<figure><img src="../../.gitbook/assets/image (1137).png" alt=""><figcaption></figcaption></figure>

\
6\) **Code Coverage –** The Code Coverage Summary can be seen as follows:

<figure><img src="../../.gitbook/assets/image (1139).png" alt=""><figcaption></figcaption></figure>

\
7\) **ATC Report -** ABAP Test Cockpit (ATC) is completely integrated into Object Navigator and Transport Organizer and executes and displays results for various tests on development objects, for example:

* Static performance tests
* Static usability tests
* Extended program checks
* Package checks
* Security Checks

8\) Click **Details** to see further info on Errors and Warnings.\


<figure><img src="../../.gitbook/assets/image (363).png" alt=""><figcaption></figcaption></figure>

