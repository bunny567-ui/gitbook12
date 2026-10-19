# Analytics Cloud Management

This section describes the process of configuring and managing **SAP Analytics Cloud (SAC)** environments in **ReleaseOwl**.

### **SAC Management**&#x20;

* Navigate to SAC Management in the Build section and click **Add Packages** to add packages from your SAC tenant to the project.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

* **Remove Artifacts** – removes the selected packages from the project.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

* **Sync History** - shows a log of every add, update and remove.&#x20;

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

**Import Settings**

* Click the **Actions** button and select **Import Settings** to view package details.

<div><figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure></div>

*   **Choose an Overwrite Preference**

    Under **Overwrite Preferences**, choose what happens when the package contains objects with the same name as objects already in the target system. New objects are always imported. Select one option:

    * **Don't overwrite objects or data** – leaves existing content unchanged.
    * **Overwrite data only** – overwrites the data of existing objects but doesn't change the structure of your models.
    * **Overwrite objects and data** – imports all selected content and lets existing objects be overwritten.

    <figure><img src="../../.gitbook/assets/image (2347).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** On the environment side, you can set the import settings for each environment separately.
{% endhint %}

**Release  Pipelines**

* Go to the Release Pipelines and click on the **Create New Release Pipeline.**

<figure><img src="../../.gitbook/assets/image (1376).png" alt=""><figcaption></figcaption></figure>

* Enter a  **Release** **Pipeline Name**.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (32).png" alt=""><figcaption></figcaption></figure>

* Click **Add Stage**.

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (18).png" alt=""><figcaption></figcaption></figure>

* Enter the stage name say for e.g., UAT or QA where the deployment has to be carried out and click OK.

<figure><img src="../../.gitbook/assets/image (382).png" alt=""><figcaption></figcaption></figure>

* **Tasks:** Click **Add** to enter any tasks that are to be performed

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)   (3).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** To remove any stage, click Remove stage button.
{% endhint %}

* Different tasks that can be added are as follows:

<figure><img src="../../.gitbook/assets/image (14) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Add a Deployment Stage**

* Click on **Add** under the **Tasks** section.
* Select **SAC - Deployment** from the available task types.

**Configure Task Details**

* In the **Task Details** panel, configure the following fields:
  * **Name** (required): Enter a name for the deployment task.
  * **Description**: Enter a description of the task.
  * **Select SAC Environment** (required): Select the target environment. For an SDS deployment task, select the target SDS environment.
* Scroll down to **Overwrite Preferences** and select how existing objects and data should be handled during import. New objects are always imported.
  * **Don't overwrite objects or data**: Preserves existing objects and data.
  * **Overwrite data only**: Overwrites existing data without changing the structure of objects.
  * **Overwrite objects and data**: Allows existing objects and data to be overwritten.
* **Set Include Data:** Tick **Include Data** to import the data along with the objects. Clear it to import the objects only
* Save the pipeline to apply the configuration.

<figure><img src="../../.gitbook/assets/image (2348).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
&#x20;**Note:** The settings configured in the deployment task serve as the default import settings for the selected environment.
{% endhint %}

**Advance Settings**

* **Prevent same approver across tasks:**
  * **Behaviour:** once a user approves or rejects one approval task in a run, they can’t act on another approval task in that run.
  * **Details:** it is off by default, and adding an assignee isn’t counted.
  * **Message:** the denial message users see is quoted.
* **Notification Email(s):** type an address, press Enter to add it, then click **Save**.

<figure><img src="../../.gitbook/assets/image (2349).png" alt=""><figcaption></figcaption></figure>
