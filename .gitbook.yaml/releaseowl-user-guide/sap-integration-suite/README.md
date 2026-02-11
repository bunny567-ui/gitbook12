# SAP Integration Suite

ReleaseOwl seamlessly integrates with **SAP Cloud Integration (CPI)** to enable continuous integration and delivery of integration artifacts. Through secure credential management and environment registration, ReleaseOwl connects directly with the CPI tenant to manage, deploy, and monitor artifacts across development, quality, and production landscapes.

### Prerequisites

**1. Tenant Provisioning**

* A **ReleaseOwl Tenant/Subaccount** must be provisioned for your organization by the **ReleaseOwl team**.
* Once provisioned, ReleaseOwl will share the **URL to access the ReleaseOwl Subaccount**.

**2. User Access**

* Ensure that users have access to **SAP BTP** through one of the following authentication mechanisms:
  * **SAP Identity Authentication Service (IAS)** using **S-User ID**
  * **Custom Identity Provider (IDP)**

**3. Tenant Admin Details**

* Provide the **email ID(s)** that should be added as **Tenant Admin** in ReleaseOwl.
* These users will have administrative privileges to manage the tenant.

**4. User Management in ReleaseOwl**

* Grant access to the ReleaseOwl platform by **adding users within the platform**.
* Assign each user an appropriate **user role**, such as:
  * **Admin** – for full administrative access
  * **User** – for standard operational access

