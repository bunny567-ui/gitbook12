# CPI Governance Rules

The CPI Rules section in ReleaseOwl provides a centralized configuration interface to enforce governance policies and best practices for SAP Cloud Platform Integration (CPI) artifacts. These rules ensure that artifacts comply with security, coding, and operational standards

By configuring CPI Rules, administrators can establish policies that improve security, consistency, and reliability in CPI development and deployments.

## 1. Key Objectives of CPI Rules

* Standardization: Enforce consistent development practices across artifacrs
* Security Compliance: Restrict insecure configurations (e.g., clear text authentication).
* Governance: Enable rule-based validation to prevent policy violations.
* Custom Policies: Define naming conventions and resource allowances.

## 2. Accessing CPI Rules

1. Navigate to Administration → Static Code Analysis → CPI Rules from the sidebar menu.
2. The CPI Rules Dashboard displays a list of pre-configured rules and customization options.

## 3. Configuring CPI Rules

### 3.1 Enabling/Disabling Rules

* Check or uncheck the checkbox next to each rule to enable or disable it.
* Enabled rules will be enforced during artifact deployments and validations.

### 3.2 Configuring Custom Policies

Use the dropdown fields for the following:

* Allowed Scripting Languages
* Allowed Receiver Adapters
* Allowed Sender Adapters
* Allowed XSLT Versions
* Allowed Mapping Types
* Duplicate Resources Not Allowed
* Select the appropriate options from the dropdown menus to align with your organizational policies.

### 3.3 Naming Conventions

* Use the Naming Conventions text area to define custom naming rules for IFLOWs, resources, and endpoints.

## 4. Save Configuration

* Once all configurations are updated, click on the Save button at the top-right corner.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
