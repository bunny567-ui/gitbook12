# Trading Partner Management

The **Trading Partner Management (TPM)** module in ReleaseOwl enables you to synchronize, manage, version, and deploy SAP Trading Partner Management (TPM) artefacts across SAP Integration Suite environments.

ReleaseOwl integrates with SAP Trading Partner Management to manage the deployment lifecycle of TPM artefacts. It provides capabilities to synchronize Agreements and Partner Directory artefacts from the source environment, organize them into User Stories, and promote them through Release Pipelines.

### Prerequisites

Before using the TPM module in Releaseowl, the following must be in place:

1. Releaseowl syncs Partner Directory data using SAP's public **Process Integration Runtime API**. This requires the role: **`AuthGroup_TenantPartnerDirectoryConfigurator`**&#x54;his role must be assigned to the technical/integration user in SAP so Releaseowl's public API calls are authorized to read and update Partner Directory attributes.
2. Agreement-level actions (sync, activation) go through **web/browser authentication** against the TPM tenant, not the public API. In the tenant's **Trust Configuration**, assign both of the following roles to the user/role collection Releaseowl authenticates as:

* **`TPM Agreement Configuration – Edit`**
* **`TPM Agreement Configuration – Activate`**

3. **Enable Trading Partner Management**

&#x20;To enable Trading Partner Management for an SAP CPI environment:

1. Navigate to **Administration→ Environments**.
2. Select (or register) the relevant CPI environment **SAP CPI Environment**.
3. Under **General Information**, check **Enable Trading Partner Management**.
4. Once checked, a **Configure Import Options** button becomes available next to it — use this to set the tenant-level (default) import behavior for TPM artifacts synced into this environment
5. Save the environment.

<figure><img src="../../.gitbook/assets/image (2042).png" alt=""><figcaption></figcaption></figure>

4. Set up a Releaseowl **Project** and add the **source** and **target** environments (e.g., Dev as source, QA/Prod as target) that TPM artifacts will move between.

### Navigating to TPM: the B2B Scenarios Screen

Select the B2B secenarions in the cpi environment. It shows three tabs agreement, partner directory and partner configuration&#x20;

Once the prerequisites above are complete, open **B2B Scenarios** within the CPI environment/project. This screen has **three tabs**:

1. **Agreements**
2. **Partner Directory**
3. **Partner Directory Configuration**

#### **Agreements**

This tab is where agreements exported from the SAP TPM tenant are brought into Releaseowl and tracked.

&#x20;**Adding an Agreement**

* Click **Add Artifacts**. Every agreement that has already been **exported** from the source SAP TPM tenant is listed here and can be pulled into Releaseowl.
* Releaseowl does not create or edit agreements — it only ever reflects what has already been exported in SAP.

<figure><img src="../../.gitbook/assets/image (2036).png" alt=""><figcaption></figcaption></figure>

Once an agreement is added, Releaseowl exposes the following (via row-level image/icon options):

| Action                 | What it does                                                                                                  |
| ---------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Details**            | Shows what's contained inside the agreement — the configuration elements bundled into that agreement package. |
| **Download**           | Downloads the exported agreement artifact/package to your local machine.                                      |
| **Deployment History** | Shows the history of deployments carried out for that agreement — which environment, when, and the outcome.   |

<figure><img src="../../.gitbook/assets/image (2037).png" alt=""><figcaption></figcaption></figure>

#### Partner Directory&#x20;

This tab gives you direct visibility into the **Partner Directory** data behind your agreements — the raw identifiers and parameters, independent of any specific configuration grouping.

* Partner Directory entries of type **String** and **Binary**.
* Each entry can be **synced** as an artifact from SAP into Releaseowl.
* A **sync history** is available per entry, showing when it was last synced and its status.
* You can **search by ID** to locate a specific Partner Directory attribute directly, rather than scrolling the full list

<figure><img src="../../.gitbook/assets/image (2038).png" alt=""><figcaption></figcaption></figure>

#### Partner Directory Configuration Tab

This is the Releaseowl-only artefact used to **group specific Partner Directory attributes together** so they can be versioned and deployed as a single unit — instead of moving every attribute one at a time.

**To Create a Partner Directory Configuration**:

1. Navigate to **Partner Directory Configuration**.

<figure><img src="../../.gitbook/assets/image (2043).png" alt=""><figcaption></figcaption></figure>

2. Click on the "**Create Partner Directory Configuration.**"
3. In the pop-up, enter the:

* **Artifact Name**
* **Version**

4. Click **Create**. The configuration is created and displayed in the configuration list.

<figure><img src="../../.gitbook/assets/image (2040).png" alt=""><figcaption></figcaption></figure>

5. Click on " actions button and click the edit and click on add to addd the partner directory data.
6. Click "save" button.

<figure><img src="../../.gitbook/assets/image (2041).png" alt=""><figcaption></figcaption></figure>

7. After saving also you can add the different partner directoyr id but it will be saved as the new version.

Configurations:

You can chnage the parmater values by the configuratuions button of the created partner directory id.&#x20;

<figure><img src="../../.gitbook/assets/image (2044).png" alt=""><figcaption></figcaption></figure>

If the type is binary then the form will be open inside the configurations and you can change the value of the parameters

<figure><img src="../../.gitbook/assets/image (2045).png" alt=""><figcaption></figcaption></figure>

Deployment history :thumbsup:

Versions: You can also assign it to user story also.



User stories&#x20;

After assigning it to the user story and go to the b2b scenorios and click add to add the aggrements or partner directory configuration

<figure><img src="../../.gitbook/assets/image (2046).png" alt=""><figcaption></figcaption></figure>

When you click on the actions button of the type agreement , you can see the import settings where you can see the  force deploy where you can deploy it once again and indiviual artificats import settings.&#x20;

<figure><img src="../../.gitbook/assets/image (2047).png" alt=""><figcaption></figcaption></figure>

For partner directory the import settings there is only force deploy and the order of the deployment will always be import of agreement and followed by partner directory configuration. other wise the the partner directoyr configuration will be override.

Click on the promote and you can see the deploys logs of the depolyed  and its import status and etc

<figure><img src="../../.gitbook/assets/image (2048).png" alt=""><figcaption></figcaption></figure>

When you click on the icon of the import status you can see the import logs of the respective agrrements or partner directory configuration.&#x20;

<figure><img src="../../.gitbook/assets/image (2049).png" alt=""><figcaption></figcaption></figure>



When you click on the activation agreement status of the failed or success icon you can see logs of the active agreemment logs

<figure><img src="../../.gitbook/assets/image (2050).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (2051).png" alt=""><figcaption></figcaption></figure>

