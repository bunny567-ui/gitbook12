# Environment Registration

This section explains the process of registering SAP Cloud and SAP ABAP environments in **ReleaseOwl**.

### SAP Cloud Environment Registration in ReleaseOwl

1. Log in to the **ReleaseOwl Dashboard**.
2. Navigate to **Environments**.
3. Click **Register SAP Cloud Environment**.

<figure><img src="../../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

**Provide the Following Details:**

4. **Name**: Enter a name as per your environment naming convention (e.g., DEV\_ABAP\_CLOUD).
5. **Region**: Select the region where the SAP BTP environment is hosted.
6. **API Endpoint**: Enter the API endpoint URL of the SAP BTP Cloud Foundry environment.

* This can be found in the **SAP BTP Cockpit** under:\
  **Subaccount → Cloud Foundry Environment → Overview**.

7. Copy the **API Endpoint** URL

<figure><img src="../../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

8. **Credential Name**: Select the previously registered credential from the dropdown list.
9. **Org**: Automatically populated after validating the API endpoint.
10. **Space**: Automatically populated after selecting the Org.
11. **Environment Type**: Select the appropriate environment type (e.g., Development, Quality, Production).
12. Click **Save** to register the SAP Cloud Environment.

<figure><img src="../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

### SAP ABAP Environment Registration in ReleaseOwl

1. Navigate to **SAP ABAP Environment** in the ReleaseOwl dashboard.
2. Click **Register ABAP Environment**.

<figure><img src="../../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

**Provide the Following Details:**

3. **Name**: Enter a name as per your environment naming convention.
4. **SAP Cloud Environment**: Select the previously registered **SAP Cloud Environment** from the dropdown list.
5. **ABAP Instance**: The ABAP service instance will be automatically populated based on the selected SAP Cloud Environment.
6. **ABAP Service Key**: Once the ABAP instance is selected, the available Service Keys will be displayed. Select the required **Service Key**.
7. **Host URL**: Automatically populated based on the selected **Service Key**.
8. **ABAP Credential**: Select the previously registered ABAP credential from the dropdown list.
9. **Environment Type**: Select the appropriate environment type (e.g., Development).
10. Click **Save** to complete the registration.

<figure><img src="../../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>
