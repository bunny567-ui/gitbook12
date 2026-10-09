# KVM Configuration Parameters & APIM Deployment Behavior

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

**No Delete Operation**

ReleaseOwl does **not** perform delete operations for configuration parameters.

**Example Scenario**

* A parameter named `testParam` exists in the target environment.
* The same parameter is deleted from the source environment.
* During deployment:
  * ReleaseOwl **will not delete** `testParam` from the target.
  * The parameter remains unchanged in the target environment.

### APIM Deployment Behavior

#### API Proxy

When API Proxies are synchronized — either through **Add Artifacts (New Artifacts)** or through an individual sync of an existing proxy (with or without a new revision) — ReleaseOwl also captures the **Products** associated with the proxy.

During deployment of an API Proxy that is associated with a Product:

1. ReleaseOwl checks whether the Product is available in the **target environment**.
2. If the Product **is available**, the API Proxy is linked to the existing Product automatically.
3. If the Product **is not available**, ReleaseOwl does not create it — deploy the Product to the target first if the association is required.

#### API Product

1. During API Product deployment, any associated API Proxy that is **not available in the target environment is skipped** — only proxies existing in the target are associated with the Product.
2. If the API Product **already exists in the target environment**, you do not need to assign it to the User Story separately — during API Proxy deployment, ReleaseOwl automatically links the proxy to the existing Product in the target.

{% hint style="info" %}
**Deployment order tip:** when both a Product and its Proxies are new, deploy in an order that lets the associations resolve — the Product needs its proxies present in the target to associate them, and a proxy needs the Product present to link to it.
{% endhint %}
