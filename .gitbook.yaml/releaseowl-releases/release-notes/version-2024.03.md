# Version 2024.03

### **New Features & Enhancements** <a href="#pdf-page-itv3uqgpx0droghjqrjp-new-features-and-enhancements" id="pdf-page-itv3uqgpx0droghjqrjp-new-features-and-enhancements"></a>

**1. UiPath Integration**

* Introduced integration with **UiPath** to enhance automation capabilities.

**2. Callback from Build Agent to Update Build Status**

* Implemented a callback mechanism for the build agent to **update build status** in pipelines instead of polling, improving efficiency and reducing latency.

**3. Application Link in Account Activation Email**

* Added an **application link** in the ReleaseOwl account activation email for easier access.

**4. User Story Comments**

* Users can now **add comments to user stories**, similar to transport management in other environments.

**5. Number of Builds to Hold for Pipelines**

* Implemented an option to **define the number of builds** to retain for build pipelines.

**6. CPI Test Tool Enhancements**

* Made **significant enhancements** to the **CPI test tool** to improve functionality.

**7. Service User for SAP On-Premise**

* Now displays the **Service User** instead of the promoting user while updating comments in user stories.

**8. Cluster Support for Scheduling Build Pipelines**

* Added support for **clustering** when scheduling build pipelines, enhancing **scalability and reliability**.

**9. Malware Execute Scan**

* Integrated a **malware execution scan** to enhance security.

**10. Continue on Failure in Release Pipeline for Test Execution**

* Introduced an option to **continue execution on failure** in release pipelines, specifically for test execution.

### **Performance Improvements** <a href="#pdf-page-itv3uqgpx0droghjqrjp-performance-improvements" id="pdf-page-itv3uqgpx0droghjqrjp-performance-improvements"></a>

**1. Build Pipeline Performance**

* Addressed **backend performance issues**, resulting in **faster and more reliable** build pipeline execution.

### **Bug Fixes** <a href="#pdf-page-itv3uqgpx0droghjqrjp-bug-fixes" id="pdf-page-itv3uqgpx0droghjqrjp-bug-fixes"></a>

**1. CPI Environment Issues**

* Fixed an issue where **IFLOW OAuth credentials and IFLOW API URL** were incorrectly marked as mandatory.

**2. Activity Log Updates**

* Resolved an issue where the **Activity Log** required a manual refresh to update.

**3. SAP Cloud Environment Edit Issue**

* Fixed a **busy indicator issue** occurring when the organization call failed during SAP Cloud environment edits.

**4. CPI Scenario Approval Error**

* Addressed an **approval error** that occurred after a rollback in the pipeline.

**5. User Email Visibility in Logs**

* Fixed an issue where **ReleaseOwl user email IDs** were visible in the build pipeline logs.

**6. Pipeline Activity in User Stories**

* Fixed an issue where **pipeline activity in user stories** was not functioning correctly.

**7. Build Pipeline Naming Issue**

* Resolved an issue where **build pipelines with the same name** appeared in different projects.

**8. Validations in Release Pipeline Approvals**

* Corrected an issue where a release pipeline could be saved **without selecting a user/role** in the approval task.

**9. CPI Promote Button Visibility**

* Fixed an issue where the **Promote button** was visible even when the release pipeline was not assigned.

**10. Project Types Based on Licenses**

* Ensured that **project types** in settings and different sections of user stories/release packages are shown **based on licenses** for multiverse projects.

**11. Associating Multiple Release Pipelines**

* Fixed an issue where associating **multiple release pipelines** with the “On-Successful Build Pipeline” option was **not working**.

**12. CPI Artifact Fetching**

* Resolved an issue where **artifacts** could not be fetched from the last package.

**13. SonarQube Credential Selection**

* Fixed an issue where **default SonarQube credentials (e.g., SONAR OnPrem)** were not retained upon editing.

**14. Transport Management Description Field**

* Changed the **field name** from **"Name"** to **"Description"** in transport management.

**15. Mandatory Stage & Task in Release Pipelines**

* Ensured that at least **one stage and one task** are mandatory in a release pipeline.
