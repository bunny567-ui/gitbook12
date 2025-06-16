# Transport Promotion and Pipeline Activity

### Transport Promotion

In **ReleaseOwl**, _transport promotion_ refers to the controlled and automated movement of **Transport Requests (TRs)** across various stages of the **release pipeline**, typically from **DEV → QA → PROD**.

#### **Steps to Promote a Transport**

1. Click on the **action menu (⋯)** next to the transport.
2. Select the **Promote** option.
3. The transport will then be promoted to the next environment (e.g., from DEV to QA or QA to PROD), depending on its current stage in the pipeline.

{% hint style="info" %}
**Note:**  Before a transport can be promoted, it **must be assigned to a User Story**.

* The **User Story** must be linked to a **Release Pipeline**.
* If not properly assigned, you will receive a warning indicating the missing association, and the promotion will not proceed.
{% endhint %}

&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Pipeline Activity:**

In ReleaseOwl, the **Pipeline Activity** section provides a real-time, detailed overview of all actions executed during the deployment lifecycle, including validation tasks, approvals, and deployment tasks.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Refresh Button**

The **Refresh** button in the **Transport Management** section updates the **Pipeline Activity** screen with the most recent information.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**History Button**

The **History** button in the **Transport Management** section provides a detailed log of all actions performed on a **Transport Request** within the release pipeline.

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

When you click on the arrow button (**>**), you are taken to the **Pipeline Activity** screen.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (7) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
