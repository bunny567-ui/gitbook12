# Trading Partner Management

The Trading Partner Management (TPM) module in Releaseowl lets you synchronize, manage, version, and deploy SAP TPM artefacts across your SAP Integration Suite environments.

Releaseowl integrates with SAP Trading Partner Management to manage the deployment lifecycle of TPM artifacts. Using this module, you can synchronize Agreements and Partner Directory artifacts from a source environment, organize them into User Stories, and promote them through your Release Pipelines

## Prerequisites

Before using the TPM module in Releaseowl, the following must be in place:

**1. Role for Partner Directory sync (public API)**

Releaseowl syncs Partner Directory data using SAP's public **Process Integration Runtime API**. For this to work, assign the following role to the technical/integration user in SAP:

* **`AuthGroup_TenantPartnerDirectoryConfigurator`**

This authorizes Releaseowl's public API calls to read and update Partner Directory attributes.

**2. Roles for Agreement actions (web authentication)**

Agreement-level actions — sync and activation — go through web/browser authentication against the TPM tenant, not the public API. In the tenant's **Trust Configuration**, assign both of the following roles to the user/role collection Releaseowl authenticates as:

* **`TPM Agreement Configuration – Edit`**
* **`TPM Agreement Configuration – Activate`**

Both roles are required together.

**3.  Enable Trading Partner Management for an Environment**

To turn on TPM support for an SAP CPI environment:

1. Go to **Administration → Environments**.
2. Select the relevant SAP CPI environment (or register a new one if it isn't already added).
3. Under **General Information**, check **Enable Trading Partner Management**.
4. Once checked, a **Configure Import Options** button appears next to it — use this to set the tenant-level (default) import behavior for TPM artifacts synced into this environment.
5. Click **Save** on the environment.

<figure><img src="../../.gitbook/assets/image (2042).png" alt=""><figcaption></figcaption></figure>

4. You'll also need to set up a Releaseowl **Project** and add the **source** and **target** environments (e.g., Dev as the source, QA/Prod as the target) between which TPM artifacts will move.

## &#x20;B2B Scenarios (cpi)

Select the B2B secenarions in the cpi environment. It shows three tabs agreement, partner directory and partner configuration&#x20;

Once the prerequisites above are complete, open **B2B Scenarios** within the CPI environment/project. This screen has **three tabs**:

1. **Agreements**
2. **Partner Directory**
3. **Partner Directory Configuration**

### **1. Agreements**

This tab is where agreements exported from the SAP TPM tenant are brought into Releaseowl and tracked.

&#x20;**Adding an Agreement**

* Click **Add Artifacts**. Every agreement that has already been **exported** from the source SAP TPM tenant is listed here and can be pulled into Releaseowl.
* Releaseowl does not create or edit agreements — it only ever reflects what has already been exported in SAP.

<figure><img src="../../.gitbook/assets/image (2036).png" alt=""><figcaption></figcaption></figure>

Once an agreement is added, use the action options to view its details, download the artifact, and check its deployment history.

| Action                 | What it does                                                                                                  |
| ---------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Details**            | Shows what's contained inside the agreement — the configuration elements bundled into that agreement package. |
| **Download**           | Downloads the exported agreement artifact/package to your local machine.                                      |
| **Deployment History** | Shows the history of deployments carried out for that agreement — which environment, when, and the outcome.   |

<figure><img src="../../.gitbook/assets/image (2037).png" alt=""><figcaption></figcaption></figure>

### 2. Partner Directory&#x20;

Use this tab to view the Partner Directory data behind your agreements directly — the raw identifiers and parameters — independent of any configuration grouping.

* Entries appear as type **String** or **Binary**.
* You can **sync** any entry as an artefact from SAP into Releaseowl.
* Each entry has a **sync history**, showing when it was last synced and its status.
* Use **Search by ID** to jump straight to a specific Partner Directory attribute instead of scrolling the full list.

<figure><img src="../../.gitbook/assets/image (2038).png" alt=""><figcaption></figcaption></figure>

### 3.  Partner Directory Configuration Tab

This is the Releaseowl-only artefact used to **group specific Partner Directory attributes together** so they can be versioned and deployed as a single unit — instead of moving every attribute one at a time.

**Create a configuration**

1. Go to the **Partner Directory Configuration** tab.

<figure><img src="../../.gitbook/assets/image (2043).png" alt=""><figcaption></figcaption></figure>

2. Click **Create Partner Directory Configuration**.
3. In the pop-up, enter:
   * **Artifact Name**
   * **Version**
4. Click **Create**. Your new configuration now appears in the configuration list.

<figure><img src="../../.gitbook/assets/image (2040).png" alt=""><figcaption></figcaption></figure>

5. Click the **Actions** button on your configuration, then choose **Edit**.
6. Click **Add**, and select the Partner Directory data (attributes/IDs) you want included.
7. Click **Save**.

<figure><img src="../../.gitbook/assets/image (2041).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note: I**f you go back later and add more Partner Directory IDs to the same configuration, Releaseowl saves that change as a **new version** rather than overwriting the existing one — so each meaningful change to the attribute set is preserved as its own version.
{% endhint %}

**Configurations:**

* To change the value of a parameter on an attribute you've already added, open the **Configurations** button for that Partner Directory ID.

<figure><img src="../../.gitbook/assets/image (2044).png" alt=""><figcaption></figcaption></figure>

* If the attribute is of type **Binary**, a form opens inline within the configuration where you can update the value of its parameters directly.

<figure><img src="../../.gitbook/assets/image (2045).png" alt=""><figcaption></figcaption></figure>

**Deployment History and Versions**

* **Deployment History** shows you the past deployments of this configuration.
* **Versions** lists every version created for the configuration. From here, you can **assign a specific version to a User Story** for deployment.

### 4. Working with User Stories

Once your Agreements and/or Partner Directory Configurations are ready, bundle them into a User Story for deployment:

1. Assign the artifact (or a specific configuration version) to a **User Story** — either from the artefact's **Versions** screen, or by user story sections
2. &#x20;Go to  **B2B Scenarios** and click **Add** to attach the Agreement or Partner Directory Configuration to that User Story.

<figure><img src="../../.gitbook/assets/image (2046).png" alt=""><figcaption></figcaption></figure>

3. **Agreements:** Click the **Actions** button on an agreement inside the User Story to open its **import settings**, where you'll find:

* **Force Deploy** — lets you redeploy the agreement again even if it was already deployed.
* **Individual artefact import settings** — artefact-specific import options that override the environment's tenant-level default.

<figure><img src="../../.gitbook/assets/image (2047).png" alt=""><figcaption></figcaption></figure>

4. **Partner Directory Configuration:** Import settings here only offer **Force Deploy** — there are no individual artefact-level import settings for this artifact type.

#### Deployment order

Releaseowl always deploys in this order:

1. **Agreement is imported first.**
2. **Partner Directory Configuration is imported afterward.**

This order is enforced deliberately — if the Partner Directory Configuration were deployed first, the Agreement import/activation that follows would **override** it. Deploying the Agreement first, then the Partner Directory Configuration, keeps your Partner Directory data intact.

<figure><img src="../../.gitbook/assets/image (2048).png" alt=""><figcaption></figcaption></figure>

### 5. Promoting and Monitoring a Deployment

1. Click **Promote** to deploy the User Story's artifacts through the pipeline.
2. This opens the **deploy logs**, showing you what was deployed, along with each artifact's **import status.**&#x20;

<figure><img src="../../.gitbook/assets/image (2049).png" alt=""><figcaption></figcaption></figure>

3. Click the **import status** icon next to any Agreement or Partner Directory Configuration to view its detailed **import logs**.

<figure><img src="../../.gitbook/assets/image (2050).png" alt=""><figcaption></figcaption></figure>

3. Click the **activation status** icon (success or failed) on an Agreement to view its **activation logs**.

<figure><img src="../../.gitbook/assets/image (2051).png" alt=""><figcaption></figcaption></figure>

