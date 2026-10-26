# Analytics Cloud Management

This section describes the process of configuring and managing **SAP Analytics Cloud (SAC)** environments in **ReleaseOwl**.

### **SAC Management**&#x20;

* Navigate to SAC Management in the Build section and click **Add Packages** to add packages from your SAC tenant to the project.

<figure><img src="../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

* **Remove Artifacts** – removes the selected packages from the project.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* **Sync History** - shows a log of every add, update and remove.&#x20;

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Import Settings**

* Click the **Actions** button and select **Import Settings** to view package details.

<div><figure><img src="../../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure></div>

*   **Choose an Overwrite Preference**

    Under **Overwrite Preferences**, choose what happens when the package contains objects with the same name as objects already in the target system. New objects are always imported. Select one option:

    * **Don't overwrite objects or data** – leaves existing content unchanged.
    * **Overwrite data only** – overwrites the data of existing objects but doesn't change the structure of your models.
    * **Overwrite objects and data** – imports all selected content and lets existing objects be overwritten.

    <figure><img src="../../.gitbook/assets/image (2347).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** On the environment side, you can set the import settings for each environment separately.
{% endhint %}

