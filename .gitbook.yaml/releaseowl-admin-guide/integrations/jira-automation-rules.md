# Jira Automation Rules

ReleaseOwl supports the automatic synchronization of user story changes made in Jira through automation rules. These rules must be configured in Jira to update changes made to issues and sprints in ReleaseOwl.

This guide outlines how to create an automation rule in Jira that triggers specific actions based on predefined conditions. The **ReleaseOwl API** should be invoked in the **"Send Web Request"** action to synchronize issue or sprint changes from Jira to ReleaseOwl.

### **Issue or Sprint Changes Synchronization**

#### **Creating an Automation Rule for Issue or Sprint Synchronization**

1. Navigate to **Project Settings**.
2. Click on **Automation**.
3. **Click the "Create Rule" button** to begin configuring a new automation rule.

<figure><img src="../../.gitbook/assets/image (828).png" alt=""><figcaption></figcaption></figure>

### **1. Define the Rule Trigger**

A **trigger** determines when the rule should execute. To add multiple triggers, select **Multiple Issue Events** in the **"Add a Trigger"** section and choose one or more relevant triggers.

<figure><img src="../../.gitbook/assets/image (829).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
#### **Possible Triggers:**

* **Issue Created** – Triggers when a new issue is created.
* **Issue Assigned** – Triggers when an issue is assigned to a user.
* **Issue Transitioned** – Triggers when an issue moves from one status to another.
* **Issue Updated** – Triggers when an issue is updated.
{% endhint %}

### **2. Add Conditions**

**Conditions** refine rule execution by restricting it to specific scenarios. These conditions must align with the criteria defined in the **ALM Integration in ReleaseOwl**; otherwise, unwanted user stories from Jira may appear in ReleaseOwl.

* Click **"+ Add Component"** and select **"IF: Add a Condition."**

<figure><img src="../../.gitbook/assets/image (830).png" alt=""><figcaption></figcaption></figure>

#### **Choose an Appropriate Condition Type:**

* **Issue Fields Condition** – Evaluates a specific field (e.g., status, priority) against predefined criteria.
* **JQL Condition** – Uses **Jira Query Language (JQL)** for advanced issue filtering.

<figure><img src="../../.gitbook/assets/image (831).png" alt=""><figcaption></figcaption></figure>

### **3. Define an Action**

Once a condition is met, configure an **action**. The **ReleaseOwl API** should be invoked in the action (**"Send Web Request"**) for synchronizing issue or sprint changes from Jira to ReleaseOwl.

#### **Steps to Add an Action:**

1. Click **"+ Add Component"** and select **"THEN: Add an Action."**

<figure><img src="../../.gitbook/assets/image (832).png" alt=""><figcaption></figcaption></figure>

2. In the **"Add an Action"** search bar, select **"Send Web Request."**
3. **Web Request URL** – Copy the **Web Request URL** generated in the **Web Request URL for Automation Rule.**

<figure><img src="../../.gitbook/assets/image (1082).png" alt=""><figcaption></figcaption></figure>

4. **HTTP Method** – Set this to **POST**.
5. **Web Request Body** – Select **Custom Data**.

#### **Custom Data for Synchronization:**

**For Issue Sync:**

```json
{
  "webhookEvent": "automation_rule",
  "eventName": "issue_rule",
  "issueId": "{{issue.key}}"
}
```

**For Sprint Sync:**

```json
{
  "webhookEvent": "automation_rule",
  "eventName": "sprint_rule",
  "sprintId": "{{sprint.id}}"
}
```

<figure><img src="../../.gitbook/assets/image (833).png" alt=""><figcaption></figcaption></figure>

### **4. Activate and Test the Rule**

1. Click the **"Turn on Rule"** button.
2. Enter details such as **Rule Name** and who can edit the rule.
3. Click **"Turn on Rule"** to perform tests and validate the rule execution.

<figure><img src="../../.gitbook/assets/image (834).png" alt=""><figcaption></figcaption></figure>

For more information, refer to [**Create and edit Jira automation rules | Cloud Automation Cloud | Atlassian Support**.](https://support.atlassian.com/cloud-automation/docs/create-and-edit-jira-automation-rules/)
