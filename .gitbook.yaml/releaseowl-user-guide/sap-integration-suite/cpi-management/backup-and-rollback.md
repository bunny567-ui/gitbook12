# Backup & Rollback

The **Enable Rollback** option is one of the key **Deployment Actions** that can be configured during the deployment process. When enabled, this option creates a **backup of the current deployment version**, allowing you to **rollback changes** in case of deployment failures or post-deployment issues.

### **Key Points:**

* Rollback is supported for **CPI artifacts** deployed both to **design time** and **runtime**.
* To use rollback during a release pipeline, you must **enable rollback while creating the pipeline**.
* During pipeline execution, you can initiate rollback by clicking the **Rollback** option in the deployment screen.
* Detailed deployment information, including rollback status, is available in the associated **deployment task**.
* Rollback logs in the **Pipeline Activity** section appear only when a rollback is triggered, reducing clutter in the pipeline history.

### **How to Enable Rollback:**

1. While adding a **Deployment Task**, you will see an option for **Enable Rollback**.
2. **Select the checkbox** next to this option.
3. Click **Save** to confirm the changes.<br>

<figure><img src="../../../.gitbook/assets/image (1068).png" alt=""><figcaption></figcaption></figure>

4. You can view the Release Pipeline execution status from User Stories screen by navigating to the Pipeline Activity as shown below:<br>

<figure><img src="../../../.gitbook/assets/image (1071).png" alt=""><figcaption></figcaption></figure>

5. Click on the **Pipeline Activity** option. You can find the Rollback option under **Deployment section**.&#x20;
6. At any point of time i.e., during or after the deployment done by the execution of the Release Pipeline, you can rollback to previous version by clicking the Rollback option available.&#x20;

<figure><img src="../../../.gitbook/assets/image (1073).png" alt=""><figcaption></figcaption></figure>

7. To rollback to the previous version, click on **Rollback** and in the confirmation pop-up that appears, click **Yes**. Rollback process starts.

<figure><img src="../../../.gitbook/assets/image (1072).png" alt=""><figcaption></figcaption></figure>

### **Rollback Logs**

* **Rollback Logs** are generated for **CPI artifacts** deployed to both **design time** and **runtime**.
* To rollback a build, click **Rollback** on the **Pipeline Activity status page**.
* Once rollback is triggered, the **rollback status and details** will be visible in the **deployment logs**, providing transparency into the rollback process and outcomes.

<figure><img src="../../../.gitbook/assets/image (1616).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note :** Rollback logs in the Pipeline Activity section are now dynamically displayed only when a rollback is actually triggered.
{% endhint %}
