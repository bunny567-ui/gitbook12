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

<figure><img src="../.gitbook/assets/image (15) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

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

### 2. Manage Software Components

#### Step 3: Create Software Component

1. In the ABAP Cloud system, navigate to **Manage Software Components**.

<figure><img src="../.gitbook/assets/image (28) (1).png" alt=""><figcaption></figcaption></figure>

2. Click **Create**.

<figure><img src="../.gitbook/assets/image (29) (1).png" alt=""><figcaption></figcaption></figure>

3. Provide:

* **Software Component Name** (as per naming convention)
* **Type**
* **Repository URL (Git Repository URL)**

4. Click **Create**.

<figure><img src="../.gitbook/assets/image (30) (1).png" alt=""><figcaption></figcaption></figure>

#### Step 5: Clone the Software Component

After creating the Software Component:

1. Select the created Software Component.
2. Click **Clone**.

<figure><img src="../.gitbook/assets/image (31) (1).png" alt=""><figcaption></figcaption></figure>

3. Provide:

* **Git User Name**
* **Personal Access Token (PAT)**

4. Select the required **Branch** to clone.
5. Confirm the action.

The software component is now connected to the Git repository and ready for ReleaseOwl-based deployment.

<figure><img src="../.gitbook/assets/image (33) (1).png" alt=""><figcaption></figcaption></figure>

Once the above setup is completed, the system will be ready for integration through ReleaseOwl.
