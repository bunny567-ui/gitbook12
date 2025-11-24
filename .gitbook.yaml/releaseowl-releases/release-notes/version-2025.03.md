# Version 2025.3

### **New Features**

1.  **CPI Test Generator - Run On**

    * Introduced a “**Run On**” option for both Test Suites and Test Cases.
    * Allows users to execute tests based on the selected environment.

    <figure><img src="../../.gitbook/assets/image (982).png" alt=""><figcaption></figcaption></figure>
2.  **Deputy Users**

    * Added a Deputy Users feature under Profile.
    * Allows users to approve or reject tasks in _My Tasks_ on behalf of someone else.
    * If the original assignee is unavailable, they can delegate the task to another user within the same project.
    * Only one deputy can be assigned per project at a time.

    <figure><img src="../../.gitbook/assets/image (984).png" alt=""><figcaption></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (985).png" alt=""><figcaption></figcaption></figure>

### **Improvements**

#### **Dashboard**

* Added _Pipeline Stage_ and _Pipeline Status_ information to the Release Pipeline Cycles table.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Change Management - User Stories**

* Introduced a dropdown filter for _User Story Type_.
* Added _Modified By_ and _Modified On_ columns.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) ( (3).png" alt=""><figcaption></figcaption></figure>

* Included _ALM Integration_ and _Sprint_ columns in the Sync History table.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Transport Management**

* Added filters for _Transport Type_, _Status_, and _Last Imported System_.
* Enabled Excel download for exporting transport details.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* In gCTS, clicking on a Commit ID now displays the list of files.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Added _TOC request details_ to the Import History section.

#### **API Management**

* Values in Key Value Maps (KVMs) are now shown based on the type:
  * Encrypted KVMs display values securely in encrypted form.
  * Plain text KVMs display values in readable form.

#### **Build Pipeline Enhancements**

* Added support for Version Control Platform input when creating a build pipeline.
* Enables navigation to commits and improves version control integration.

#### **Release Pipeline Enhancements**

* Introduced a _Notify_ option for users waiting on promotion tasks.

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* b. Added a **Description field** to all tasks in the Release Pipeline to provide detailed information about each task.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

*   Improved task name validation:

    * Only letters, numbers, hyphens (-), underscores (\_), and periods (.) are allowed.

    <figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Pipeline Activity Enhancements**

* Rollback button is hidden after completion for CPI deployments.
* Added TOC ID details to On-Premise deployment logs.
* Deployment tasks now display retry metadata: _Last Retry By_ and _Last Retry On_.

<figure><img src="../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Transport type is now shown in On-Premise deployment logs.
* Integration Advisor deploy logs now include _Consistency Check_ and _Import Logs_.

<figure><img src="../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **CPI Test Generator Enhancements**

* _Last Test Results_ and _Test Runs_ are now accessible from the action buttons on both Test Suites and Test Cases.

<figure><img src="../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (12) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* New columns added to the message table during test case creation:
  * `messageType`, `multicastIndex`, `splitIndex`, `branchId`, and `childCount`
* Excel download functionality added for CPI test results.

<figure><img src="../../.gitbook/assets/image (13) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Update History now includes _Commit ID_ and _Branch_ columns.
* Test Run Results now display _Artifact Version_ and _Test Suite_.
* Mock Endpoints field is now visible in the Test Case view.
* Test Run Details now include _Artifact Version_, _Mock Run_, and _headerProps_ for improved debugging.

#### **ALM Integration**

* Once created, ALM settings cannot be edited, except for:
  * _Jira JQL_
  * _Disable writing comments/notes_
* Added a checkbox to enable/disable automatic comment writing on Jira user stories.
* _Web Request URL_ field is now automatically populated during integration setup.

#### Administration > Environment

* Changed label from **“IFlow API URL”** to **“IFLOW URL”** in CPI environment setup.

<figure><img src="../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Static Code Analysis - CPI Rules**

* Enhanced CPI linting to account for allowed user role values, improving test case validation.

<figure><img src="../../.gitbook/assets/image (16) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Bug Fixes**

* Fixed issue where the _Sync History_ dialog would not open in User Stories.
* Corrected filtering behavior to properly apply _User Story ID_ filters based on ALM integration and sprint.
* Transport Management filters now support: _Transport ID_, _Status_, _Type_, _User Story Owner_, and _Description_.
* Manual tasks are now automatically set to “Done” if a pipeline is aborted—cannot be approved or rejected manually.
* Resolved an issue with CPI logs not displaying “Downgrade check failed” messages.
* Continuous Deployment (On-Premise) is now allowed even when transports are imported with warnings.



### **Known Issues**

* **Task Name Validation**:
  * Only letters, numbers, hyphens (-), underscores (\_), and periods (.) are allowed.
  * Special characters are not supported.
