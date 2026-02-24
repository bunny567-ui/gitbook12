# Key Value Map (KVM) Deployment Behavior

This document explains how **Key Value Map (KVM) configuration parameters** are handled during artifact deployment between source and target environments in ReleaseOwl. It covers deployment behavior for both **encrypted** and **non-encrypted** parameters.

### 1. Encrypted Configuration Parameters

#### 1.1 Artifact Not Present in Target Environment

If the artifact does **not** exist in the target environment:

* All configuration parameters must be **manually edited** in ReleaseOwl.
* Encrypted values **cannot be retrieved** from the SAP system.
* ReleaseOwl does **not** have the capability to read or copy encrypted values from the source environment.
* Therefore, encrypted values must be re-entered before deployment.

#### 1.2 Artifact Present and Updated in Target Environment

If the artifact already exists and is being updated:

* Configuration parameter values must be **manually updated** in ReleaseOwl.
* This ensures encrypted values are correctly provided during deployment.
* Existing encrypted values cannot be automatically reused or extracted

### 2. Non-Encrypted Configuration Parameters

#### 2.1 Artifact Not Present in Target Environment

If the artifact does **not** exist in the target environment:

* Configuration parameters from the source environment are deployed automatically.
* Users have the option to **review and edit** configuration parameters in ReleaseOwl before deployment.

#### 2.2 Artifact Present in Target Environment

If the artifact already exists:

* Only **updated configuration parameters** are deployed.
* Existing parameters remain unchanged unless explicitly modified in ReleaseOwl.

#### 2.3 Newly Added Configuration Parameters

If new configuration parameters are introduced in the source environment:

* These parameters are automatically added to the target environment during deployment.
* No manual recreation is required (for non-encrypted parameters).

### &#x20;Important Notes

#### No Delete Operation

ReleaseOwl does **not** perform delete operations for configuration parameters.

**Example Scenario:**

* A parameter named `testParam` exists in the target environment.
* The same parameter is deleted from the source environment.
* During deployment:
  * ReleaseOwl **will not delete** `testParam` from the target.
  * The parameter remains unchanged in the target environment.

