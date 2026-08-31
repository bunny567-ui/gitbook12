# Datasphere Environment Registration

To register the SAP Datasphere Environment, you must first register the Datasphere credential. Follow the [link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-datasphere/administration/credential-management) and complete the credential setup.

### **To Register SAP Datasphere** <a href="#pdf-page-dk8rbzgxugve408ig5ly-to-register-sap-datasphere" id="pdf-page-dk8rbzgxugve408ig5ly-to-register-sap-datasphere"></a>

1. In Environments, go to **SAP Datasphere**.

<figure><img src="../../../.gitbook/assets/image (1358).png" alt=""><figcaption></figcaption></figure>

2. Click **Register SAP Datasphere Environment**. The following screen is displayed:

<figure><img src="../../../.gitbook/assets/image (1359).png" alt=""><figcaption></figcaption></figure>

3. **Fill in the required details:**

* **Name**: Enter a name for your reference.
* **OAuth Credentials**: Select the SAP Datasphere OAuth Credentials registered with ReleaseOwl.
* **Host URL**: The Datasphere tenant URL.
* **Environment Type**: Select the environment type you are registering (e.g., Dev or QA, etc.).

4. Click **Save** to register the environment.

<figure><img src="../../../.gitbook/assets/image (1360).png" alt=""><figcaption></figcaption></figure>

### Space Mapping

Space Mapping defines how the spaces of a source SAP Datasphere environment correspond to the spaces of a target environment. During deployment, ReleaseOwl imports the content into the mapped target space. A space mapping must be created for each source-to-target environment pair before the first deployment.

#### Creating a Space Mapping

1. Click **Space Mapping** in the top-right corner.

<figure><img src="../../../.gitbook/assets/image (2240).png" alt=""><figcaption></figcaption></figure>

2. The **Space Mappings** panel opens, listing the existing mappings. Use the **Search mappings** bar to find a mapping by name. Use the **Search mappings** bar to find a mapping by name. If no mappings exist, the message _"No space mappings yet. Choose Create to add the first one."_ is displayed.
3. Click **Create**.

<figure><img src="../../../.gitbook/assets/image (2241).png" alt=""><figcaption></figcaption></figure>

4. Fill in the required details:

| Field                   | Description                                                                                   |
| ----------------------- | --------------------------------------------------------------------------------------------- |
| **Name**                | Enter a name for the space mapping.                                                           |
| **Source Environment**  | Select the Datasphere environment whose spaces are the source (e.g., the development tenant). |
| **Target Environment**  | Select the environment to which the content will be deployed (e.g., the QA tenant).           |

<figure><img src="../../../.gitbook/assets/image (2242).png" alt=""><figcaption></figcaption></figure>

5. The **Map Spaces** section displays all spaces of the selected source environment. The counter in the header shows how many spaces are mapped.

<figure><img src="../../../.gitbook/assets/image (2243).png" alt=""><figcaption></figcaption></figure>

5. For each source space, open the **Select target space** dropdown and choose the corresponding space in the target environment.
   * Click **✕** next to a row to clear its selection.
   * Click the **Refresh** icon to reload the space lists from the tenants.
6. Once the required spaces are mapped, click **Create** to create the mapping.&#x20;

<figure><img src="../../../.gitbook/assets/image (2244).png" alt=""><figcaption></figcaption></figure>

7. The newly created mapping appears in the **Space Mappings** list.

<figure><img src="../../../.gitbook/assets/image (2245).png" alt=""><figcaption></figcaption></figure>

#### How Space Mapping is used

When a user story or release package is deployed from the source environment to the target environment, ReleaseOwl looks up the space mapping and imports each package into the **mapped target space**. Ensure that every space whose content will be delivered has a target space selected — a package belonging to an unmapped source space has no destination in the target environment.

#### Environment Actions

1. Click on the required environment to view the details.
2. Click the **edit icon** to edit the registered SAC Environment.

<figure><img src="../../../.gitbook/assets/image (2246).png" alt=""><figcaption></figcaption></figure>

3. Click the **delete icon** to delete the required environment.

<figure><img src="../../../.gitbook/assets/image (1361).png" alt=""><figcaption></figcaption></figure>



