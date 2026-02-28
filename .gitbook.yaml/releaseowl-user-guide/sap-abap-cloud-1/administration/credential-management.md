# Credential Management

This section describes the process of registering system credentials in ReleaseOwl to enable secure communication with **SAP Cloud** and **ABAP Cloud environments.**

### Register SAP Cloud Credential in ReleaseOwl

1. Log in to the **ReleaseOwl Dashboard**.
2. Navigate to **Administration → Credential Manager**.
3. Click **Register Credential.**

<figure><img src="../../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

4. Provide the following details:

* **Credential Name**: Enter a name as per your naming convention.
* **Credential Type**: Select **SAP Cloud Environment**.
* **Scope**: Select the appropriate scope based on your project or environment configuration.
* **User Name**: Enter the **BTP credential user name**.
* **Password**: Enter the **password associated with the BTP credentials**.

5. Click **Save** to register the credential.

<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

### Register ABAP Cloud Credential in ReleaseOwl

Similarly, create a credential for the **ABAP Cloud Environment**:

1. Navigate to **Administration → Credential Manager** in the ReleaseOwl dashboard.
2. Click **Register Credential**.

<figure><img src="../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

**Provide the Following Details**:

* **Credential Name**: Enter a name as per your naming convention.
* **Credential Type**: Select **ABAP Cloud Communication**.
* **Scope**: Select **Global**.
* **User Name**: Enter the **Outbound Communication User** created in the ABAP Cloud Communication Arrangement.
* **Password**: Enter the password associated with the Outbound Communication User.

3. Click **Save** to register the credential.

<figure><img src="../../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

