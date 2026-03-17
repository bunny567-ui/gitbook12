# SAP ABAP Cloud Communication Setup

This document outlines the configuration steps required to set up the **SAP BTP ABAP Environment (ABAP Cloud)** for integration with the ReleaseOwl dashboard. It includes the creation of the service instance, Service Key, Communication Arrangements, and Software Components

### 1. Prerequisites

To access **SAP BTP ABAP Environment (ABAP Cloud)**, ensure the following:

1. An active subscription to the **ABAP Environment** service in SAP BTP.
2. An ABAP Environment instance created in the relevant subaccount.
3. Web access enabled with required role collections assigned to users.

### 2. ABAP Cloud Setup- Step- by- Step Configuration Guide

#### Step 1: Create a Service Key

After successfully creating the ABAP Environment instance, follow these steps to generate a Service Key:

1. Log in to the **SAP BTP Cockpit**.
2. Navigate to your **Subaccount** → **Instances and Subscriptions**.
3. Select the created **ABAP Environment** instance.
4. Go to the **Service Keys** section.
5. Click **Create Service Key**.
6. Provide a name for the service key and click **Create**.

<figure><img src="../.gitbook/assets/image (15) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Step 2: Create Communication Keys&#x20;

Communication keys must be created for the required **communication scenarios** in the ABAP Environment instance.

Follow the steps below:

1. Navigate to your **ABAP Environment instance** in the SAP BTP Cockpit.
2. Select the **Service Keys** section.
3. Click **Create Service Key**.
4. Provide the required **JSON configuration** for the communication scenario.
5. Click **Create** to generate the service key.

#### Service Key for Software Component Integration (SAP\_COM\_0510)

Use the following JSON configuration:

```
{"scenario_id": "SAP_COM_0510", "type": "basic"}
```

<figure><img src="../.gitbook/assets/image (1702).png" alt=""><figcaption></figcaption></figure>

#### Service Key for ABAP Unit Test Integration (SAP\_COM\_0735)

Similarly, create the service key for **ABAP Unit Test Integration** using the following JSON configuration:

```
{"scenario_id": "SAP_COM_0735","type": "basic"}
```

<figure><img src="../.gitbook/assets/image (1701).png" alt=""><figcaption></figcaption></figure>

#### Alternative Method: Create Communication Arrangements in ABAP Cloud

Communication arrangements can also be created directly in the **ABAP Cloud system** for the required communication scenarios.

1. Log in to the **ABAP Cloud system**.
2. Navigate to **Administration → Communication Arrangements**.

<figure><img src="../.gitbook/assets/image (13) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Click **New**.

<figure><img src="../.gitbook/assets/image (14) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Select the Communication Scenario:

* **SAP\_COM\_0510 – Software Component Test Integration**

5. Click **Create**.

<figure><img src="../.gitbook/assets/image (15) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. In the **Common Data** section:
   * Enter an **Arrangement Name**.
   * In the **Communication System** field, click **New** to create a new system.

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

#### Create Communication System

1. Enter a **System ID** and **Name** (as per naming convention).
2. Click **Create** to generate the Communication System.

<figure><img src="../.gitbook/assets/image (17) (1).png" alt=""><figcaption></figcaption></figure>

#### Create User for Outbound Communication

1. Under **Outbound Communication**, click the **“+” (Add)** button.

<figure><img src="../.gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>

2. Enter:

* User Name (as per naming convention)
* Password (define a secure password of your choice, following your organization’s password policy)

3. Click **Create**.

<figure><img src="../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>

4. Click **Save** to complete the arrangement setup.

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

#### &#x20;Create Communication Arrangement for ABAP Unit Test Integration (SAP\_COM\_0735)

Repeat the same process for ABAP Unit Test Integration:

1. Go to **Communication Arrangements**.
2. Click **New**.
3. Select Communication Scenario:
   * **SAP\_COM\_0735 – ABAP Unit Test Integration**
4. Click **Create**.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

5. In the **Common Data** section:
   * Enter an **Arrangement Name**.
   * In the **Communication System** field, click **New** to create a new system.
6. Enter a **System ID** and **Name** (as per naming convention).
7. Click **Create** to generate the Communication System.

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

**Create User for Outbound Communication**

1. Under **Outbound Communication**, click the **“+” (Add)** button.
2. Enter:
   * User Name (as per naming convention)
   * Password (define a secure password of your choice, following your organization’s password policy)
3. Click **Create**.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

4. Click **Save** to complete the arrangement setup.

<figure><img src="../.gitbook/assets/image (10) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Verification of Service Details

Once the **communication arrangements (SAP\_COM\_0510 and SAP\_COM\_0735)** are successfully created and activated, the corresponding **service details** can be verified in the **Service Key generated for the ABAP Environment service instance**.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

## 3. Manage Software Components

#### Step 3: Create Software Component

1. In the ABAP Cloud system, navigate to **Manage Software Components**.

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

2. Click **Create**.

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

3. Provide:

* **Software Component Name** (as per naming convention)
* **Type**
* **Repository URL (Git Repository URL)**

4. Click **Create**.

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

#### Step 5: Clone the Software Component

After creating the Software Component:

1. Select the created Software Component.
2. Click **Clone**.

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

3. Provide:

* **Git User Name**
* **Personal Access Token (PAT)**

4. Select the required **Branch** to clone.
5. Confirm the action.

The software component is now connected to the Git repository and ready for ReleaseOwl-based deployment.

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

Once the above setup is completed, the system will be ready for integration through ReleaseOwl.
