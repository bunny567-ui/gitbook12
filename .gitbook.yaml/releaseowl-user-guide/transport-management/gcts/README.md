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

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FNePlBYW9sUuWvdkC0Uv3%252Fimage.png%3Falt%3Dmedia%26token%3D52f22468-8a67-44ea-b4f6-d4e8b91bf8bb&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=34b97bf0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. **Search for:** `gcts` in the Fiori Launchpad.
6. **Select:** **Git-enabled CTS – Manage Repositories**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F5cefjEHcNSuM3TZY1P2A%252Fimage.png%3Falt%3Dmedia%26token%3D24dffa52-50fa-4278-8506-0e6ffd63ccf3&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=33b3af29&#x26;sv=2" alt=""><figcaption></figcaption></figure>

7. All **existing repositories** linked to the current gCTS environment are displayed.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F2HpKmHWtsqDRg8Cb2cSy%252Fimage.png%3Falt%3Dmedia%26token%3Dd181b564-b80b-4fc8-9fb1-4f8c4177719c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6345e74a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

8. Click on **Create** to initiate repository creation.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FWRz8fMhMfegE9VOizbrv%252Fimage.png%3Falt%3Dmedia%26token%3D84dc5854-b819-4ec9-94de-87abeb9ea162&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5aea5272&#x26;sv=2" alt=""><figcaption></figcaption></figure>

9. Fill the required details as follows:

| **Field**       | **Description**                                                                                                                                                                          |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **URL**         | Enter the URL of the GIT repository you want to link with the SAP gCTS environment.                                                                                                      |
| **Description** | Enter a relevant description, or keep the default description text.                                                                                                                      |
| **vSID**        | Enter any name of your choice. A virtual system with this name will be created in the Transport Route. **Note**: Each unique GIT repository requires its own virtual system in SAP gCTS. |
| **Role**        | Select **Developer**.                                                                                                                                                                    |
| **Type**        | Select **GitHub**.                                                                                                                                                                       |
| **Visibility**  | Select **Private**.                                                                                                                                                                      |

<figure><img src="../../../.gitbook/assets/image (1030).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F71vGi6X1MJHjCAgesP9w%252Fimage.png%3Falt%3Dmedia%26token%3D693b5a8d-4984-4c48-8246-3de608e48dbd&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ab5cf830&#x26;sv=2" alt=""><figcaption></figcaption></figure>

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



<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F1wB8kI9IuZnM2gAtOWb7%252Fimage.png%3Falt%3Dmedia%26token%3Da06041d9-eaba-49d8-ac3e-a3a04268b3f6&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=45f76fca&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click **Create**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FcsL74sinGv6SmYYXvzh8%252Fimage.png%3Falt%3Dmedia%26token%3D0d59125e-d07f-40d7-b391-c6551d2b8414&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5e86241b&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Add the following two parameters:
  * `CLIENT_VCS_AUTH_USER`: Enter the GitHub user ID in the **Value** field.
  * `CLIENT_VCS_AUTH_TOKEN`: Enter the GitHub personal access token.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FBeuuZHWDmdYhYLUv67fL%252Fimage.png%3Falt%3Dmedia%26token%3D105d8622-3198-4a0a-8d3b-58b007846851&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=97ce191d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F8RMulIFIRncRl15xaTyG%252Fimage.png%3Falt%3Dmedia%26token%3D2c7c0348-d36b-4735-bd71-a1bce6e93ae1&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=af7acda8&#x26;sv=2" alt=""><figcaption></figcaption></figure>

13. Both parameters will appear in the configuration list.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FSRNGF61dVZRk7i0NAKmF%252Fimage.png%3Falt%3Dmedia%26token%3D59253385-e2da-4722-858a-1e10be9336d4&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3913881d&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### GitHub Branch Setup

14. Create required branches in GitHub:

* `dev` branch from `main`
* `qa` branch from `dev`

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fj81w9AKkxeukuAgcDW0O%252Fimage.png%3Falt%3Dmedia%26token%3D945f3453-9178-485f-a427-83faa5136fef&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e225c853&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Repository Cloning and Development in SAP

1. Navigate to the **SAP gCTS** application.&#x20;

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FM75USqQltQDdOihNMs6A%252Fimage.png%3Falt%3Dmedia%26token%3D750fae6e-d043-4d1c-87a8-4e1a14ac2278&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a9cb8b1a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. Clone the ABAP system repository with the one created in **GitHub**.
   * This creates a **local copy** of the GitHub repository in the SAP ABAP system.
   * The **latest commits** from GitHub become visible in the local repository.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FkqnMwCty80Wwoxg9CnLn%252Fimage.png%3Falt%3Dmedia%26token%3D4bbaf4be-5202-4dc6-aef7-77e0c348778e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=7d186bb5&#x26;sv=2" alt=""><figcaption></figcaption></figure>

3. For every repository:
   * The **default active branch** in SAP gCTS is `main`.
   * Any changes made in SAP will be saved to this branch by default.
   * Based on the requirement, the **active branch** can be changed (e.g., set to `dev` instead of `main`).

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F2xWMQbroP5cpqfmJYshT%252Fimage.png%3Falt%3Dmedia%26token%3D5790d03a-4312-4e90-b7cc-55a775eb8b6a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5867eff0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

4. Create the **same package** in the SAP ABAP system as defined in the gCTS environment.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fe7JNwnrBFi2ZYQqcnuY9%252Fimage.png%3Falt%3Dmedia%26token%3D5ce3a0ee-6ed2-487f-ae3d-b2d62ff83de2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=47ca9a39&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. Enter all the required details:
   * Select the **transport layer** created during the repository creation in gCTS.
   * Click **Save**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F0peeJ3Pd038Tp4EFj2XW%252Fimage.png%3Falt%3Dmedia%26token%3D38e69e54-5080-4907-be98-9ed3ce8efe44&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=eadc4f0f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

6. The system prompts the user to **create a transport request**:
   * Create a new transport request.
   * Click **Save**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F6FMXTruRpRgoz5nepTny%252Fimage.png%3Falt%3Dmedia%26token%3D18f08248-c217-493a-b362-781722e54b9d&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5a62752f&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FNPeWoFDU8vibYoPRfxBW%252Fimage.png%3Falt%3Dmedia%26token%3Dd556152a-a76a-4b5b-ab4f-51d0e2d528fd&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=9f728610&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FzPA07j6GHwHhQY7f2jne%252Fimage.png%3Falt%3Dmedia%26token%3Db62f75e5-bc95-4ce2-a5ac-511ac65f9755&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=79b7f3e9&#x26;sv=2" alt=""><figcaption></figcaption></figure>

7. Now, **create a class** in the same package:

* Enter all the required details.
* Choose the appropriate package.
* Click **Save**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Fto94jXO0TuNtGAMYcP0c%252Fimage.png%3Falt%3Dmedia%26token%3D9d76f428-c8e7-4c17-816c-35f98a6c177b&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b5f5a072&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FrnI4yzKuh1UeScqv0Tdh%252Fimage.png%3Falt%3Dmedia%26token%3Dcb0bfb9d-1cf5-4cc0-883a-29903a71d014&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=dfb5c706&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FWZzH3Lm18LXeh6MVDDK2%252Fimage.png%3Falt%3Dmedia%26token%3D6f34cff6-1321-4812-aac7-b080ff0648f8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b44270ed&#x26;sv=2" alt=""><figcaption></figcaption></figure>

12. The system prompts to associate the class with a **transport request**:
    * Select the newly created transport request.
    * Save the changes.
    * Make required changes to the class.
    * Save and **activate** the objects.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FPuB2MCcaJ2Tulksrewtk%252Fimage.png%3Falt%3Dmedia%26token%3D271b22ab-6644-4548-b3ea-b2a76388bd40&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c62e44d3&#x26;sv=2" alt=""><figcaption></figcaption></figure>

13. **Release the task** associated with the transport request in use.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FtgxY9BHVl87WJ95MZnGq%252Fimage.png%3Falt%3Dmedia%26token%3D5d1477d4-940b-492b-9730-d19cbe54bea4&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=37f2acea&#x26;sv=2" alt=""><figcaption></figcaption></figure>



### Integration of SAP gCTS with ReleaseOwl and GitHub

1. Register the **Transport Manager Credential** in the Credential Manager section in **ReleaseOwl**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FmAnBWAMz5cSiP8dAcUtk%252Fimage.png%3Falt%3Dmedia%26token%3D5ba017a4-4bfb-4d67-a7d6-fbab451f3ead&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=14d37a55&#x26;sv=2" alt=""><figcaption></figcaption></figure>

2. Register the **Transport Domain Controller** in ReleaseOwl:

* Click **Get Systems** to fetch all systems available in the system landscape.
* The newly created SAP system ID (e.g., **RKS**) will be listed.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FG9vjhmsRt9GWc13vO3Wd%252Fimage.png%3Falt%3Dmedia%26token%3D1089ccf4-b9d1-45d9-8988-916e3931a4ae&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=73d2f5c2&#x26;sv=2" alt=""><figcaption></figcaption></figure>

3. **Register** the **GITHub** credential in the **Credential** **Manager.**

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FaCbeaaBUpptnGJhwPIA4%252Fimage.png%3Falt%3Dmedia%26token%3Dbaebab00-fe4e-44b8-9994-f938e945c4cd&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f97047e7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note: GITHub APIs** can be **accessed** only via **Personal Access Tokens** and **not** by **username** and **password.** For further information on the **Personal Access Tokens, please refer to the link -** [**https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token**](https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)&#x20;
{% endhint %}

4. **Register** the **dev** **ABAP** **system** in **ReleaseOwl** as follows:&#x20;

* Ensure to select the role as **Development**.
* Choose the appropriate credential for each repository.
* The SAP system should be the actual **Development system** (e.g., **S4D**) and **not** the gCTS Virtual System (e.g., **RKD**).

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FzqwBvOZ3ZR4d8sMOM47A%252Fimage.png%3Falt%3Dmedia%26token%3D8aed5cd2-c306-4af6-bfde-e3aa2c5c790e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d825b726&#x26;sv=2" alt=""><figcaption></figcaption></figure>

5. Set up the **QA gCTS system** for transporting changes from Dev to QA:
   * Login to **QA SAP gCTS** using SAP ABAP credentials.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FwPsLlwbSx4lJLuud9FX4%252Fimage.png%3Falt%3Dmedia%26token%3Dd6ce15f9-895a-4ba8-be50-3d1675e5801e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f6778890&#x26;sv=2" alt=""><figcaption></figcaption></figure>

6. Create a **repository** in QA with the **same name** as in Dev.

* Fill in the required details accordingly.

| **Field**       | **Description**                                                                            |
| --------------- | ------------------------------------------------------------------------------------------ |
| **URL**         | Enter the URL of the GIT repository that you want to link with the SAP gCTS environment.   |
| **Description** | Enter a relevant description, or keep the default description text.                        |
| **vSID**        | Enter the name of the virtual system that was created in the SAP gCTS **Dev** environment. |
| **Role**        | Select **Provided**.                                                                       |
| **Type**        | Select **GitHub**.                                                                         |
| **Visibility**  | Select **Private**.                                                                        |

7. Add two configuration parameters in QA as done in Dev:
   * `CLIENT_VCS_AUTH_USER`
   * `CLIENT_VCS_AUTH_TOKEN`

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FA5BrnOc34hS9zA1zb7Du%252Fimage.png%3Falt%3Dmedia%26token%3Dfd1ded6a-800e-41af-920b-78b7c02e5695&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e507c7e7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

8. Clone the repository in **SAP gCTS (QA)** environment to the ABAP system.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FqjsNkpV0TSbULZcoxLlT%252Fimage.png%3Falt%3Dmedia%26token%3Dad1a306b-f3de-4b8b-b0b0-bd510a75fb99&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=34bfdb5e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

9. Switch the **active branch** from `main` to `qa`.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FIP5vqPYb3rCEgjhLQ7sJ%252Fimage.png%3Falt%3Dmedia%26token%3Dd5392215-f0b2-4a91-a3d4-1de59ffabb59&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3015da44&#x26;sv=2" alt=""><figcaption></figcaption></figure>

10. Register the same ABAP system in **ReleaseOwl** for QA:
    * Login to ReleaseOwl and add a new ABAP system.
    * Select the role as **Provided**.
    * Choose the appropriate credential for each repository.
    * The SAP system should be the actual **QA system** (e.g., **S4Q**) and **not** the gCTS Virtual System (e.g., **RKS**).

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F0p178r6fbo6KtSDDoG1U%252Fimage.png%3Falt%3Dmedia%26token%3Dec699e6e-227e-408b-b1dc-83a45dbd9f72&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e0489b76&#x26;sv=2" alt=""><figcaption></figcaption></figure>

11. &#x20;Add the appropriate **SAP ABAP environment** to the active project in ReleaseOwl.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FcjwQmntxmDP5aeBZQWq6%252Fimage.png%3Falt%3Dmedia%26token%3D9ce63a3a-01d9-4839-be94-9664f1787ef7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=cb3b7332&#x26;sv=2" alt=""><figcaption></figcaption></figure>

12. Create a **User Story** in ReleaseOwl.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F4wAbeWqHcYC1iB1ynwZA%252Fimage.png%3Falt%3Dmedia%26token%3D838d4d74-18ac-4af8-978a-2845e54a1598&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3be179f4&#x26;sv=2" alt=""><figcaption></figcaption></figure>

13. **Add the transport request** to the user story and save the changes.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FCpJUBcr4fgIBxw2Mdpgo%252Fimage.png%3Falt%3Dmedia%26token%3D6eae6059-b318-4c27-b311-39e2400f4666&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f33fa082&#x26;sv=2" alt=""><figcaption></figcaption></figure>

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

26. Once deployment is successful:

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
