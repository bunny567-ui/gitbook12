# Landscape Registration

## **Register SAP On-Premise Environment**

You have to register the SAP On-Premise system login credentials first to access the SAP On-Premise environment with ReleaseOwl.

### **Transport Manager Credential**

1. Navigate to Transport Domain Controller under Administration review to register a Transport Domain Controller. The screen looks as follows:

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Click Register Transport Domain Controller to register a new Transport Domain Controller.
3. Enter the required details and save the changes:

<figure><img src="../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="415">Name</th><th width="321" valign="middle">Any name of your choice for the Transport Domain Controller (TDC)</th></tr></thead><tbody><tr><td>Proxy Type</td><td valign="middle">Type of connectivity ( over the internet / Cloud connector) to access On-prem system</td></tr><tr><td>Proxy Url</td><td valign="middle">URL to access the destination (auto generated)</td></tr><tr><td>SAP Cloud Credentials</td><td valign="middle">Provide the registered BTP Service user credentials in ReleaseOwl</td></tr><tr><td>Client ID</td><td valign="middle">Client ID of the TDC</td></tr><tr><td><br>Destination</td><td valign="middle">Enter the destination name from the Connectivity section of SAP BTP.</td></tr><tr><td>SAP User</td><td valign="middle"> Enter the SAP Username from the Destination Configuration in the Connectivity section of SAP BTP.</td></tr><tr><td>Enable Retrofit</td><td valign="middle">If you want to perform transport retrofit, then you have to enable retrofit source</td></tr><tr><td>Retrofit Domain Controller ( Destination) </td><td valign="middle">Supports an <strong>N+2 configuration</strong> for Retrofit Domain Controllers. To improve redundancy and scalability, users can add <strong>multiple Retrofit Domain Controllers</strong> as needed. </td></tr><tr><td>System Landscape</td><td valign="middle">To fetch all the systems pertaining to the system landscape in use.</td></tr></tbody></table>

4. The newly created Transport Domain Controller gets displayed in the Transport Domain Controller screen.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Note**: Create the Transport Domain Controller in ReleaseOwl according to the destination created for all development environments.
