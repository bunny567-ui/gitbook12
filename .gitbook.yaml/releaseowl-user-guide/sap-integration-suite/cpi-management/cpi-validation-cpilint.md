# CPI Validation - CPILint

**CPILint** is a command-line tool used to validate SAP CPI IFlows against a predefined set of rules. These rulesets can include naming conventions, preferred mapping types, scripting technologies, and other best practices. When executed, CPILint analyzes the IFlows and reports any deviations from the defined ruleset, helping ensure consistency, maintainability, and high quality across all integration artifacts.

{% hint style="info" %}
**Note : Further information on CPILint can be found from the below mentioned links:**\
[https://blogs.sap.com/2019/02/01/meet-cpilint/](https://blogs.sap.com/2019/02/01/meet-cpilint/)\
[https://github.com/mwittrock/cpilint/wiki](https://github.com/mwittrock/cpilint/wiki)
{% endhint %}

{% hint style="info" %}
Note: **License terms of CPI Lint tool can be found here:**\
[https://github.com/mwittrock/cpilint?tab=MIT-1-ov-file#readme](https://github.com/mwittrock/cpilint?tab=MIT-1-ov-file#readme)
{% endhint %}



#### **Prerequisites**

In the **General** tab of Project Settings, scroll down to the **CPI Settings** section. If the **"Both"** option is selected, the system generates a **Validation Report** that includes results from both **CPI Lint** and **CPI Design Guidelines**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Validate - CPI**

1. Go to a required package in the User Stories screen under Change Management Section and click **Actions**. Click **Validate** to start the validation process.

<figure><img src="../../../.gitbook/assets/image (1671).png" alt=""><figcaption></figcaption></figure>

2. A pop-up dialog appears prompting you to select the appropriate **SAP CPI target environment** from the list.
3. After selecting the target environment, click the **Validate** button to initiate the validation process.

<figure><img src="../../../.gitbook/assets/image (1673).png" alt=""><figcaption></figcaption></figure>

### **Validation Report**

Validation report is visible only after the validation process is complete.\
\
**To view the validation report:**

1\. Go to a required package and click **Actions**. Click **Validation Report**.

2\. The validation report is displayed below.

<figure><img src="../../../.gitbook/assets/image (1675).png" alt=""><figcaption></figcaption></figure>

3\. Expand the artifact to view the details.

<figure><img src="../../../.gitbook/assets/image (1676).png" alt=""><figcaption></figcaption></figure>

#### CPI Downgrade Check

This feature ensures that the correct user story is reused during a downgrade operation when a target version already exists.

#### How It Works

1. During a downgrade, the system checks whether the **target version** is already associated with a user story.
2. If a user story already exists for the target version, the system displays that **existing user story**.
3. After the downgrade validation is successful, the system **reuses the same artifact-assigned user story**.
4. The reused user story is displayed in the **Target User Story** column.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**CPI Downgrade Check – Validation Outcomes**

This check ensures version consistency between the source and target environments before deployment. Below are the possible validation outcomes:

**✅ Success – Equal or Lower Version**

If the **target version is lower than or equal to** the source version, the validation **passes**.

* **Example Message:** `"The artifact '' target environment version '1.2' is lower than the source environment version '1.3'."`

**✅ Success – Artifact Not Present in Target**

If the artifact is **not present** in the target environment (e.g., initial deployment), the validation **passes**.

* **Example Message:** `"The artifact '' is not present in the target environment ''."`

**❌ Failure – Target Has Higher Version**

If the **target version is higher** than the source version, the validation **fails**.

* **Example Message:** `"The artifact '' target environment version '1.4' is higher than the source environment version '1.3'."`

**⚠️ Warning – Force Deploy Enabled**

If **Force Deploy** is enabled, the deployment proceeds, but a **warning** is shown.

* **Example Message:** `"The artifact '' target environment version '1.4' is higher than the source environment version '1.3' but force deploy is enabled."`

**⚠️ Warning – Already Deployed via ReleaseOwl**

If the artifact was **already deployed via ReleaseOwl** and an older version is redeployed, the downgrade is considered intentional. A **warning** is shown and the artifact is **not redeployed**.

* **Example Scenario:** Version 1.1 was deployed, then version 1.2. Attempting to redeploy 1.1 results in:
* **Example Message:** `"The artifact '' target environment version '1.4' is higher than the source environment version '1.3' but artifact is already deployed via ReleaseOwl."`

### CPI Governance

The **CPI Rules** section in **ReleaseOwl** provides a centralized configuration interface to define and enforce governance policies and best practices for **SAP Cloud Platform Integration (CPI)** artifacts. These rules help ensure that integration artifacts comply with established **security**, **coding**, and **operational** standards across projects.

#### Design Guidelines Report

Under CPI governance, ReleaseOwl includes **CPI Design Guidelines** that are automatically validated as part of the **validation reports**. These guidelines consist of built-in rules and industry best practices designed to help developers build **high-quality**, **standardized**, and **maintainable** integration flows.

* During the validation of **CPI Design Guidelines**, ReleaseOwl evaluates integration artifacts against built-in rules and best practices. These guidelines help developers create **high-quality**, **standardized**, and **maintainable** integration flows.
* The validation generates compliance reports (**Compliant / Non-Compliant**) with defined **severity levels** (High, Medium, Low). The reports are accessible directly within the **Integration Flow editor** and provide **actionable insights**, including navigation to the affected steps.
* Additionally, the reports reference recommended integration packages such as the **CPI Cloud Exemplar** to help developers learn and apply proven patterns for **performance, security, and efficiency**, ensuring consistent integration quality across projects.

<figure><img src="../../../.gitbook/assets/image (1677).png" alt=""><figcaption></figcaption></figure>
