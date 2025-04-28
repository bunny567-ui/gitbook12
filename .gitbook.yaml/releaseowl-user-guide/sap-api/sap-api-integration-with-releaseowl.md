# SAP API Integration with ReleaseOwl

1\.      Navigate to Environments from the Administration menu.

2\.      Select API Management and click on register API Management.

3\.      Provide the following details and click on **save.**

| **Field**        | **Description**                                                                 |
| ---------------- | ------------------------------------------------------------------------------- |
| Name             | Enter a unique name for the SAP CPI Environment.                                |
| Host URL         | Provide the Host URL for connecting to the SAP API Environment from service key |
| OAuth Credential | Select the OAuth credentials used for API Portal,API Access authentication.     |
| Environment Type | Select the environment type (e.g., Dev, QA, Prod).                              |

<figure><img src="../../.gitbook/assets/image (959).png" alt=""><figcaption></figcaption></figure>

### Create the Project <a href="#create-the-project" id="create-the-project"></a>

**1. Navigate to the Administration Page**

* Go to the **Administration** page of the application.

**2. Access the Projects Section**

* Under the **Projects** section, locate the **Create New Project** button.
* Click on the **Create New Project** button located at the top right corner.

**3. Fill in the Project Details**

* A popup form titled **Create Project** will appear.
* Enter the following details:

Here’s the information formatted as a table:

| **Field**          | **Description**                                                                                |
| ------------------ | ---------------------------------------------------------------------------------------------- |
| **Name**           | Provide a unique name for your project.                                                        |
| **Description**    | Optionally, add a description for better clarity.                                              |
| **Project Prefix** | Specify a prefix that aligns with your project standards. This will act as a short identifier. |
| **Project Type**   | Select **SAP CPI** as the project type.                                                        |

<figure><img src="../../.gitbook/assets/image (7) (1) (1).png" alt=""><figcaption></figcaption></figure>

**5. Configure the Project Settings**

* To the right of each project, click on the **action button** (three dots).
* Click on **Switch To Project** to navigate to the configuration page of the selected project.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F2Dn3Qm6ImFNuHL8a1e1S%252Fimage.png%3Falt%3Dmedia%26token%3De95acfbd-5890-48ca-86b3-3c0bda8f80f2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e5aadaba&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Navigate to the **Project Settings** page. Click the **Environments** tab.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FlLnTTq33CQJypWdCloj0%252Fimage.png%3Falt%3Dmedia%26token%3D9a20a37f-6183-42ac-ba96-0e282c43d216&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b94b3af0&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click **+ Add** (top-right of the **Environments** table).
* Select the desired environment and click **Select**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FH5MQ229cbWTjicoLwGGh%252Fimage.png%3Falt%3Dmedia%26token%3Df8e09b3e-02e0-4a96-9f67-6a812e422736&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=45061be4&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* If this environment is the **source for deployments or synchronization**, check the **Source** checkbox.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F0rKjO6Md4mon3oWXf0oM%252Fimage.png%3Falt%3Dmedia%26token%3D6aa63082-9af7-44c1-9add-efae772de1f8&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=918ffff3&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**6. Manage User Roles and Permissions**

* Go to the **Users** tab.
* Click the **Edit (lock) icon** next to the user.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F1mQm9D1fEcm6N8h4BFkn%252Fimage.png%3Falt%3Dmedia%26token%3D67d2d457-66b6-405b-9d6f-77f727999312&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e651d26c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Check the **Deploy** checkbox for relevant environment(s)

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FyUKbEmsVdfHG7Cw8g1u8%252Fimage.png%3Falt%3Dmedia%26token%3D6a3c1976-1580-4051-8730-335c5ff2de2a&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a17a922c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**7. Synchronize API Management Artifacts**

* Navigate to **API Management (Beta)**.
* Click **Synchronize** to sync API proxies created in **SAP API**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fr4KtoIO20ImCAGwcK6au%252Fimage.png%3Falt%3Dmedia%26token%3D43630a07-dc32-4c99-a409-0317f552685d&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=22d3c421&#x26;sv=2" alt=""><figcaption></figcaption></figure>

8. **Configure Artifacts**

* In the " **API** **Artifacts**" list, click the three dots in the "**Actions**" column for the desired artifact.
* Select "**Configure**" from the list.

<figure><img src="../../.gitbook/assets/image (1086).png" alt=""><figcaption></figcaption></figure>

* On the configuration screen, click the **Modify Values** button to update the required fields.
* Use the **Target Endpoints** view to configure endpoint details across multiple environments.

<figure><img src="../../.gitbook/assets/image (1087).png" alt=""><figcaption></figcaption></figure>

### Creating a Release Pipeline <a href="#pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline" id="pdf-page-della43ge2ynalx23r7p-creating-a-release-pipeline"></a>

Release Pipelines in ReleaseOwl manage approvals, validations, deployments, automated tests, task assignments, and user story updates for SAP systems.

**1. Create a New Release Pipeline**

* Navigate to **Release Pipelines**.
* Click **Create New Release Pipeline**.

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Provide a **Pipeline Name**.

<figure><img src="https://open.gitbook.com/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F02Nu3sYI7jhLWH36mwUk%252Fimage.png%3Falt%3Dmedia%26token%3Db0546bb3-8bb9-4902-889b-4ac5022d1e6c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=18908539&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Add stages (e.g., QA, Prod) and assign tasks to each stage.

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

#### Managing Sprints and User Stories <a href="#managing-sprints-and-user-stories" id="managing-sprints-and-user-stories"></a>

**1. Create a Sprint**

* In the **Project View**, navigate to **Change Management**.
* Click **Create Sprint**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252F3CVWW53nDb3soqZIqCrY%252Fimage.png%3Falt%3Dmedia%26token%3D7e838dbf-d632-4afc-886a-eb43ca4d839f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2a39c1cd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Enter the **Sprint Name** and click **Save**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FI2BzhgyQLZNVN006mB9I%252Fimage.png%3Falt%3Dmedia%26token%3D85a9ddb4-d5e9-425b-9990-bbc8dbcffcef&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2e585e27&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click the **three dots (Actions) button** and select **Start Sprint**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FGbN4NTGx6aVqmo7GXwEi%252Fimage.png%3Falt%3Dmedia%26token%3D776ccadc-9f28-4b62-bf6f-c7e842991a58&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=484b2198&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**2. Create a User Story**

* Go to **User Stories** and click **Create New User Story**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FHm3czXRNXBFSZcx6ys5U%252Fimage.png%3Falt%3Dmedia%26token%3D1023c3ec-4556-410d-8786-cd811d8c5211&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=6adc500c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Fill in the required details:
  * **Summary:** Provide a summary of the user story.
  * **Type:** Select the type of story.
* Click **Save.**

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FBvxTjv7XdldRSJJBHnby%252Fimage.png%3Falt%3Dmedia%26token%3D68a7944e-0314-4b03-a671-fd9df56f77c2&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=b39208ce&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click the **three dots button**, then select **Edit**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252Fz17Xyqtz5J6UIKiyIxTb%252Fimage.png%3Falt%3Dmedia%26token%3D821d067c-0253-44a5-b4bb-92baa2d72daa&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=18aa2e4e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**3. Manage API Management Artifacts**

* Go to **API Management Artifacts**.
* Click **+ Add** to add API Management artifacts.
* Select the **Release Pipeline and Component**.
* Click **Save**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FuFb66wSumGYiUFhTQUgY%252Fimage.png%3Falt%3Dmedia%26token%3D6b5f39c5-6af9-4aed-bf63-159cda51daf6&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d69ffe7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click the **three dots button**, then select **Promote**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FKkGYShxDsN9OOn3BmFFo%252Fimage.png%3Falt%3Dmedia%26token%3D2189903a-b0d7-40dd-b602-538814dc6f8f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1e7ba85a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

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

* The **Deployment Tasks** will show as **Approved**.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FeEtLCYXQ1rREFPZyMOaW%252Fimage.png%3Falt%3Dmedia%26token%3Dc2cb8fcc-1c07-474b-85d2-e4e046e16343&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=62fc6563&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click **Deploy Logs** to view details:
* **Artifact Name**
* **Type**
* **Version**
* **Deploy Status**

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2486808281-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FntTXS8vTRxGt8qfbPi3l%252Fuploads%252FIAjyRZUBDNfFdIqxTFCF%252Fimage.png%3Falt%3Dmedia%26token%3D90788559-ebf9-42ea-80d5-c98c1872a408&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d8e375af&#x26;sv=2" alt=""><figcaption></figcaption></figure>
