# Retrofit & Conflict Resolution

The retrofit process in ReleaseOwl ensures that changes made in the maintenance landscape are synchronized with the implementation landscape while preventing downgrades, overwrites, and conflicts. It supports both automated and manual retrofitting mechanisms to handle various object types and development workflows.

### Retrofit Approaches

Retrofitting in ReleaseOwl can be performed in two ways:

#### &#x20;Automated Retrofit via Pipelines

ReleaseOwl offers an **automated retrofit task** as part of the release pipeline.\
This ensures that whenever changes are moved to **Quality (QA)** or **Production (PRD)**, they are automatically retrofitted back to the **implementation landscape**.

The retrofit task:

* Checks for conflicts
* Ensures that only **non-conflicting** changes are moved forward automatically

#### Manual Retrofit via the Retrofit Screen

In cases where a **transport request (TR)** is modified or delayed, it will appear on the **Retrofit Screen** in ReleaseOwl.

Users can manually trigger the retrofit process from this screen, which will:

* Dynamically create a new transport request
* Transfer changes from the **maintenance landscape** to the **implementation landscape**

This manual method gives users control over which TRs to retrofit and when, especially useful in cases requiring conflict resolution or selective movement.

### **Enabling and Performing Transport Retrofit in ReleaseOwl**

You can enable the **retrofit** option in the **Transport Domain Controller** screen.

{% hint style="info" %}
**Note:** In **ReleaseOwl**, transport retrofit can be performed for **Customizing** and **Workbench** transports that have already been released.
{% endhint %}

### **Steps to Enable Retrofit:**

1. Navigate to **Transport Domain Controller** from the **Administration** view.
2. If the Transport Domain Controller is not yet registered, click **Register Transport Domain Controller**. Otherwise, you can edit the existing configuration.
3. Enter the required details.

<figure><img src="../../.gitbook/assets/image (245).png" alt=""><figcaption></figcaption></figure>

4. Check the option **Enable Retrofit (Source)** to enable retrofit.
5. Click **Save** to apply the changes.
6. The following screen is displayed upon registering the Transport Domain Controller.

### **Performing Transport Retrofit**

1. Navigate to **Transport Retrofit** under the **Build** section.
2. Select the transport you want to retrofit and click **Retrofit**.

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. After completing the retrofit process, you can view details of the retrofit objects by clicking the arrow button. This will display information such as the program ID, object type, retrofit conflict status, and more.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:**

* If the **Retrofit is successful**, the **Retrofit Status** will be **Completed**.
* If there is a **conflict**, the **Retrofit Status** will be **Retrofit Conflict**.
{% endhint %}

**Steps to Resolve Conflicts:**

1. Click on the transport request with the **Retrofit Conflict** status.
2. View the object that has a conflict.

<figure><img src="../../.gitbook/assets/image (54) (1).png" alt=""><figcaption></figcaption></figure>

3. Click the **error icon** against the **Retrofit Conflict Status** to view error details.

<figure><img src="../../.gitbook/assets/image (254).png" alt=""><figcaption></figcaption></figure>

4. Rectify the error and click **Resolve** to resolve the conflict.

<figure><img src="../../.gitbook/assets/image (253).png" alt=""><figcaption></figcaption></figure>

5. Click **OK**—the **Retrofit Conflict Status** will change successfully.

<figure><img src="../../.gitbook/assets/image (256).png" alt=""><figcaption></figcaption></figure>

6. Click **Continue Retrofit** to proceed.

<figure><img src="../../.gitbook/assets/image (255).png" alt=""><figcaption></figcaption></figure>

7. The **retrofit process completes successfully**.

<figure><img src="../../.gitbook/assets/image (257).png" alt=""><figcaption></figcaption></figure>



