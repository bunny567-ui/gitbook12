# CPI Monitoring

CPI Monitoring enables runtime visibility into SAP Cloud Integration artifacts and provides access to execution logs, including failed and retried message processing details. To configure and use CPI Monitoring in ReleaseOwl, ensure the following prerequisites are met:

#### **1. SAP CPI Role Requirement**

The SAP Cloud Integration instance must have the appropriate monitoring authorization assigned.

* The service user configured in ReleaseOwl must have the **MonitoringDataRead** role.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* This role must be assigned while creating or configuring the SAP Integration Suite instance.
* Without this role, ReleaseOwl will not be able to fetch runtime logs or message processing details.

#### **2. CPI Environment Configuration in ReleaseOwl**

* The SAP CPI environment must be registered in ReleaseOwl under the respective project.
* CPI Monitoring must be explicitly enabled at the environment level within ReleaseOwl.
* Once enabled, ReleaseOwl fetches up to **2000 message processing records** per execution cycle.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### **3. Log Retrieval Scope**

Currently, ReleaseOwl retrieves:

* Failed messages
* Retried messages
* Other non-completed execution statuses

Successful message executions are not included in the default monitoring fetch.

### **Accessing CPI Monitoring**

1. Log in to the ReleaseOwl Dashboard.
2. Navigate to: **Project Management → Monitoring → CPI Monitoring**.
3. Select the appropriate **Project** and **CPI Environment** from the dropdown.

{% hint style="info" %}
**Note :** Monitoring data is displayed only for projects linked to a configured CPI environment.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### **Using Monitoring Filters**

The CPI Monitoring screen provides multiple filters to refine runtime log results:

* **Time** –  The **Time** filter allows users to define the monitoring window for message retrieval.
* **Status** – The **Status** filter allows users to view messages based on their execution outcome.
* **Type** – The **Type** filter defines the artifact category.
* **Package** – The **Package** filter enables users to select a specific CPI package.
* **Artifacts** – The **Artifacts** filter allows users to select one or more specific integration flows (iFlows).

After applying filters, the grid updates automatically with matching message processing records.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

#### **Understanding the Monitoring Grid**

The monitoring table displays the following details:

* **Artifact Name** – This column displays the name of the CPI artifact (typically an iFlow) that processed the message.
* **Message ID** – The Message ID is a unique technical identifier assigned to each message execution in CPI.
* **Type** –  This column indicates the artifact type.
* **Started On** – This column shows the exact date and time when the message processing began.
* **Status** – The Status column indicates the current processing state of the message.

Each row represents a single message processing instance.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

#### **Viewing Detailed Execution Information**

1. Click on an **Artifact Name** from the monitoring grid.
2. The right-side panel displays detailed information under the following tabs:

**Status**

* Displays execution result.
* Shows error message if processing failed.

**Properties:** Displays runtime metadata and technical properties.

**Artifact Details:** Shows additional artifact-level information related to the execution.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

#### **Error Analysis and Troubleshooting**

If a message is marked as **Failed**:

1. Review the error message in the **Status** tab.
2. Identify the root cause (e.g., HTTP error, adapter issue, authentication failure, mapping error).
3. Make the necessary correction in the CPI iFlow.
4. Redeploy the artifact if required.
5. Re-trigger the integration from the source system.

#### **Refreshing Monitoring Data**

* Click the **Refresh** icon to fetch the latest message processing records.
* ReleaseOwl retrieves up to **2000 non-completed records** per fetch cycle.
* Verify that subsequent executions move to a successful state after corrective actions.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

#### **Accessing CPI Alert Configurations**

**Alert Configuration:** Automated failure alerts are triggered when a configured integration package or iFlow execution fails in the selected CPI environment. Upon failure, ReleaseOwl generates an alert entry and notifies the configured recipients.

1. Log in to the **ReleaseOwl Dashboard**.
2. Navigate to: **Monitoring → Alerts**
3. Click on the " **Create Alert Configuration.**"

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

4. Fill in the following details:&#x20;

* **Name** –  A unique and identifiable name representing the purpose and environment of the alert.
* **Description** – Sends email notifications for failed iFlow executions.
* **Environment** - Select the appropriate CPI environment from the dropdown list. Alerts will monitor runtime failures only for the selected environment.
* **Active** – When enabled, the alert configuration is active and notifications will be sent.
* **Similar Error Notification Interval (Minutes)** – Defines the minimum time gap between repeated notifications for the same error. If the same error occurs multiple times within 10 minutes, only one notification will be sent. This prevents alert flooding and reduces duplicate email notifications.
* **Artifacts** - When you click the **+ Add** button, you can select and add specific CPI packages or individual artifacts to the alert configuration. This defines the scope of integrations that will be monitored under the alert rule.

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

After clicking the **Save** button in the Alert Configuration screen, the system redirects to the **CPI Alerts Monitoring** page. This screen displays real-time alert-triggered message details based on the configured alert rules.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

#### **Top-Level Filters**

The following filters are available in the CPI Alerts screen to refine and analyze alert-triggered messages:

| **Filter Name**          | **Description**                                                                                                                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Environment**          | Displays the selected CPI environment. Only alerts triggered within the selected environment are shown.                                                                                                |
| **Alert Configurations** | Allows selection of a specific alert configuration . The grid displays only the messages that triggered this selected alert rule.                                                                      |
| **Group By**             | Enables grouping of alert records based on defined criteria. When set to **None**, alerts are displayed individually without grouping.                                                                 |
| **Time**                 | Filters alert records based on the selected time range. Useful for reviewing alerts within a specific monitoring window.                                                                               |
| **Alert Status**         | Filters alerts by their current lifecycle status: • **Open** – Alert is active and unresolved. • **Resolved** – Alert has been marked as resolved. • **All** – Displays both Open and Resolved alerts. |
| **Type**                 | Filters alerts based on the artifact type.                                                                                                                                                             |
| **Package**              | Filters alerts based on the CPI package to which the artifact belongs.                                                                                                                                 |
| **Artifacts**            | Allows selection of specific artifacts (iFlows) to narrow down alert-triggered messages for targeted analysis.                                                                                         |

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

#### **Messages Grid**

The **Messages** section displays all runtime instances that triggered the configured alert. Each row represents a failed execution that met the alert condition.

#### **Alert Detail Panel (Right Side)**

When a message row is selected, detailed information appears on the right panel:

**Status Tab**

* Displays failure message.
* Shows error details from CPI runtime.
* Provides technical error information (e.g., HTTP exceptions, adapter errors).

**AI Coach Failure Analysis (If Enabled)**

* Provides intelligent insights into potential root causes.
* Assists in faster troubleshooting.

**Alert Lifecycle**

1. A failure occurs in the configured artifact.
2. ReleaseOwl detects the failure.
3. Email notification is sent (based on configuration).
4. An alert entry is created with status **Open**.
5. After corrective action, the alert can be marked as **Resolved**.

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1699).png" alt=""><figcaption></figcaption></figure>
