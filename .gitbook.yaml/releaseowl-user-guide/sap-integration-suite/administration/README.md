# Administration

ReleaseOwl seamlessly integrates with **SAP Cloud Integration (CPI)** to enable continuous integration and delivery of integration artifacts. Through secure credential management and environment registration, ReleaseOwl connects directly with the CPI tenant to manage, deploy, and monitor artifacts across development, quality, and production landscapes.

To register an **SAP Integration Suite** environment in **ReleaseOwl**, you must complete the following two steps:

1. **Credential Management** – Configure and store the required OAuth or Basic Authentication credentials securely in the **Credential Manager** to enable authenticated access to the SAP CPI tenant.
2. **Environment Registration** – Register the **SAP CPI environment** by providing necessary details such as environment name, host URL (tenant endpoint), credential reference, and environment type (e.g., Dev, QA, Prod).

