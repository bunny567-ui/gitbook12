# Credential Management

The **Credential Manager** allows administrators to securely store and manage credentials used by ReleaseOwl to connect with third-party applications and services. These credentials can be referenced by ReleaseOwl projects and pipelines to authenticate and interact with external systems without requiring users to manually provide authentication details each time.

ReleaseOwl supports integration with various external systems, including artifact repositories, cloud storage platforms, source code repositories, and other third-party services. After a credential is registered, it can be used by authorized projects and release pipelines based on its configured scope.

### Accessing the Credential Manager

1. Switch to the **Administration** view.
2. From the left navigation pane, click **Credential Manager**.

The **Credential Manager** page displays all registered credentials that are available based on your access permissions.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### **Credential Types**

Use the **Credential Types** filter to view credentials of a specific type. You can select one or more credential types to display the corresponding registered credentials.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* **Scope** – Credentials are categorized based on visibility:
  * **Global**: Visible to all users. Credentials created under this scope cannot be deleted by other users.
  * **Private**: Visible only to the user who created them. These credentials remain hidden from other users.
* **Search Bar** – Use this to quickly search for credentials by name.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Registering a New Credential**:

To register a new credential:

1. Navigate to **Administration** > **Credential Manager**.
2. Click **Register Credential**.
3. Select the appropriate **Credential Type**.
4. Enter the required credential details.
5. Select the appropriate **Scope** (**Global** or **Private**).
6. Click **Save** to register the credential.

Once the credential is successfully registered, it becomes available for use in ReleaseOwl projects and release pipelines according to its configured scope.

<figure><img src="../../../.gitbook/assets/image (2032).png" alt=""><figcaption></figcaption></figure>

**Editing a Credential**

You can modify an existing credential if its configuration or authentication details change.

To edit a credential:

1. Navigate to **Administration** > **Credential Manager**.
2. Select the credential you want to edit.
3. Update the required information.
4. Click **Save** to apply the changes.

The credential details page also displays audit information, including:

* **Created By** – The user who created the credential.
* **Created On** – The date and time the credential was created.
* **Last Modified By** – The user who most recently updated the credential.
* **Last Modified On** – The date and time of the latest modification.

This audit information helps administrators track changes and maintain accountability for credential management.

<figure><img src="../../../.gitbook/assets/image (27) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Delete**

* You can delete any credential by clicking the delete icon seen against that credential.

<figure><img src="../../../.gitbook/assets/image (1581).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note: Edit** and **Delete** options are available only for the users with appropriate user roles.
{% endhint %}

