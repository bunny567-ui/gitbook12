# Cloud Environment Registration

**Environment Registration** allows you to onboard SAP S/4HANA Public Cloud environments into ReleaseOwl. These environments represent the actual system domains where deployments and validations will occur (e.g., Development, Test, Production).

### **Steps to Register an Environment:**

1. Navigate to the **Environment** section.
2. Select **S/4HANA Public Cloud Environment** and click **Register**.

<figure><img src="../../../.gitbook/assets/image (1533).png" alt=""><figcaption></figcaption></figure>

3. Enter the required details:

* **Name** : Provide a name of your choice.&#x20;
* **Credentials** : Select the credentials created in **Credential Management**.
* **Host URL** : Enter the tenant host URL.&#x20;
* **Client ID** : Enter the **Client ID** of the **S/4HANA Public Cloud Environment.**
* **PC System Type** : Select the type of S/4HANA Public Cloud system you are registering, such as development, customizing, test and Prod.&#x20;

<figure><img src="../../../.gitbook/assets/image (1554).png" alt=""><figcaption></figcaption></figure>

* **Environment Type** : Choose the desired environment type.

<figure><img src="../../../.gitbook/assets/image (1534).png" alt=""><figcaption></figcaption></figure>

#### **Assign Environment to a Project**

1. Go to the **Projects** section and select your project.
2. Enter necessary details and choose **Project Type** as **SAP Public Cloud**.

<figure><img src="../../../.gitbook/assets/image (1537).png" alt=""><figcaption></figcaption></figure>

3. Click **“Switch to Project”** for the project you just created.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. From the **Projects** dropdown (top-right corner), select **Project Settings → Environment**.

<figure><img src="../../../.gitbook/assets/image (1538).png" alt=""><figcaption></figcaption></figure>

5. Click **+Add** to add a new environment.

<figure><img src="../../../.gitbook/assets/image (1539).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1513).png" alt=""><figcaption></figcaption></figure>

6. On the subsequent screen, select the required environment from the Source list. Only artifacts with a defined source are synced to ReleaseOwl, and you can also add multiple source environments.
7. The environment is added to the corresponding project in ReleaseOwl.
8. Click on the **Users** tab. This tab lists all existing users associated with the project.
9. Click on the **edit (lock)** icon next to the user for whom you want to manage roles and permissions.&#x20;

<figure><img src="../../../.gitbook/assets/image (1516).png" alt=""><figcaption></figcaption></figure>

10. Scroll down to the Environments section.
11. Select the _**Deploy**_ checkbox for the relevant environment(s) to grant the user deployment access.

<figure><img src="../../../.gitbook/assets/image (1514).png" alt=""><figcaption></figcaption></figure>



#### **Synchronize Artifacts**

1. Switch to the **Project View**.
2. Click on **S/4HANA Public Cloud** in the **Build** section.
3. Click the **Synchronize** button. This retrieves all artifacts of type **Transport** and **Software Collection** from the S/4HANA Public Cloud into ReleaseOwl.

{% hint style="info" %}
**Note:** For **Transports**, the first **500 released transport requests** are synchronized. For **Software Collections**, the **latest exported version** is synchronized.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (1517).png" alt=""><figcaption></figcaption></figure>
