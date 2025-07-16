# gCTS

gCTS is an offering from SAP that allows us to manage ABAP (Advanced Business Application Programming) change and transport management processes using Git as an external version management system. By integrating Git with the traditional SAP transport system, gCTS enables developers to leverage Git's powerful version control capabilities, branching strategies, and collaboration features in the context of SAP ABAP development.

### **Key Features** <a href="#pdf-page-5oopygj2qtse4j6l4ary-key-features" id="pdf-page-5oopygj2qtse4j6l4ary-key-features"></a>

* **Git Integration:** gCTS integrates Git repositories with SAP systems, allowing ABAP developers to store their source code, configurations, and other development artifacts in Git repositories.
* **Version Control:** Developers can take advantage of Git's version control features, such as branching, merging, and code reviews, to manage ABAP source code changes more efficiently.
* **Continuous Integration and Delivery (CI/CD):** By using Git and gCTS, SAP customers can set up CI/CD pipelines for ABAP development. This enables automation of testing, deployment, and release processes, leading to faster and more reliable software delivery.
* **Collaboration:** Developers can collaborate more effectively by using Git's collaboration features, such as pull requests and code reviews, to review and discuss code changes before they are merged into the main codebase.
* **Traceability and Auditing:** gCTS provides traceability and auditing capabilities, allowing organizations to track changes made to the SAP systems and ensuring compliance with regulatory requirements.

### **gCTS Integration with ReleaseOwl** <a href="#pdf-page-5oopygj2qtse4j6l4ary-gcts-integration-with-releaseowl" id="pdf-page-5oopygj2qtse4j6l4ary-gcts-integration-with-releaseowl"></a>

The integration of gCTS (Git-enabled Change and Transport System) with ReleaseOwl is a powerful combination for SAP customers. By integrating gCTS with ReleaseOwl, organizations can leverage the functionalities of Git repositories and establish robust Continuous Integration and Continuous Delivery (CI/CD) processes for their ABAP (Advanced Business Application Programming) development. The integration of gCTS with ReleaseOwl offers a streamlined and efficient approach to managing ABAP development, enabling organizations to deliver high-quality SAP applications faster, with reduced risks, and improved collaboration among team members. To enable gCTS we require a Git platform host, an ABAP system in which code will be developed, and a CI server (which is optional) which can be used to automate development cycle.

### **Prerequisites**

Before starting the gCTS configuration, ensure the following prerequisites are met:

* An **SAP S/4 HANA 1909 or 2022 system**
* An **SAP machine** (with version **11 or higher**) or comparable **JRE**
* Import the **relevant SAP Central Note** (based on the SP level of your system)
* Create **gCTS-related working directories** at the OS level

### **Configuration Steps**

Once the prerequisites are met and the ABAP system is ready, proceed with the configuration which consists of **three major steps**:

1. **gCTS Configuration on ABAP System**
2. **Git Enablement**
3. **CI/CD Pipeline Configuration in ReleaseOwl**

### **Steps in the ABAP System to Complete the gCTS Configuration**

1. Validate Required SAP Notes
2. Authorizations
3. Validate Required Ports
4. gCTS Fiori UI Enablement
5. Set Parameters and Initialize Systems

### **Systems in use here to guide the user the steps involved** <a href="#pdf-page-5oopygj2qtse4j6l4ary-systems-in-use-here-to-guide-the-user-the-steps-involved" id="pdf-page-5oopygj2qtse4j6l4ary-systems-in-use-here-to-guide-the-user-the-steps-involved"></a>

* Access to either GitHub or BitBucket
* Access to the gCTS environment of SAP (S4 2022). Here – S4D (main Dev system), S4Q (QA system) and S4V (virtual system for production).
* Each package should be linked to one repository.

### **Steps Involved in gCTS Configuration with GitHub**

1. Create a new repository in GitHub. (Example: `ZKRK_GCTS_SALES.` )
2. Open the **gCTS environment** for SAP using the **Fiori app URL**.
3. Log in using your **SAP gCTS ABAP system credentials**.
4. A **blank screen** is displayed by default upon successful login.

<figure><img src="../../../.gitbook/assets/image (8) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. **Search for:** `gcts` in the Fiori Launchpad.
6. **Select:** **Git-enabled CTS – Manage Repositories**.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

7. All **existing repositories** linked to the current gCTS environment are displayed.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

8. Click on **Create** to initiate repository creation.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

9. Fill the required details as follows:

| **Field**       | **Description**                                                                                                                                                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **URL**         | Enter the URL of the GIT repository you want to link with the SAP gCTS environment.                                                                                                                                                         |
| **Description** | Enter a relevant description, or keep the default description text.                                                                                                                                                                         |
| **vSID**        | <p>Enter any name of your choice. A virtual system with this name will be created in the <strong>Transport Route</strong>. </p><p></p><p><strong>Note</strong>: Each unique GIT repository requires its own virtual system in SAP gCTS.</p> |
| **Role**        | Select **Developer**.                                                                                                                                                                                                                       |
| **Type**        | Select **GitHub**.                                                                                                                                                                                                                          |
| **Visibility**  | You can choose either one: **Public** or **Private**.                                                                                                                                                                                       |

<figure><img src="../../../.gitbook/assets/image (4) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

10. Click **Save**. A new repository gets created.
11. Upon repository creation:
    * A new **transport layer** is automatically created.
    * This transport layer appears under the **Configuration** tab parameters.
    * The naming convention used is `Z<vSID>` where `<vSID>` is the system ID.
    * It is also visible in the **Transport Routes** screen.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FTBAFRySFEn4dPSt7q7ec%252Fimage.png%3Falt%3Dmedia%26token%3D89f1ad87-2381-4623-9ac3-39aa441620fe&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=82c9a32d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Repository Authorization and Configuration

12. **Authorization is required to clone the repository:**

    * Navigate to the **Configuration** tab.
    * Click **Create**.

    <figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

*   Add the following two parameters:

    * `CLIENT_VCS_AUTH_USER`: Enter the GitHub user ID in the **Value** field.
    * `CLIENT_VCS_AUTH_TOKEN`: Enter the GitHub personal access token.

    <figure><img src="../../../.gitbook/assets/image (7) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

13. Both parameters will appear in the configuration list.

<figure><img src="../../../.gitbook/assets/image (8) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### GitHub Branch Setup

14. Create required branches in GitHub:

* `dev` branch from `main`
* `qa` branch from `dev`&#x20;

<figure><img src="../../../.gitbook/assets/image (9) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Repository Cloning and Development in SAP

1. Navigate to the **SAP gCTS** application.&#x20;

<figure><img src="../../../.gitbook/assets/image (26) (1).png" alt=""><figcaption></figcaption></figure>

2. Clone the ABAP system repository with the one created in **GitHub**.

* This creates a **local copy** of the GitHub repository in the SAP ABAP system.
* The **latest commits** from GitHub become visible in the local repository.

<figure><img src="../../../.gitbook/assets/image (10) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. For every repository:

* The **default active branch** in SAP gCTS is `main`.
* Any changes made in SAP will be saved to this branch by default.
* Based on the requirement, the **active branch** can be changed (e.g., set to `dev` instead of `main`).

<figure><img src="../../../.gitbook/assets/image (11) (1) (1).png" alt=""><figcaption></figcaption></figure>

4. Create the **same package** in the SAP ABAP system as defined in the gCTS environment.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fe7JNwnrBFi2ZYQqcnuY9%252Fimage.png%3Falt%3Dmedia%26token%3D5ce3a0ee-6ed2-487f-ae3d-b2d62ff83de2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=47ca9a39&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. Enter all the required details:
   * Select the **transport layer** created during the repository creation in gCTS.
   * Click **Save**.

<figure><img src="../../../.gitbook/assets/image (13) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. The system prompts the user to **create a transport request**:

* Create a new transport request.
* Click **Save**.

<figure><img src="../../../.gitbook/assets/image (14) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (15) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (16) (1).png" alt=""><figcaption></figcaption></figure>

7. Now, **create a class** in the same package:

* Enter all the required details.
* Choose the appropriate package.
* Click **Save**.

<figure><img src="../../../.gitbook/assets/image (17) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure>

12. The system prompts to associate the class with a **transport request**:

    * Select the newly created transport request.
    * Save the changes.
    * Make required changes to the class.
    * Save and **activate** the objects.

    <figure><img src="../../../.gitbook/assets/image (21) (1).png" alt=""><figcaption></figcaption></figure>
13. **Release the task** associated with the transport request in use.

<figure><img src="../../../.gitbook/assets/image (22) (1).png" alt=""><figcaption></figcaption></figure>

### Integration of SAP gCTS with ReleaseOwl and GitHub

1. Register the **Transport Manager Credential** in the Credential Manager section in **ReleaseOwl**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FmAnBWAMz5cSiP8dAcUtk%252Fimage.png%3Falt%3Dmedia%26token%3D5ba017a4-4bfb-4d67-a7d6-fbab451f3ead&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=14d37a55&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. Register the **Transport Domain Controller** in ReleaseOwl:

* Click **Get Systems** to fetch all systems available in the system landscape.
* The newly created SAP system ID (e.g., **RKS**) will be listed.

<figure><img src="../../../.gitbook/assets/image (23) (1).png" alt=""><figcaption></figcaption></figure>

3. Register the **GITHub** credential in the **Credential** **Manager.**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FaCbeaaBUpptnGJhwPIA4%252Fimage.png%3Falt%3Dmedia%26token%3Dbaebab00-fe4e-44b8-9994-f938e945c4cd&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f97047e7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note: GITHub APIs** can be **accessed** only via **Personal Access Tokens** and **not** by **username** and **password.** For further information on the **Personal Access Tokens, please refer to the link -** [**https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token**](https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)&#x20;
{% endhint %}

4. Register the **dev** **ABAP** **system** in **ReleaseOwl** as follows:&#x20;

* Ensure to select the role as **Development**.
* Choose the appropriate credential for each repository.
* The SAP system should be the actual **Development system** (e.g., **S4D**) and **not** the gCTS Virtual System (e.g., **RKD**).

<figure><img src="../../../.gitbook/assets/image (24) (1).png" alt=""><figcaption></figcaption></figure>

5.  Set up the **QA gCTS system** for transporting changes from Dev to QA:

    * Set up the QA gCTS system to enable transport of changes from **Dev** to **QA**.&#x20;
    * Log in to the QA SAP gCTS system using SAP ABAP credentials and follow the same configuration steps as performed for the Dev gCTS system.

    <figure><img src="../../../.gitbook/assets/image (1317).png" alt=""><figcaption></figcaption></figure>



    <figure><img src="../../../.gitbook/assets/image (1316).png" alt=""><figcaption></figcaption></figure>
6. Create a **repository** in QA with the **same name** as in Dev.

* Fill in the required details accordingly.

| **Field**       | **Description**                                                                            |
| --------------- | ------------------------------------------------------------------------------------------ |
| **URL**         | Enter the URL of the GIT repository that you want to link with the SAP gCTS environment.   |
| **Description** | Enter a relevant description, or keep the default description text.                        |
| **vSID**        | Enter the name of the virtual system that was created in the SAP gCTS **Dev** environment. |
| **Role**        | Select **Provided**.                                                                       |
| **Type**        | Select **GitHub**.                                                                         |
| **Visibility**  | You can choose either one: **Public** or **Private**.                                      |

<figure><img src="../../../.gitbook/assets/image (1315).png" alt=""><figcaption></figcaption></figure>

7. Add two configuration parameters in QA as done in Dev:

* `CLIENT_VCS_AUTH_USER`
* `CLIENT_VCS_AUTH_TOKEN`&#x20;

<figure><img src="../../../.gitbook/assets/image (1312).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1311).png" alt=""><figcaption></figcaption></figure>

8. Clone the repository in **SAP gCTS (QA)** environment to the ABAP system.

<figure><img src="../../../.gitbook/assets/image (1313).png" alt=""><figcaption></figcaption></figure>

9. Switch the **active branch** from `main` to `qa`.

<figure><img src="../../../.gitbook/assets/image (1314).png" alt=""><figcaption></figcaption></figure>

10. Register the same ABAP system in **ReleaseOwl** for QA:

* Login to ReleaseOwl and add a new ABAP system.
* Select the role as **Provided**.
* Choose the appropriate credential for each repository.
* The SAP system should be the actual **QA system** (e.g., **S4Q**) and **not** the gCTS Virtual System (e.g., **RKS**).

<figure><img src="../../../.gitbook/assets/image (1318).png" alt=""><figcaption></figcaption></figure>

11. Add the appropriate **SAP ABAP environment** to the active project in ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (1319).png" alt=""><figcaption></figcaption></figure>

12. Create a **User Story** in ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (1320).png" alt=""><figcaption></figcaption></figure>

13. Add the **Transport Request** to the user story and save the changes.

<figure><img src="../../../.gitbook/assets/image (1321).png" alt=""><figcaption></figcaption></figure>

14. **Release** the **transport** **request** from **ReleaseOwl**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fn24bxnPWmgmEiOoFy5f0%252Fimage.png%3Falt%3Dmedia%26token%3D9b5f611f-3db9-4132-b0f0-4aa5d75b1582&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9bf82765&#x26;sv=2" alt=""><figcaption></figcaption></figure>

15. &#x20;Once the transport request is released:

* The associated **commits** can be viewed.
* In GitHub, refresh the repository — the new objects will now be visible in the **dev** branch.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FFjkF7ApVo9bHAlBOHrbg%252Fimage.png%3Falt%3Dmedia%26token%3Dc3cf443d-3384-41e6-9e6e-c388bcf2829e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2d91728a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Whenever a **transport request** which is **associated** with **gCTS** is **released**, all the **changes** will be **pushed** to **GIT**.
{% endhint %}

16. The changes **will not be pushed to QA** until the transport request is imported into QA.
17. Create a **Release Pipeline** in ReleaseOwl:
    * Add a **Deployment Task**.
    * Save the pipeline.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FnvfT2uhIFcufCuW207xt%252Fimage.png%3Falt%3Dmedia%26token%3Dbbf60e7d-5f30-4d53-b35a-b47d9943b3e2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c71c2ac3&#x26;sv=2" alt=""><figcaption></figcaption></figure>

18. Associate the release pipeline with the active **Project Settings** in ReleaseOwl.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FDegAsrJG6dJUlpOTZ5FJ%252Fimage.png%3Falt%3Dmedia%26token%3D234cd382-2984-43bc-907c-64c2b8fc9977&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=85799e1d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

19. &#x20;Grant **Deployment Permissions** to the user:
    * Navigate to: **Project Settings > Users > Security**.
    * Without this, deployment will not proceed.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FZzGt49QiqIK9Jg7LVU1F%252Fimage.png%3Falt%3Dmedia%26token%3D4477efe5-bc81-4219-ad5a-bbe2831bfa26&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=8c0d2872&#x26;sv=2" alt=""><figcaption></figcaption></figure>

20. &#x20;Promote the **User Story to QA**:

* Click **OK**.
* Check for any **Approval Tasks** that may be pending for **deployment** to take place.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FNFuBugUWLf6yMews4POZ%252Fimage.png%3Falt%3Dmedia%26token%3D7c4b02d0-b355-4876-a629-f3274239da32&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3363f04b&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F1P7o21IzfrzEiMqWxP31%252Fimage.png%3Falt%3Dmedia%26token%3D2ceff868-8128-4046-8125-d0733123338d&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a5a20fa0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

21. Once the **approver** **approves** the **task**, the **deployment** **starts**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FaSVWiaJULJnnBoMw0rKS%252Fimage.png%3Falt%3Dmedia%26token%3D4490062e-ee1d-4a82-8e70-12eb23f2befb&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=cce33a5&#x26;sv=2" alt=""><figcaption></figcaption></figure>

22. Click on **Go to Pipeline Activity**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FxfTKb7u5QsuQFV98iJg7%252Fimage.png%3Falt%3Dmedia%26token%3D072fa0c0-9c73-4560-ab7a-0dc7f0aaf827&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=984ab3b0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

23. **Check** the **Deployment Logs.**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FwKTJ81pHzn7Ebe53Gxsr%252Fimage.png%3Falt%3Dmedia%26token%3D90db97c1-eecf-4469-be73-fd806280ab32&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=11b9e3fc&#x26;sv=2" alt=""><figcaption></figcaption></figure>

24. &#x20;The gCTS task details are visible directly in the pipeline activity logs. This links the deployment to specific **gCTS tasks**, supporting traceability and audits.&#x20;

<figure><img src="../../../.gitbook/assets/image (1016).png" alt=""><figcaption></figcaption></figure>

25. When you click **“View gCTS  Switch Details”** in ReleaseOwl (Pipeline Activity > Logs), you can view metadata related to the gCTS operation for the associated deployment.

<figure><img src="../../../.gitbook/assets/image (1017).png" alt=""><figcaption></figcaption></figure>

26. **Validation Report:**&#x20;

* Click on the **Validation Report** button  for the selected User Story.&#x20;
  * After Validating,  you will find two tabs:
    * **TR Report**: Displays the details of the Transport Requests linked to the User Story.
    * **ATC Report**: Displays the ABAP Test Cockpit (ATC) results, highlighting any code quality or compliance issues.
  * **Release Status Check**
    * Under the **TR Report** tab, you will find:
      * **Release Status Check**:\
        Shows whether all the linked transports have passed the required checks.
        * **Status: Success** indicates everything is in order.
  * **gCTS Sequence Check (Beta)**
    * Located beside the Release Status Check.
    * sequence check (Beta) for gCTS transport to validate object-level sequences during the validation process.

<figure><img src="../../../.gitbook/assets/image (1088).png" alt=""><figcaption></figcaption></figure>

27. &#x20;When you click on the **gCTS Sequence Check (Beta)**:
    * You will see two sections:
      1.  **Transport Sequence Dependency**

          * This section shows the dependencies between different transport requests.

          <figure><img src="../../../.gitbook/assets/image (1089).png" alt=""><figcaption></figcaption></figure>

          <figure><img src="../../../.gitbook/assets/image (1090).png" alt=""><figcaption></figcaption></figure>
      2.  **Valid Transport Sequence**

          * This feature is used to validate the order in which SAP transport requests should be imported to avoid inconsistencies or errors in the target system.

          <figure><img src="../../../.gitbook/assets/image (1091).png" alt=""><figcaption></figcaption></figure>
28. Once deployment is successful:

* Verify that changes are pushed to the **qa branch** in GitHub.
* Login to **SAP gCTS (QA)** and confirm that the latest **commits** are available.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FAnXBENB6QupWyyxJh0AH%252Fimage.png%3Falt%3Dmedia%26token%3D13c3e7e5-6816-4044-bd37-e6bed990d075&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=26f15c3d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

27. Login to **S4Q (QA) ABAP system**:

* On the **first transport**, the package, class, and objects will be pushed to QA ABAP.
* On **subsequent transports**, only the changed objects will be updated in both:
  * SAP QA **gCTS Fiori**
  * SAP QA **ABAP system**

{% hint style="info" %}
**Note:**&#x20;

* Without ReleaseOwl, changes must be **manually pulled** into SAP QA ABAP from gCTS Fiori.
* With ReleaseOwl, this process is **automated**, pushing changes to both SAP QA gCTS and ABAP systems upon transport release.
{% endhint %}
