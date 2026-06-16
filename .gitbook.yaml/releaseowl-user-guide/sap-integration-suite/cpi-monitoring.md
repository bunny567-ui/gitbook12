# CPI Monitoring

**CPI Monitoring** in ReleaseOwl enables users to track and manage integration artifacts such as **iFlows, APIs, and messages** from the SAP Integration Suite. It provides visibility into message processing, errors, and performance to ensure integrations run smoothly.

Using this feature, users can:

* Monitor message processing status
* Analyse logs
* Identify failed or retried messages
* Troubleshoot integration issues in real time

#### **SAP CPI Role Requirement**

To read monitoring data in ReleaseOwl, the **“MonitoringDataRead”** role must be assigned in the **SAP Process Integration Runtime (API)** instance.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :**  Without this role, ReleaseOwl will not be able to fetch runtime logs or message processing details.
{% endhint %}

#### **CPI Environment Configuration in ReleaseOwl**

To enable monitoring:

1. Navigate to the **CPI Environment**.
2. Select the required environment.
3. Under **Advanced Settings**, enable the **Enable Monitoring** checkbox.

<figure><img src="../../.gitbook/assets/image (19) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### CPI Monitoring Configuration

The **CPI Monitoring Configuration** allows users to configure how monitoring data is fetched from the SAP CPI tenant and displayed in ReleaseOwl.

To view the monitoring configuration:

1. Switch to **Project View**.
2. Navigate to **Monitoring**.
3. Select **CPI Monitoring**.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### CPI Monitoring Screen

The CPI Monitoring screen provides multiple filters to refine runtime log results:

* **Time** –  The **Time** filter allows users to define the monitoring window for message retrieval.
* **Status** – The **Status** filter allows users to view messages based on their execution outcome.
* **Type** – The **Type** filter defines the artifact category.
* **Package** – The **Package** filter enables users to select a specific CPI package.
* **Artifacts** – The **Artifacts** filter allows users to select one or more specific integration flows (iFlows).

<figure><img src="../../.gitbook/assets/image (1703).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :** Monitoring data is displayed only for projects linked to a configured CPI environment.
{% endhint %}

#### **Understanding the Monitoring Grid**

The monitoring table displays the following details:

* **Artifact Name** – This column displays the name of the CPI artifact (typically an iFlow) that processed the message.
* **Message ID** – The Message ID is a unique technical identifier assigned to each message execution in CPI.
* **Type** –  This column indicates the artifact type.
* **Started On** – This column shows the exact date and time when the message processing began.
* **Status** – The Status column indicates the current processing state of the message.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* **Configuration** -  Click **Configuration** to view or modify the **CPI Monitoring configuration settings**.&#x20;
* These settings control how monitoring data is fetched from the **SAP CPI tenant** into **ReleaseOwl**.
*   Through this configuration, users can define which messages should be monitored, how many records should be retrieved, and how frequently the monitoring data should be updated.

    <figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

The following parameters are available in the configuration:

**Status**\
Specifies the message statuses for which monitoring data will be fetched from the SAP CPI tenant to ReleaseOwl. Only messages with the selected statuses (such as **Failed, Escalated, Retry**, etc.) will be retrieved and displayed in the monitoring dashboard.

**Messages Count**\
Defines the maximum number of monitoring records that will be retrieved during each execution. This helps control the volume of monitoring data fetched from the CPI tenant.

**Time Period**\
This option is used during the **initial execution** to fetch monitoring data starting from the specified **date and time**. It ensures that ReleaseOwl retrieves historical monitoring records from the defined starting point.

**Real Time Monitor**\
When enabled, ReleaseOwl automatically creates a **scheduled job** to periodically fetch monitoring data from the SAP CPI tenant. This allows users to monitor integration messages continuously without manual intervention.

**Schedule Interval (Minutes)**\
Specifies the time interval, in minutes, between each scheduled monitoring data fetch when **Real Time Monitor** is enabled.

**Example:**\
If **Real Time Monitor** is enabled and the **Schedule Interval** is set to **10 minutes**, ReleaseOwl will automatically retrieve monitoring data from the SAP CPI tenant **every 10 minutes** and update the monitoring dashboard accordingly

<figure><img src="../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Check Messages** -  Click **Check Messages** to manually fetch monitoring data from the CPI tenant. When this option is used, ReleaseOwl retrieves monitoring records from the **last execution time until the current time**. This option is typically used when **Real-Time Monitoring is disabled**.

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Viewing Detailed Execution Information**

1. Click on an **Artifact Name** from the monitoring grid.
2. The right-side panel displays detailed information under the following tabs:

**Status**

* Displays execution result.
* Shows error message if processing failed.

**Properties:** Displays runtime metadata and technical properties.

**Artifact Details:** Shows additional artifact-level information related to the execution.

**Refreshing Monitoring Data :** Click the **Refresh** icon to fetch the latest message processing records.

<figure><img src="../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### &#x20;**Alerts**

The **Alerts** feature allows users to configure notifications based on specific **CPI environments** and **monitoring statuses**. When a configured alert condition is triggered, **ReleaseOwl** sends notification emails to the specified users so that integration issues can be addressed quickly. Alerts help teams proactively monitor **integration failures, escalations, or retries**, enabling them to respond promptly and maintain stable integrations.

1. Log in to the **ReleaseOwl Dashboard**.
2. Navigate to: **Monitoring → Alerts**
3. Click on the " **Create Alert Configuration.**"

<figure><img src="../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Fill in the following details:&#x20;

| Field                                             | Description                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Name**                                          | Enter a unique and identifiable name that represents the purpose and environment of the alert configuration.                                                                                                                                                                                                                                                                                           |
| **Description**                                   | Enter a description that explains the purpose of the alert. For example, notifications for failed iFlow executions.                                                                                                                                                                                                                                                                                    |
| **Environment**                                   | Select the CPI environment for which the alert should be triggered.                                                                                                                                                                                                                                                                                                                                    |
| **Active**                                        | Enable the **Active** checkbox to activate the alert configuration. When enabled, notifications are sent whenever the configured alert conditions are triggered. When disabled, notifications are not sent.                                                                                                                                                                                            |
| **Similar Error Notification Interval (Minutes)** | Prevents duplicate notifications for the same error from being sent repeatedly. If the same artifact generates multiple identical errors within the specified interval, ReleaseOwl sends only one notification during that period. For example, if the interval is set to 10 minutes and the same artifact generates 10 identical errors, only one notification email is sent within those 10 minutes. |
| **Notification Email(s)**                         | Specify the email addresses that should receive alert notifications. Multiple email addresses can be added and must be separated by a comma (,).                                                                                                                                                                                                                                                       |
| **Artifacts**                                     | Configure alerts for specific Packages or Artifacts. This allows users to monitor specific integration packages, track failures for particular integration artifacts, and receive targeted notifications only for selected integrations.                                                                                                                                                               |

<figure><img src="../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* After clicking the **Save** button in the Alert Configuration screen, the system redirects to the **CPI Alerts Monitoring** page.&#x20;
* This screen displays real-time alert-triggered message details based on the configured alert rules.

<figure><img src="../../.gitbook/assets/image (1900).png" alt=""><figcaption></figcaption></figure>

#### **Top-Level Filters**

The following filters are available in the CPI Alerts screen to refine and analyze alert-triggered messages:

| **Filter Name**          | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Environment**          | Displays the selected CPI environment. Only alerts triggered within the selected environment are shown.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Alert Configurations** | Allows selection of a specific alert configuration . The grid displays only the messages that triggered this selected alert rule.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Group By**             | <p>The <strong>Group By</strong> option in the filter section allows users to control how <strong>CPI Monitoring Alerts</strong> are displayed in ReleaseOwl.</p><p>Two options are available:</p><p><strong>None</strong><br>When <strong>None</strong> is selected:</p><ul><li>All CPI Monitoring Alerts are displayed <strong>individually</strong>.</li><li>Each alert appears as a <strong>separate record</strong>.</li><li>This view shows the <strong>complete list of alerts without grouping</strong>.</li></ul><p><strong>Error</strong><br>When <strong>Error</strong> is selected:</p><ul><li>Alerts are <strong>grouped based on the error type</strong>.</li><li>Identical errors are grouped together.</li><li>The system displays a <strong>count</strong> showing how many times that error has occurred.</li></ul> |
| **Time**                 | Filters alert records based on the selected time range. Useful for reviewing alerts within a specific monitoring window.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Alert Status**         | Filters alerts by their current lifecycle status: • **Open** – Alert is active and unresolved. • **Resolved** – Alert has been marked as resolved. • **All** – Displays both Open and Resolved alerts.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Type**                 | Filters alerts based on the artifact type.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Package**              | Filters alerts based on the CPI package to which the artifact belongs.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Artifacts**            | Allows selection of specific artifacts (iFlows) to narrow down alert-triggered messages for targeted analysis.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

<figure><img src="../../.gitbook/assets/image (1901).png" alt=""><figcaption></figcaption></figure>

#### **Messages Grid**

The **Messages** section displays all runtime instances that triggered the configured alert. Each row represents a failed execution that met the alert condition.

**Alert Detail Panel (Right Side)**

When a message row is selected, detailed information appears on the right panel:

**Status Tab**

* Displays failure message.
* Shows error details from CPI runtime.
* Provides technical error information (e.g., HTTP exceptions, adapter errors).

**Generate AI Recommendation**

The **Generate AI Recommendation** feature helps users identify the possible cause of an **artifact failure** using AI-generated insights. When an artifact fails in **CPI Monitoring**, users can click **Generate AI Recommendation** to analyze the failure details.

Once triggered:

* The system analyzes the **error information**.
* An **AI-based recommendation** is generated.
* The recommendation helps determine the **possible cause of the failure** and assists users in troubleshooting the issue more efficiently.

<figure><img src="../../.gitbook/assets/image (1902).png" alt=""><figcaption></figcaption></figure>

#### Mark as Resolved

The **Mark as Resolved** feature allows users to update the status of an alert once the underlying issue has been fixed. This helps maintain accurate alert tracking and provides visibility into issues that have been successfully addressed.

**Resolving an Alert**

1. Select the alert that has been addressed.
2. Click **Mark as Resolved**.
3. The alert status is updated from **Open** to **Resolved**, indicating that the issue has been successfully resolved.

**Resolve All Similar Errors**

The **Resolve All Similar Errors** feature enables users to resolve multiple alerts that were triggered by the same artifact and error pattern. This helps reduce manual effort and simplifies alert management when the same issue generates multiple alerts.

**Resolving All Similar Errors**

1. Select the alert to be resolved.
2. Enable the **Resolve All Similar Errors** checkbox.
3. Click **Resolved**.
4. The system automatically resolves all alerts associated with the same artifact and matching error pattern.

<figure><img src="../../.gitbook/assets/image (1903).png" alt=""><figcaption></figcaption></figure>

#### Raise Defect

The **Raise Defect** feature enables users to create and manage defects directly from CPI Monitoring alerts whenever issues are identified in integration flows or message processing.

**Creating a Defect from an Alert**

1. Select the alert for which a defect needs to be created.
2. Click **Raise Defect**.
3. A pop-up window is displayed, allowing you to select the required ALM integration for defect management.
4. Select the ALM platform where the defect should be created.

<figure><img src="../../.gitbook/assets/image (1904).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note** : Currently, **SAP Cloud ALM** is supported as the integrated ALM platform. Users can optionally set the selected ALM integration as the default integration for future defect creation activities. Once configured, the application automatically redirects users to SAP Cloud ALM whenever a defect is raised.
{% endhint %}

**Access the Created Defect**

1. Return to the CPI Alert record.
2. Navigate to the **Status** section.
3. Locate the **Defect ID** associated with the alert.
4. Click the **Defect ID** hyperlink to open the corresponding defect record in SAP Cloud ALM.
5. View, track, update, and manage the defect throughout its lifecycle.

<figure><img src="../../.gitbook/assets/image (1906).png" alt=""><figcaption></figcaption></figure>

#### **Code Change**

The **Code Change** feature allows users to compare the previous and current versions of an artifact to understand the changes that may have contributed to an issue. This helps users analyze modifications, perform impact assessments, and support troubleshooting activities.

**Viewing Code Changes**

1. Select an alert from the **Messages** grid.
2. Click the **Code Change** button.
3. The system displays the previous and current versions of the selected artifact side by side.
4. Review and compare the changes between the two versions.

<figure><img src="../../.gitbook/assets/image (1907).png" alt=""><figcaption></figcaption></figure>

#### **Viewing Alert Data**&#x20;

Once an alert is triggered, the corresponding alert information will be available in **ReleaseOwl** for monitoring and analysis. At the same time, notification emails will be sent to the configured users to inform them about the alert. This allows users to quickly review the issue and take the necessary action.

<figure><img src="../../.gitbook/assets/unknown (3).png" alt=""><figcaption></figcaption></figure>

