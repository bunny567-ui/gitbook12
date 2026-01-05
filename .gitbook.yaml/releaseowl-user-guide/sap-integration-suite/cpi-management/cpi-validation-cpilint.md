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

### **To validate a package:**

1. Go to a required package in the Release Packages screen under Release Section and click **Actions**. Click **Validate** to start the validation process.

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
