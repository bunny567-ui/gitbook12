# Landscape Mapping

In any DevOps or CI/CD setup for SAP or cloud-based applications, it is essential to define and manage the sequence of environments through which your applications or transport artifacts move — typically from Development to Production.

**ReleaseOwl** introduces **Landscape Mapping(Beta)** to streamline and govern this structured progression. Landscape Mapping in ReleaseOwl is composed of two main components:

1. **Landscape Stages**
2. **Landscape Stage System Mapping**

<figure><img src="../.gitbook/assets/image (1293).png" alt=""><figcaption></figcaption></figure>

### Landscape Stages

**Landscape Stages** represent the logical progression of environments that are part of the software delivery process. These stages reflect the different checkpoints where code or configurations are built, tested, validated, and finally released to users.  Typical stages in a landscape include: DEV, QA and Prod.&#x20;

**To define Landscape Stages:**

* Navigate to the **Landscape Mapping** screen.
* Click on the **"Landscape Stages"** tile.

<figure><img src="../.gitbook/assets/image (1294).png" alt=""><figcaption></figcaption></figure>

* Click the **Edit** button to begin adding or modifying stages.

<figure><img src="../.gitbook/assets/image (1295).png" alt=""><figcaption></figcaption></figure>

* Click **Add Stage** to insert a new stage (e.g., DEV, QA, PROD).
* After configuring the required stages, click the **Save** button to apply the changes.

<figure><img src="../.gitbook/assets/image (1296).png" alt=""><figcaption></figcaption></figure>

### Landscape Stage System Mapping

Once the stages are defined, each stage needs to be connected to an actual system or environment. **Landscape Stage System Mapping** is the process of linking each logical stage to a corresponding application runtime environment.

**To configure Landscape Stage System Mapping:**

1. Click on the **"Landscape Stage System Mapping"** tile.
2. Click the **Edit** button to begin mapping.

<figure><img src="../.gitbook/assets/image (1297).png" alt=""><figcaption></figcaption></figure>

3. Click the **+ Add Landscape** button.&#x20;

<figure><img src="../.gitbook/assets/image (1298).png" alt=""><figcaption></figcaption></figure>

4. A pop-up window will appear prompting you to provide the following details:

* **Landscape Name** – Enter a descriptive name for the landscape.
* **Environment Type** – Select the appropriate environment type from the dropdown (e.g., SAP CPI, API Management etc.).

5. Click **OK** to add the landscape mapping entry.

<figure><img src="../.gitbook/assets/image (1299).png" alt=""><figcaption></figcaption></figure>

6. Once all mappings have been added, click the **Save** button to save the landscape-to-environment mapping configuration.

<figure><img src="../.gitbook/assets/image (1300).png" alt=""><figcaption></figcaption></figure>

