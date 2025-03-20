# Retrofit & Conflict Resolution

### **Enabling and Performing Transport Retrofit in ReleaseOwl**

#### **Enabling Retrofit in Transport Domain Controller**

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
3. The **Transport Retrofit** process begins, and you can view details such as:

* **Retrofit Request**
* **Retrofit System ID**
* **Retrofit Client ID**
* **Retrofit By**
* **Retrofit On**
* **Retrofit Status**

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:**

* If the **Retrofit is successful**, the **Retrofit Status** will be **Completed**.
* If there is a **conflict**, the **Retrofit Status** will be **Retrofit Conflict**.
{% endhint %}

**Steps to Resolve Conflicts:**

1. Click on the transport request with the **Retrofit Conflict** status.
2. View the object that has a conflict.

<figure><img src="../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

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



