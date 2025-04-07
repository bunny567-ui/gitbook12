# Version 2024.4

### **New Features & Enhancements** <a href="#pdf-page-ncgtjavtsbv6rkaxuxvf-new-features-and-enhancements" id="pdf-page-ncgtjavtsbv6rkaxuxvf-new-features-and-enhancements"></a>

**1. CRT (Copado Robotic Testing) Integration**

* Introduced integration with **CRT (Copado Robotic Testing)** for enhanced test automation.

**2. SAP Datasphere Deployment**

* Enabled deployment of **SAP Datasphere-related packages**, improving data management capabilities.

**3. DocuSign Integration**

* Implemented **DocuSign integration**, allowing seamless document signing workflows within ReleaseOwl.

**4. Freeze Period Implementation**

* Added a **Freeze Period** feature to restrict deployments during predefined timeframes.

**5. Integration Suite API Management**

* Introduced the ability to **deploy API Management-related artifacts**, including **API Proxies and Key-Value Pairs**.

**6. TR Group Import**

* Enhanced **Transport Request (TR) management** by enabling bulk TR imports in a user story, eliminating the need for one-by-one imports.

**7. Support for Different Object Types in Cloud Integration Suite**

* Improved compatibility by adding support for **SOAP, REST, and OData documents** in the Cloud Integration Suite.

### **Bug Fixes** <a href="#pdf-page-ncgtjavtsbv6rkaxuxvf-bug-fixes" id="pdf-page-ncgtjavtsbv6rkaxuxvf-bug-fixes"></a>

#### **Cloud Platform Integration (CPI) Fixes**

1. **(RP-658) CPI Rollback Restriction:** Prevented rollback to any version lower than the latest deployed version.
2. **(RP-659) CPI Test Generator:** Fixed issue where an empty error message appeared when an incorrect sequence ID was provided.
3. **(RP-661) CPI Value Mapping Deployment:** Resolved failure occurring when deploying a package and Value Mapping together in a user story.
4. **(RP-664) CPI Package Deployment:** Fixed an issue where lower versions of packages could still be deployed.
5. **(RP-666) CPI Deployment History:** Ensured the latest artifact in a package correctly displays deployment details.
6. **(RP-670) CPI Rollback Logs:** Deploy status is now visible in logs when "Upload and Deploy" is selected in the pipeline.
7. **(RP-675) CPI Deployment Dashboard:** Fixed an issue where deployment data was not visible in the dashboard.

### **API & Backend Fixes**

1. **(RP-795) API Response Fix:** The API response for retrieving the latest results now includes the **BuildPipeline ID**.
2. **(RP-769) SAC Role Concealment:** Fixed an issue where **SAC-related roles** were not concealed in MTAR-subscribed environments.
3. **(RP-770) CPI Artifact Sync:** Resolved errors encountered when syncing artifacts.
4. **(RP-774) DMOL Logs:** Attached **DMOL logs** to release-related emails for better traceability.
5. **(RP-785) Retrofit Retries:** Implemented **automatic retry** for retrofit in case of failure.

### **UI & Performance Improvements**

1. **(RP-786) Backend Pagination Fixes** for improved performance.
2. **(RP-792) UI Pagination Enhancements** across Build Pipeline, Build Result, Release Pipeline, Release Pipeline Cycles, and UI5 Upload Results.
3. **(RP-797) API for Retrofit Source Code Validation** added for improved validation processes.

### **SAP Transport Management & Release Fixes**

1. **(RP-808) SAP TR Objects Update:** Fetches updated TR objects whenever a TR is released or synced with the SAP system.
2. **(RP-811) Build Pipeline Credentials:** Credentials API replaced with parameters in the build pipeline for improved security.
3. **(RP-812) Retrofit View & API Fixes** to enhance user experience.
4. **(RP-814) Multiverse Project Fix:** Resolved an error occurring when opening a user story in edit mode.
5. **(RP-822) Bulk Import Support** added for user stories and pipelines.

### **Deployment & Environment Fixes**

1. **(RP-823) Release Pipeline Target System Visibility:** Fixed an issue where target systems were not visible in deployment tasks for the Transport Domain Controller.
2. **(RP-824) On-Premise TR Deployment Issues:** Addressed errors during TR deployments on **On-Premise environments**.
3. **(RP-825) On-Premise TR Editing:** Ensured **TRs from other projects** correctly display data when edited.
4. **(RP-826) Release Package Testing Issues:** Fixed problems encountered during testing of **release packages**.
5. **(RP-828) Test Evidence Task:** Now behaves similarly to **Approval Tasks**.
6. **(RP-830) SAP Datasphere Fix:** Ensured that `env_type` and `resource_type` for **SAP Datasphere environments** are saved correctly instead of being mistakenly assigned to SAC.
7. **(RP-834) Deployment History Fix:** Resolved an issue where environments were not shown in the deployment history of **CPI Artifacts, SAC Packages, SDS, API, TR, and MTAR**.

### **Other Fixes & Enhancements**

1. **(RP-835) Console View for Pipelines** implemented for better visibility.
2. **(RP-837) Transport Dialog Sync Removed:** Eliminated unnecessary sync for transport dialogs after promotion.
3. **(RP-690) Build Pipeline Node Version Selection:** Instead of manual entry, users can now select **supported Node.js versions** directly in the build pipeline.
