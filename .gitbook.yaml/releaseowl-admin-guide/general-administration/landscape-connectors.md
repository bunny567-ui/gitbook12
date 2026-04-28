---
hidden: true
---

# Landscape Connectors

In general, SAP ECC and S/4HANA landscape systems will be deployed in the Client Network. As a SaaS platform, ReleaseOwl must communicate with the SAP system from the ReleaseOwl Network. There are multiple ways you can establish secure communication between ReleaseOwl and SAP systems.

### Whitelisting ReleaseOwl Server IP Address

Users must add the ReleaseOwl IP Address as a trusted IP in the client network settings. The IP address will be provided by mail communication during implementation.

### Setting Up SAP Router

**Reverse Proxy**\
A reverse proxy server is a type of proxy server that typically sits behind the firewall in a private network and directs client requests to the appropriate backend server. It provides an additional level of abstraction and control to ensure the smooth flow of network traffic between clients and servers.

ReleaseOwl will connect to the SAP On-Premise domain controller using **Apache2** as **Reverse Proxy** as follows:

**Apache2 Reverse Proxy Configuration**

* Transport Domain Controller URL: `https://<domain-controller>:8080`
* Reverse Proxy (Apache2 server) URL: `https://<proxy-host>:443/`
* Sample Configuration of reverse Proxy (Apache2) in file:\
  `/etc/apache2/sites-enabled/rosap-ssl.conf`

<figure><img src="../../.gitbook/assets/image (1184).png" alt=""><figcaption></figcaption></figure>

## **ReleaseOwl Transport Domain Controller Configuration**



<figure><img src="../../.gitbook/assets/image (1186).png" alt=""><figcaption></figcaption></figure>

### **Application Server:**

**Port:** port to access the proxy

**Credential:** SAP On-Prem userID and password

### **Setting up Proxy Server**

SAP Router is a proxy between SAP systems on different networks and between SAP systems and external applications which means it acts as an additional layer of filter/firewall in addition to the main firewall.

ReleaseOwl interacts with SAP Systems via HTTP/HTTPS protocol, but SAP Router runs on Network Layer (NI) which cannot understand the HTTP/HTTPS protocol. So, we have to configure Reverse Invoke (RI) in SAP Router referring to the below link

[https://help.sap.com/viewer/af8bcf35778c4d098ba482cc0b59f339/7.5.22/en-US/46d37ef8e5343c1de10000000a155369.html](https://help.sap.com/viewer/af8bcf35778c4d098ba482cc0b59f339/7.5.22/en-US/46d37ef8e5343c1de10000000a155369.html)

The diagram below shows connection flow between SAP Routers (server and client)<br>

<figure><img src="../../.gitbook/assets/image (1185).png" alt=""><figcaption></figcaption></figure>

**Note:** One SAP Router should be configured for each domain controller because of HTTPS access using reverse invoke.

**RI Configuration of Server SAP Router**

RI can be configured with SNC (Secured Network Communications) or without SNC.

**With SNC**

SAP Router communication can be made more secure using Secure Network Communications by referring to the following links:

[https://support.sap.com/en/tools/connectivity-tools/saprouter/install-saprouter.html](https://support.sap.com/en/tools/connectivity-tools/saprouter/install-saprouter.html)

or

[https://wiki.scn.sap.com/wiki/display/Basis/How+to+setup+SNC+connection+between+SAProuters](https://wiki.scn.sap.com/wiki/display/Basis/How+to+setup+SNC+connection+between+SAProuters)

For secure communication certificates should be exchanged between client and server.

**Configuration File**

server = true

client\_hostname = 3.232.119.28 (Actual IP will be provided during setup)

client\_service = 5001

reg\_service = 5002 (to be provided by customer during setup)

**Route Permission file**

KP p: \* 8080

**Start SAP Router**

./saprouter -K p: -i -S 4002 -R

**Without SNC**

Configuration File

server = true

client\_hostname = 3.232.119.28 (Actual IP will be provided during setup)

client\_service = 5001

reg\_service = 5002

Route permission file

3.232.119.28 \* 8080

Start SAP Router

./saprouter -i -S 4002 -R

### **Configuration parameters that are required by RO from customer**

* Server certificates for SNC configuration
* Common Name (CN) of Server SAP Router to specify in route permission table
* IP address and port number for accessing Server SAP Router
* Domain name or IP and HTTP port of the Domain controller URL (These ports need not be opened to outside of customer network)

### **Configuration parameters that are required by customer from RO**

* Client certificate for SNC configuratio&#x6E;**(nexus URL)**
* Common Name (CN) of client SAP Router to specify in the route permission table
* Client SAP Router registration port, Access port and IP to establish RI connection.

### **Reference Links**

* [https://support.sap.com/en/tools/connectivity-tools/saprouter.html#section\_1556745727](https://support.sap.com/en/tools/connectivity-tools/saprouter.html#section_1556745727)[https://help.sap.com/saphelp\_nwce10/helpdata/en/46/d37f01e5343c1de10000000a155369/content.htm?no\_cache=true](https://help.sap.com/saphelp_nwce10/helpdata/en/46/d37f01e5343c1de10000000a155369/content.htm?no_cache=true)
*

    ### Creating a Release Pipeline <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

    Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

    **1. Create a New Release Pipeline**

    * Navigate to **Release Pipelines**.
    * Click **Create New Release Pipeline**.

    <figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)  (29).png" alt=""><figcaption></figcaption></figure>

    * Provide a **Pipeline Name**.
    * Add stages (e.g., QA, Prod) and assign tasks to each stage.

    <figure><img src="../../.gitbook/assets/image (13) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fp9bYnD6MU10rrjza1IzY%252Fimage.png%3Falt%3Dmedia%26token%3D7e30a12a-4061-483e-a9a2-06d82b9f2caf&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3549c696&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    **2. Add Deployment Tasks**

    * Click the **Add** button in a task stage to include deployment tasks.
    * Fill in the required details:
      * **Name:** Enter a preferred name for the deployment task.
      * **Deploy Type:** Select **API**.
      * **API Management:** Select the target API environment.

    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fqfn1WVRDYayxAzHAcdYs%252Fimage.png%3Falt%3Dmedia%26token%3D7c13f154-42df-4ac1-986f-0ebd12fb0d60&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ec530eef&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    **3. Add Approval Tasks**

    * Click the **Add** button in a task stage to include approval tasks.
    * Fill in the required details:
      * **Name:** Enter a preferred name for the approval task.
      * **Assign To:** Select the user responsible for approval.
    * Click **Save**.

    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F9qsSsahluL3mHYz2eBGN%252Fimage.png%3Falt%3Dmedia%26token%3D626877d4-54bd-471b-a1c0-eccc21f0b96f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=13a93698&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    ### Managing Sprints and User Stories <a href="#managing-sprints-and-user-stories" id="managing-sprints-and-user-stories"></a>

    **1. Create a Sprint**

    * In the **Project View**, navigate to **Change Management**.
    * Click **Create Sprint**.

    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F3CVWW53nDb3soqZIqCrY%252Fimage.png%3Falt%3Dmedia%26token%3D7e838dbf-d632-4afc-886a-eb43ca4d839f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2a39c1cd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    * Enter the **Sprint Name** and click **Save**.

    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FI2BzhgyQLZNVN006mB9I%252Fimage.png%3Falt%3Dmedia%26token%3D85a9ddb4-d5e9-425b-9990-bbc8dbcffcef&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2e585e27&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    * Click the **Actions button** and select **Start Sprint**.

    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FGbN4NTGx6aVqmo7GXwEi%252Fimage.png%3Falt%3Dmedia%26token%3D776ccadc-9f28-4b62-bf6f-c7e842991a58&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=484b2198&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    **2. Create a User Story**

    * Go to **User Stories** and click **Create New User Story**.

    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FHm3czXRNXBFSZcx6ys5U%252Fimage.png%3Falt%3Dmedia%26token%3D1023c3ec-4556-410d-8786-cd811d8c5211&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6adc500c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    * Fill in the required details:
      * **Summary:** Provide a summary of the user story.
      * **Type:** Select the type of story.
    * Click **Save.**

    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FBvxTjv7XdldRSJJBHnby%252Fimage.png%3Falt%3Dmedia%26token%3D68a7944e-0314-4b03-a671-fd9df56f77c2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b39208ce&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    * Click the **Action button**, then select **Edit**.

    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fz17Xyqtz5J6UIKiyIxTb%252Fimage.png%3Falt%3Dmedia%26token%3D821d067c-0253-44a5-b4bb-92baa2d72daa&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=18aa2e4e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

    **3. Manage API Management Artifacts**

    * Go to **API Management Artifacts**.
    * Click **+ Add** button to add the selected artifact by choosing the artifact from the drop down button and click on the OK button.

    <figure><img src="../../.gitbook/assets/image (1775).png" alt=""><figcaption></figcaption></figure>

    * Select the **Release Pipeline and Component**.
    * Click **Save**.

    <figure><img src="../../.gitbook/assets/image (1776).png" alt=""><figcaption></figcaption></figure>

    <div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p><strong>Note:</strong> You can <strong>promote a user story</strong> directly from the <strong>Edit User Story</strong> screen in ReleaseOwl.</p></div>

### Attachments Section

The **Attachments** section allows users to add reference links directly to their items for easy access and documentation.

#### Steps to Add a Link

1. Navigate to the **Attachments** section of the desired item.
2. Click the **Link** button.
3. In the dialog box, enter the following details:
   * **Name** – Provide a meaningful name for the link.
   * **URL** – Enter the complete URL of the reference link.
4. Click **Add t**o attach the link.&#x20;
5. The added link will be listed in the **Attachments** section and can be viewed by all relevant users.

<figure><img src="../../.gitbook/assets/image (15) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### Promoting a User Story

To promote a user story:

1. Go back to the created **User Story**.
2. Click the **Action** button (three dots).
3. Select **Promote** from the dropdown menu.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FKkGYShxDsN9OOn3BmFFo%252Fimage.png%3Falt%3Dmedia%26token%3D2189903a-b0d7-40dd-b602-538814dc6f8f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1e7ba85a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* **Activity log:** The activity log helps track the progress of deployment tasks, identify any issues or failures, and maintain a record of who performed each action.

<figure><img src="../../.gitbook/assets/image (17) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**4. Approval Process**

* Before deployment, an **Approval Section** appears.
* The assigned user must approve/reject the task.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FeduWLKFqG2PRFJbl37rH%252Fimage.png%3Falt%3Dmedia%26token%3D8ab36408-58de-4741-8cc4-91dc3c21838f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=70a726b1&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Navigate to **My Tasks**.
* Click **Approve/Reject** in the **Actions** column.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FCOkGkJYxl0OQQdcNoDrD%252Fimage.png%3Falt%3Dmedia%26token%3D809ed910-948b-404c-ab6b-8bd747e4f574&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=16098f71&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**5. Deployment Monitoring**

* After approval, go to **Pipeline Activity**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fzc5Uiu3G65ApYmscGwW4%252Fimage.png%3Falt%3Dmedia%26token%3D7341562d-2449-4a4f-9eec-948a1da6d5e0&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=813b8eca&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Once the **Deployment Tasks** are marked as **Approved**, the deployment process begins. After completing the deployment, you can review the detailed **Deploy Logs.**

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FeEtLCYXQ1rREFPZyMOaW%252Fimage.png%3Falt%3Dmedia%26token%3Dc2cb8fcc-1c07-474b-85d2-e4e046e16343&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=62fc6563&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Deploy Logs

* **Deploy Status**: Reflects the final deployment status of the API artifact to the target environment.
* **Already Deployed**: Indicates that the API artifact was previously deployed, either as part of a retry or through manual completion. This status helps avoid redundant deployments and ensures clarity during re-runs.

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

* **Manual Completion**: If a deployment fails in **ReleaseOwl**, but the artifact has been successfully deployed or addressed directly in the backend system (e.g., **SAP API Management**) through manual intervention, users can use the **Manual Completion** option in **ReleaseOwl** to mark the deployment step as completed.

**To perform manual completion:**

1. Click the **Mark as Complete** button to proceed with the pipeline.

<figure><img src="../../.gitbook/assets/image (19) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. After marking as complete, click the **Continue** button to resume the previously failed deployment stage.

<figure><img src="../../.gitbook/assets/image (20) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. You will see a confirmation that the **deployment has resumed successfully**.&#x20;

<figure><img src="../../.gitbook/assets/image (21) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. The **deployment status** will then update to **Completed**, indicating that the process finished successfully.&#x20;

<figure><img src="../../.gitbook/assets/image (22) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Retry Button**\
Allows users to retry a failed deployment or re-execute a failed stage of the pipeline.

<figure><img src="../../.gitbook/assets/image (23) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
