# Multiverse

ReleaseOwl's Multiverse feature allows users to deploy a combination of artifacts, including SAP Transports, MTAR packages, CPI Artifacts (IFlows), and SAC Artifacts, all in a single deployment request

### **Prerequisites**

Before using **Multiverse**, ensure:

* Target systems (**SAP systems, BTP, CPI, SAC**) are configured in ReleaseOwl.
* Required artifacts are built and available in their respective repositories.

### **Adding Environment Deployment Details in Release Pipelines**

#### **Step 1: Create Release Pipeline**

1. Navigate to **Release Pipelines**.
2. Click on **Create New Release Pipeline**.

<figure><img src="../.gitbook/assets/image (33) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Under **Add Stages**, enter the appropriate deployment stages (e.g., **dep**, **int**, **prod**, etc.).

<figure><img src="../.gitbook/assets/image (34) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Click **+ Add** under the **Tasks** section to add tasks like **approvals**, **callouts**, etc.

<figure><img src="../.gitbook/assets/image (35) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Step 2: Add Environment Deployment Details**

1. In the **Tasks** section, after selecting the necessary task, click the **+ Add** icon to include environment-specific deployment details.

<figure><img src="../.gitbook/assets/image (36) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. This will open a popup where you can fill in the deployment details for each environment.

<figure><img src="../.gitbook/assets/image (37) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. In the popup:

* **Select Environment(s):** Choose from the following:
  * SAP On-Premise
  * SAP BTP (MTAR)
  * SAP CPI
  * SAP Analytics Cloud
  * SAP Datasphere
  * SAP API

<figure><img src="../.gitbook/assets/image (38) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Fill in all **required fields** as per the selected environment.
5. Click **Add** to save and include the deployment details.

{% hint style="info" %}
**Note:** You can add multiple environment deployment details for a single pipeline to handle complex multi-environment deployment scenarios effectively.
{% endhint %}

### **Track and Deploy All User Stories**

In the **User Story** section, you can manage, track, and add details for specific deployment stories. Additionally, you can promote all associated artifact combinations in a **single action.**

<figure><img src="../.gitbook/assets/image (39) (1).png" alt=""><figcaption></figcaption></figure>

