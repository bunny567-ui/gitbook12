# Jira On-Premise

### **Integrating Jira with ReleaseOwl**

If you work with external project management systems such as **Jira**, you can integrate them with **ReleaseOwl**. ReleaseOwl also supports **Jira On-Premise** access.

### **Granting Jira Access to Your Servers:**&#x20;

To enable integration and secure communication with Jira Cloud or Jira On-Premise environments, follow these steps:

1. Go to **Credential Manager** from the **Administration** menu.
2. Click **Register Credential**.
3. Select **Credential Type** and choose **Jira**.
4. Provide the following details:
   * **Credential Name**: Any identifiable name (e.g., JiraIntegration).
   * **Authentication Type**: Basic.
   * **Username**: Jira Technical User account.
   * **Password/API Token**: API token generated from Atlassian (Cloud) or Jira Admin (On-Premise).
   * **Jira URL**: Enter the Jira base URL (e.g., [https://yourcompany.atlassian.net](https://yourcompany.atlassian.net/)).
   * **Proxy Type**: Select **SAP Cloud Connector**.
   * **Proxy URL**: Provide the virtual URL via Cloud Connector (e.g., https:///proxy).
   * **SAP Cloud Credentials**: Select an existing **ServiceUserCredBtp** for proxy communication.
5. Save the credential.

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

### **Validation:**

* &#x20;**Test the integration** by verifying **user story sync** or checking **webhook status** in: **Jira → System → Webhooks**

{% hint style="info" %}
**Recommendations:**  ✅ Use a **dedicated Jira Technical User** with API access permissions.\
✅ **Rotate API tokens regularly** for security.
{% endhint %}
