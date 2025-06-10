# DocuSign

This guide provides a step-by-step walkthrough on accessing your DocuSign account, creating and managing templates, setting up group signatures, and integrating DocuSign with ReleaseOwl. Follow these instructions to streamline your document approval and signature processes efficiently.

### 1. Accessing Your DocuSign Account

1. Log in to your **DocuSign** account.
2. Navigate to **My Apps & Keys** from the account dashboard.

<figure><img src="../.gitbook/assets/image (581).png" alt=""><figcaption></figcaption></figure>

### 2. Go to Templates Section

1. Click on the Templates tab.
2. Select the Start button.
3. Inside the Start menu, choose "**Envelope Templates**" and then select "**Create a Template**".

<figure><img src="../.gitbook/assets/image (582).png" alt=""><figcaption></figcaption></figure>

#### Create a Template

1. Enter the required details:

* Template Name
* Template Description

2. Upload the document that requires a signature.

<figure><img src="../.gitbook/assets/image (583).png" alt=""><figcaption></figcaption></figure>

#### Add Recipients

1. Specify recipient details:

* Role
* Name
* Email

<figure><img src="../.gitbook/assets/image (584).png" alt=""><figcaption></figcaption></figure>

2. Click **"Next**" to proceed.

<figure><img src="../.gitbook/assets/image (585).png" alt=""><figcaption></figcaption></figure>

3. Drag and drop the Signature field onto the document where the recipient needs to sign.
4. Once all fields are placed, click the **"Send**" button.

<figure><img src="../.gitbook/assets/image (586).png" alt=""><figcaption></figcaption></figure>

### 3. Recipient's Actions

1. The recipient will receive an email containing a link to sign the document.
2. Click the **"Review Document"** button in the email to proceed.

<figure><img src="../.gitbook/assets/image (587).png" alt=""><figcaption></figcaption></figure>

3. The document will open in a new tab. The recipient should click the **"Tap to Sign"** button at the designated signature location.

<figure><img src="../.gitbook/assets/image (588).png" alt=""><figcaption></figcaption></figure>

### 4. Setting Up Group Signatures

1. Go to the Admin section.
2. Navigate to **Users and Groups** and click on **Signing Groups**.

<figure><img src="../.gitbook/assets/image (589).png" alt=""><figcaption></figcaption></figure>

3. Click the **Add Signing Group** button.

<figure><img src="../.gitbook/assets/image (590).png" alt=""><figcaption></figcaption></figure>

4. Provide a name for the signing group and click **Save**.

<figure><img src="../.gitbook/assets/image (591).png" alt=""><figcaption></figcaption></figure>

5. Click **Assign Users** to add members:&#x20;

* Click **Add User Manually** and enter the user’s name and email.&#x20;
* Click **Assign** to complete the process.&#x20;

<figure><img src="../.gitbook/assets/image (592).png" alt=""><figcaption></figcaption></figure>

**Using Group Signatures**

1. Go to **Agreements** and click the **Start** button.
2. Inside the **Start** menu, select **Envelopes** and then click on **Send an Envelope**.

<figure><img src="../.gitbook/assets/image (593).png" alt=""><figcaption></figcaption></figure>

3. Upload the document that requires a signature.
4. Add recipients and specify:

* Role
* Name
* Email

<figure><img src="../.gitbook/assets/image (594).png" alt=""><figcaption></figcaption></figure>

5. In the **Name** section, click the recipient’s name to open a popup.
6. Assign the group by selecting the group name and clicking **Apply Selected**.

<figure><img src="../.gitbook/assets/image (595).png" alt=""><figcaption></figcaption></figure>

7. Click **Next** to proceed.

<figure><img src="../.gitbook/assets/image (596).png" alt=""><figcaption></figcaption></figure>

8. Drag and drop the **Signature** field onto the document.
9. Click the **Send** button.

<figure><img src="../.gitbook/assets/image (597).png" alt=""><figcaption></figcaption></figure>

**Group Recipient's Actions**

1. All group members will receive an email containing a link to sign the document.
2. Any one member of the group can click the "**Review Document**" button in the email and complete the signature process.

<figure><img src="../.gitbook/assets/image (598).png" alt=""><figcaption></figcaption></figure>

### 5. Integrating DocuSign with ReleaseOwl

1. Go to the **Administration View** in ReleaseOwl.
2. Click on **Credential Manager** and then **Register Credential.**

<figure><img src="../.gitbook/assets/image (599).png" alt=""><figcaption></figcaption></figure>

3. Fill in the fields:

* **Credential Name:** Enter a reference name of your choice.
* **Credential Type:** Choose DocuSign.

<figure><img src="../.gitbook/assets/image (600).png" alt=""><figcaption></figcaption></figure>

Retrieve Client ID and Secret

1. Log in to **DocuSign** and click the “**Admin**” button.

<figure><img src="../.gitbook/assets/image (601).png" alt=""><figcaption></figcaption></figure>

2. Navigate to **Integrations** and select **Apps** and **Keys.**

<figure><img src="../.gitbook/assets/image (602).png" alt=""><figcaption></figcaption></figure>

3. Click **Add App** and **Integration Key**.

<figure><img src="../.gitbook/assets/image (603).png" alt=""><figcaption></figcaption></figure>

4. Copy the **Integration Key** which is nothing but the client id

<figure><img src="../.gitbook/assets/image (604).png" alt=""><figcaption></figcaption></figure>

5. Click on the “**Add Secret Key**” button which is nothing but the Client Secret.

<figure><img src="../.gitbook/assets/image (605).png" alt=""><figcaption></figcaption></figure>

6. Set the Redirect URI to:

* **https://na3.releaseowl.com/rateloginserver/api/oauth/accesstoken**

7. Check all allowed HTTP methods and click Save.

<figure><img src="../.gitbook/assets/image (606).png" alt=""><figcaption></figcaption></figure>

**Save Credentials in ReleaseOwl**

1. &#x20;After creating the app successfully, click on the **Actions** button, then select **Edit.**

<figure><img src="../.gitbook/assets/image (607).png" alt=""><figcaption></figcaption></figure>

&#x20;2\. In the Apps and Keys section, locate:

* API Account ID: This is the Account ID.
* Account Base URL: This is the API Host URL.
* Copy these URLs to paste them into the credential manager.

<figure><img src="../.gitbook/assets/image (608).png" alt=""><figcaption></figcaption></figure>

3. Use the following URLs:

* Token URL: The DocuSign URL with /oauth/token.
* Authorization URL: The DocuSign URL with /oauth/auth.

4. Copy all the credentials, paste them into the Register Credential, and click the **Save** button.

<figure><img src="../.gitbook/assets/image (609).png" alt=""><figcaption></figcaption></figure>

**Generate a Token**

1. In **Credential Manager**, select the created credential.
2. &#x20;Click **Generate Token** to verify if the entered credentials are correct.

<figure><img src="../.gitbook/assets/image (610).png" alt=""><figcaption></figcaption></figure>

**Create a Release Pipeline**

1. Navigate to the project view.
2. Click **View My Projects** in the top-right corner.

<figure><img src="../.gitbook/assets/image (612).png" alt=""><figcaption></figcaption></figure>

3. Select your desired project and click **Switch to Project.**

<figure><img src="../.gitbook/assets/image (613).png" alt=""><figcaption></figcaption></figure>

**Create a New Release Pipeline:**

* Go to the **Release Pipeline** section.
* Click **Create New Release Pipeline**.

<figure><img src="../.gitbook/assets/image (614).png" alt=""><figcaption></figcaption></figure>

* Provide a name for the release pipeline.
* Add stages as required.

<figure><img src="../.gitbook/assets/image (615).png" alt=""><figcaption></figcaption></figure>

* In each stage, go to the **Tasks** section, click **Add,** and select **DocuSign Approval**.

<figure><img src="../.gitbook/assets/image (616).png" alt=""><figcaption></figcaption></figure>

**Assign Users for Approval:**

* Under Assign To, select the User option.
* Click the Select User field.
* Click the icon next to the "**Select User**" field (the square icon)

<figure><img src="../.gitbook/assets/image (617).png" alt=""><figcaption></figcaption></figure>

• In the user selection window that appears, choose the desired user and confirm the selection.

<figure><img src="../.gitbook/assets/image (618).png" alt=""><figcaption></figcaption></figure>

* For Credentials, use the dropdown menu to select the appropriate credentials.

<figure><img src="../.gitbook/assets/image (619).png" alt=""><figcaption></figcaption></figure>

Configure Approval Templates:

1. **Use Template:** Click **Get Templates** to fetch the available templates.

<figure><img src="../.gitbook/assets/image (620).png" alt=""><figcaption></figcaption></figure>

* After selecting **Get Templates**, you will receive the signed document in DocuSign on ReleaseOwl.
* If you click on the Document ID, you can view the document.
* Click on **Add** Template to retrieve the template, and then click the **Close** button.

<figure><img src="../.gitbook/assets/image (621).png" alt=""><figcaption></figcaption></figure>

2. **Manual Upload:**

* Provide a description for the subject.
* Click + to add a recipient and fill in their details.

<figure><img src="../.gitbook/assets/image (622).png" alt=""><figcaption></figcaption></figure>

• Click **Save**.

<figure><img src="../.gitbook/assets/image (623).png" alt=""><figcaption></figcaption></figure>

**Promoting a User Story with Manual Template**

1. **Create a User Story:**

* Begin by creating a user story in ReleaseOwl and save it.

<figure><img src="../.gitbook/assets/image (624).png" alt=""><figcaption></figcaption></figure>

2. Edit the User Story:

* Open the saved user story, and add the Release Pipeline and relevant components.
* Add CPI artifacts and click **Save**.

<figure><img src="../.gitbook/assets/image (625).png" alt=""><figcaption></figcaption></figure>

3. Promote the User Story:

* Click **Promote**. The recipient will receive an email notification.

<figure><img src="../.gitbook/assets/image (626).png" alt=""><figcaption></figcaption></figure>

* Click on the link in the approval email, and you will be directed to a new tab for the approval.

<figure><img src="../.gitbook/assets/image (627).png" alt=""><figcaption></figcaption></figure>

* Click on **Status** to add the templates, and a side screen will open.

<figure><img src="../.gitbook/assets/image (628).png" alt=""><figcaption></figcaption></figure>

* Add the respective documents and add the recipients. Click on **Next** to add the signature on the document.

<figure><img src="../.gitbook/assets/image (629).png" alt=""><figcaption></figcaption></figure>

* After adding the signature, click on the **Send** button.

<figure><img src="../.gitbook/assets/image (630).png" alt=""><figcaption></figcaption></figure>

* The recipient will receive the document for review.

<figure><img src="../.gitbook/assets/image (631).png" alt=""><figcaption></figcaption></figure>

* After reviewing and signing the document, the user story status will change to Completed.

4. **Review and Sign:**

* The recipient will click on the approval link in their email and be directed to the document for review.
* After reviewing and signing the document, the user story status will change to **Completed**.

&#x20;**Promoting a User Story with Upload Template**

1. **Create a User Story:** Start by creating a user story in ReleaseOwl and save it.

<figure><img src="../.gitbook/assets/image (636).png" alt=""><figcaption></figcaption></figure>

2. Edit the User Story:

* Edit the saved user story to add the Release Pipeline and necessary components.
* Add CPI artifacts and click **Save**.



<figure><img src="../.gitbook/assets/image (635).png" alt=""><figcaption></figcaption></figure>

3. **Promote the User Story**: Click **Promote** to initiate the approval process.

<figure><img src="../.gitbook/assets/image (634).png" alt=""><figcaption></figcaption></figure>

4. The recipient will receive an email notification, and the status will remain **Waiting** until they approve.

<figure><img src="../.gitbook/assets/image (633).png" alt=""><figcaption></figcaption></figure>

5. **Review and Sign:**

* The recipient will click the link in the approval email to review the document.
* After reviewing and signing, the user story status will change to Completed.

<figure><img src="../.gitbook/assets/image (632).png" alt=""><figcaption></figcaption></figure>
