# Deployment Task

A **Deployment Task** is a pipeline action that defines _how_ an artifact is delivered, installed, or transported to a designated SAP target system as part of an automated release process. It acts as the execution unit responsible for deploying one or more artifact types—such as SAP Transport Requests (TRs), MTAR packages, or CPI artifacts—to their respective runtime environments.

Within a release pipeline, the Deployment Task performs the operational steps required to move software changes from development or staging environments into higher-level systems (such as QA, Pre-Prod, or Production). This ensures consistent, accurate, and traceable deployments across all stages of the delivery lifecycle.

## **Different Deployment Tasks**

A Deployment Task supports multiple artifact categories, each with its own deployment flow, configuration parameters, and target environment. The three primary deployment types are **CPI Deployment**, **MTAR Deployment**, and **Transport Management Deployment**. Each serves a different layer of the SAP landscape and enables automated, reliable delivery across the release pipeline.

### **1. CPI Deployment Task (SAP Integration Suite Artifacts)**

The **CPI Deployment Task** handles the automated deployment of integration artifacts into an SAP Integration Suite (CPI) tenant. These artifacts may include iFlows, APIs, value mappings, scripts, or other integration components packaged within a CPI project.

<figure><img src="../../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **CPI -Deployment Task Configuration**

| **Field**                 | **Description**                                                                                                                                               |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                  | Enter any name of your choice for the deployment task being created.                                                                                          |
| **Description**           | Add any message or note that needs to be conveyed regarding the deployment.                                                                                   |
| **Upload and Deploy**     | CPI artifacts are uploaded to the design-time workspace of the target environment and then published to the runtime.                                          |
| **Upload Only**           | CPI artifacts are uploaded only to the design-time workspace of the target environment without being deployed to runtime.                                     |
| **Enable Rollback**       | Creates a backup version of the destination artifact, allowing you to roll back to the previous version if required.                                          |
| **Notify Users**          | Sends an email notification to all users associated with the pipeline when it is triggered or when specific pipeline events occur.                            |
| **Notify Promotion User** | Sends an email notification to the user who initiated the promotion (from a User Story or Release Package), regardless of whether the task succeeds or fails. |
| **Schedule Time**         | Allows a Release Pipeline to be executed manually or scheduled automatically after its reference build pipeline completes successfully.                       |

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **2. MTAR- Deployment Task Configuration**

The **Deploy task** deploys the built MTAR artifact to the target SAP Cloud environment.

| Field                                             | Type     | Description                                                           |
| ------------------------------------------------- | -------- | --------------------------------------------------------------------- |
| **Name / Description**                            | Text     | Task identity.                                                        |
| **Select Environment(s)**                         | Dropdown | The target environment to deploy to.                                  |
| **Select Build Task**                             | Dropdown | The Build task whose artifact is deployed.                            |
| **Upload Artifact to Cloud Transport Management** | Checkbox | Optionally uploads the MTAR to SAP Cloud Transport Management (CTMS). |
| **Keep Logs for (Days)**                          | Number   | Retention period for deployment logs.                                 |
| **Notify Users / Notify Promotion User**          | Checkbox | Notification options.                                                 |
| **Schedule Time**                                 | Checkbox | Schedules the deployment for a later time.                            |

The MTA extension files applied during deployment are taken from those associated with the target environment in the **Landscape Configuration**.

<figure><img src="../../../.gitbook/assets/image (2190).png" alt=""><figcaption></figcaption></figure>

### **3. Transport Management Deployment Task (SAP ABAP Transport Requests)**

The **Transport Management Deployment Task** handles deployment for **SAP Transport Requests (TRs)** in ABAP-based systems, such as S/4HANA, ECC, SAP BW, or SAP CRM.

### **Transport Management – Deployment Task Configuration**

| **Field**                  | **Description**                                                                                                                                      |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                   | Deployment task name.                                                                                                                                |
| **Domain Controller**      | Select the appropriate Transport Domain Controller, which is the system responsible for managing changes within the SAP Transport Management System. |
| **Target System**          | Enter the target system that should receive and be updated with the changes from the source system.                                                  |
| **Schedule Time**          | Allows you to specify a future date and time for automatic execution of the deployment task.                                                         |
| **Notify Users**           | Sends deployment status notifications (Success/Failure) to all users associated with the pipeline stage.                                             |
| **Notify Transport Users** | Sends notifications only to users associated with the specific transports being deployed, ensuring targeted communication.                           |
| **Notify Promotion User**  | Sends notifications to the user who promoted the user story or release package that triggered the deployment.                                        |
| **Description**            | A free-text field where notes or additional information about the deployment can be provided. Useful for context or specific instructions.           |

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **4. SAC Deployment Task (SAP Analytics Cloud Artifacts)**

The SAC Deployment Task handles the automated deployment of SAP Analytics Cloud content — stories, models, and other analytic artifacts organized as SAC packages — from the source tenant to a target SAC tenant.

#### SAC Deployment Task Configuration

| Field                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                   | Deployment task name.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Description**            | A free-text field where notes or additional information about the deployment can be provided. Useful for context or specific instructions.                                                                                                                                                                                                                                                                                                                                        |
| **Select SAC Environment** | Select the registered SAP Analytics Cloud environment into which the packages should be imported.                                                                                                                                                                                                                                                                                                                                                                                 |
| **Overwrite Preferences**  | Choose whether to overwrite existing objects while importing objects with the same name as those on the target system. New objects are always imported. Options: **Don't overwrite objects or data** — avoids overwriting any existing content; **Overwrite data only** — overwrites the data of existing objects without making changes to the structure of your models; **Overwrite objects and data** — imports all selected content, and existing objects can be overwritten. |
| **Include Data**           | When enabled, the import includes the data of the selected content along with the objects.                                                                                                                                                                                                                                                                                                                                                                                        |
| **Schedule Time**          | Allows you to specify a future date and time for automatic execution of the deployment task.                                                                                                                                                                                                                                                                                                                                                                                      |
| **Notify Users**           | Sends deployment status notifications (Success/Failure) to all users associated with the pipeline stage.                                                                                                                                                                                                                                                                                                                                                                          |
| **Notify Promotion User**  | Sends notifications to the user who promoted the user story or release package that triggered the deployment.                                                                                                                                                                                                                                                                                                                                                                     |

<div><figure><img src="../../../.gitbook/assets/image (2270).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (2271).png" alt=""><figcaption></figcaption></figure></div>

### 5. SDS Deployment Task (SAP Datasphere Packages)

The SDS Deployment Task deploys SAP Datasphere packages to the target Datasphere tenant. The package version assigned to the user story is imported into the target space defined by the **Space Mapping** maintained between the source and target environments.

#### **SDS – Deployment Task Configuration**

| Field                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**                   | Deployment task name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Description**            | A free-text field where notes or additional information about the deployment can be provided. Useful for context or specific instructions.                                                                                                                                                                                                                                                                                                                                                                                    |
| **SDS Environment**        | Select the registered SAP Datasphere environment into which the packages should be imported. The content is imported into the target space defined by the Space Mapping of the source and target environments.                                                                                                                                                                                                                                                                                                                |
| **Overwrite Preferences**  | Choose whether to overwrite existing objects while importing objects with the same name as those on the target system. New objects are always imported. Options: **Don't overwrite objects or data** — avoids overwriting any existing content; **Overwrite data only** — overwrites the data of existing objects without making changes to the structure of your models; **Overwrite objects and data** — imports all selected content, and existing objects can be overwritten (enables the **Remote Permissions** option). |
| **Deployment Preferences** | **Deploy after import** — when enabled, the imported objects are deployed in the target tenant immediately after the import completes; otherwise they remain imported but not deployed.                                                                                                                                                                                                                                                                                                                                       |
| **Schedule Time**          | Allows you to specify a future date and time for automatic execution of the deployment task.                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Notify Users**           | Sends deployment status notifications (Success/Failure) to all users associated with the pipeline stage.                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Notify Promotion User**  | Sends notifications to the user who promoted the user story or release package that triggered the deployment.                                                                                                                                                                                                                                                                                                                                                                                                                 |

<div><figure><img src="../../../.gitbook/assets/image (2268).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../../.gitbook/assets/image (2269).png" alt=""><figcaption></figcaption></figure></div>

