# Version 2025.4

### New Features

#### &#x20;Release Pipeline- **Save As Functionality**

You can now use the **“Save As”** option to duplicate an existing Release Pipeline and create a new one with a different name.

<figure><img src="../../.gitbook/assets/image (986).png" alt=""><figcaption></figcaption></figure>

#### Build Pipeline- **Save As Functionality**

The Build Pipeline also supports a **“Save As”** feature to quickly create a copy with a new name.

<figure><img src="../../.gitbook/assets/image (987).png" alt=""><figcaption></figcaption></figure>

#### 📝 User Stories- **Delete Functionality**

Users can now delete User Stories. _(Note: Available only for Release Owl Change Management users.)_

<figure><img src="../../.gitbook/assets/image (988).png" alt=""><figcaption></figcaption></figure>

### &#x20;Improvements

#### Change Management – User Stories

* **Validation Status Filter**\
  Added a column-level dropdown filter for validation status in the User Stories table.
* **Sync Status Message**\
  A message will now appear while a user story is syncing.

<figure><img src="../../.gitbook/assets/image (989).png" alt=""><figcaption></figcaption></figure>

#### Build – Transport Management

* **Validation Status Filter**\
  Added a dropdown filter for validation status.
* **Permission Verification**\
  Deployment permissions are now checked before importing via TOC.

<figure><img src="../../.gitbook/assets/image (990).png" alt=""><figcaption></figcaption></figure>

#### &#x20;Build – Build Pipeline

* **Created By & Created On Columns**\
  New columns display who created the pipeline and when.

<figure><img src="../../.gitbook/assets/image (991).png" alt=""><figcaption></figcaption></figure>

#### Release – Release Pipeline

*   **User Notifications**

    * Added a Notify option to notify users in the gCTS switch task(On-Premise).

    <figure><img src="../../.gitbook/assets/image (993).png" alt=""><figcaption></figcaption></figure>

    * Added a Notify option to notify users in the wait for Promotion Task

    <figure><img src="../../.gitbook/assets/image (994).png" alt=""><figcaption></figcaption></figure>
* **Release History Access**\
  You can now view the history of the Release Pipeline.

<figure><img src="../../.gitbook/assets/image (996).png" alt=""><figcaption></figcaption></figure>

#### Pipeline Activity

* **TOC Log Updates**\
  Logs now show SAP TR ID and RO ID, even if subtasks are missing.
* **Rollback Handling**\
  CPI rollback completion now allows the same User Story to be promoted again.

<figure><img src="../../.gitbook/assets/image (997).png" alt=""><figcaption></figcaption></figure>

* **Deployment Email Updates**\
  Enhanced email format and updated User Story details in task updates.

#### My Tasks

* **Attachments View**\
  Task details now show User Story attachments.
* **Quick Navigation**\
  Navigate directly to User Story, Transport, and Artifact (CPI, SAC, SDS) details.

<figure><img src="../../.gitbook/assets/image (998).png" alt=""><figcaption></figcaption></figure>

* **Search Field**\
  Search tasks efficiently with the new filter bar.
*   **Column-Level Filters**

    * Filter by Task Type
    * Filter by Task Source

    <figure><img src="../../.gitbook/assets/image (999).png" alt=""><figcaption></figcaption></figure>

#### &#x20;Test Automation

* **Pre-Validation**\
  Added validation before creating Test Configurations.

<figure><img src="../../.gitbook/assets/image (1000).png" alt=""><figcaption></figcaption></figure>

#### &#x20;ALM Integration

* **Disable Comments**\
  Option added to turn off comments within ALM Integration.

<figure><img src="../../.gitbook/assets/image (1001).png" alt=""><figcaption></figcaption></figure>

#### Administration

* **Validation Enhancements**\
  Checks added before creating RO Agents, Callouts, or defining Freeze Periods.
* **License Expiry Checks**\
  Project creation or switching is now blocked if the module license has expired.

<figure><img src="../../.gitbook/assets/image (1002).png" alt=""><figcaption></figcaption></figure>

&#x20;

<figure><img src="../../.gitbook/assets/image (1005).png" alt=""><figcaption></figcaption></figure>

### Bug Fixes

* **Promotion Validation**\
  Users will now be prompted if the Component field is empty during promotion.
* **User Story Filter Fix**\
  Resolved an issue with filters when adding stories to a release package.
* **Sprint View Enhancement**\
  Pipeline Activity button added in Sprint User Stories.
* **Test Retry Button**\
  Retry failed test executions in the Release Pipeline.
* **Duplicate User Check**\
  Fixed an issue where users could be created with the same email.
* **Component Mail Notification**\
  Fixed errors in component-based email notifications.
* **TestEvidence Attachments**\
  Attachment logic corrected based on the current task index.

### Known Issues

*   **Name Validation Rules**\
    Only the following characters are allowed:

    * Letters
    * Numbers
    * Hyphens (-)
    * Underscores (\_)
    * Periods (.)\
      Special characters are not allowed.

    <figure><img src="../../.gitbook/assets/image (1006).png" alt=""><figcaption></figcaption></figure>

### Additional Notes

* The option to assign an approval task to the **User Story assignee** has been **removed** to improve process governance.

