# Message Listener

The **Message Listener Task** in ReleaseOwl is designed to pause a pipeline until it receives a specific message event from an external ALM (Application Lifecycle Management) system. Once the expected message is received, the pipeline resumes execution.

### Prerequisites

Before using the Message Listener Task, make sure that:

* An **ALM integration** is already configured and attached to the project.

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* The project has an **external User Story ID** from an ALM system (e.g., Jira, ServiceNow).

<figure><img src="../../../.gitbook/assets/image (1413).png" alt=""><figcaption></figcaption></figure>

### How to Add a Message Listener Task <a href="#how-to-add-a-message-listener-task" id="how-to-add-a-message-listener-task"></a>

* Go to your **Project View** in ReleaseOwl.
* Click on **Release Pipelines**.
* Select **Create New Release Pipeline** (or edit an existing pipeline).

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FOyM9H219tLuVgb3NGBed%252Fimage.png%3Falt%3Dmedia%26token%3D4c4d5f4f-86b2-47ce-a572-947a0cb1aab7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ea4736b1&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Add an **Approval Task** if required.
* Add the **Message Listener Task**.
* Click **Save** to save the pipeline.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F4Z99ea6Fph5mo9csKSm1%252Fimage.png%3Falt%3Dmedia%26token%3D3e683462-cf28-4b1d-a862-7b92de7b41b3&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a86502d4&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### Assign Variables <a href="#assign-variables" id="assign-variables"></a>

In ReleaseOwl, the _**Assign Variables**_ feature allows you to capture dynamic data during pipeline execution and store it in named variables. These variables can later be reused in different stages, such as scheduling a deployment at a specific date and time. In the case of a **Message Listener**, values can be assigned to these variables by parsing the JSON payload received by the listener.&#x20;

**How to Use "Assign Variables" in ReleaseOwl**

When you click **Assign Variables** in the **Message Listener** task configuration screen, a pop-up window appears. This feature allows you to define pipeline variables that will be dynamically populated with data received from the external message.

The **Assign Variables** screen contains a table with two columns:

* **Name** : Specify the name of the pipeline variable you want to create. This is the variable that will hold the extracted data. (**Note:** Special characters and spaces are not allowed in the variable name.)
* **Value** : Provide the mapping expression that extracts data from the incoming message. The syntax depends on the structure and format of the message.

**Mapping Syntax**

Use the following format to map variables to event message properties:

```
${resp.<message-object>.<property>}
```

Where:

* **resp** → Represents the entire response message.
* **\<message-object>** → The key or object name inside the message (as defined in the Message Listener configuration).
* **\<property>** → The field within the `<message-object>` whose value you want to extract.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252Ftufm6SPt1Xyw0xlqHiGd%252Fimage.png%3Falt%3Dmedia%26token%3D2f6e4e1d-829c-4e90-a46f-462210cc1158&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1fc43e53&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### User Story Promotion <a href="#user-story-promotion" id="user-story-promotion"></a>

* Promote the User Story directly in ReleaseOwl.
* Open the **Pipeline Activity** view.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

* Locate the **Message Listener** task.
* Click **Send Message** to open the message form and view the event payload details.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252FhIaDerENANMxuUKOwrAB%252Fimage.png%3Falt%3Dmedia%26token%3Dd0853d0b-ed8c-46da-8ace-593e29746067&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=707e7ffd&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Click **Save**. Once the correct message is received, the pipeline proceeds to the next stage.

<figure><img src="https://releaseowl.gitbook.io/releaseowl-docs/~gitbook/image?url=https%3A%2F%2F1890383800-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FDWyxe6hm5vqosFaByVgs%252Fuploads%252F5eg3xLxFjP2gTvuiwRZM%252Fimage.png%3Falt%3Dmedia%26token%3D4b414e40-22c5-4963-8ec4-4d70475d86c9&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=c610ff1c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Optionally, click **View Message** to inspect the event details and confirm what was received.

<figure><img src="https://releaseowl.gitbook.io/user-story-dependencies/~gitbook/image?url=https%3A%2F%2F1282312313-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FSnDqxvUfUkMbScdvMYGA%252Fuploads%252F3EJEhbPpK1yoKrSV0AMe%252Fimage.png%3Falt%3Dmedia%26token%3D0b106fe2-ce84-46b8-973e-79efa4f178e9&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e7e5de6e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://releaseowl.gitbook.io/user-story-dependencies/~gitbook/image?url=https%3A%2F%2F1282312313-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FSnDqxvUfUkMbScdvMYGA%252Fuploads%252Fw06etqXwLoE3B90FtVMZ%252Fimage.png%3Falt%3Dmedia%26token%3D676eef33-bcc8-47dd-8736-72f8f6043d19&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d5bd9bb9&#x26;sv=2" alt=""><figcaption></figcaption></figure>

### Triggering the Message from an External Tool (e.g., Postman) <a href="#triggering-the-message-from-an-external-tool-e.g.-postman" id="triggering-the-message-from-an-external-tool-e.g.-postman"></a>

The **Message Listener** can be triggered from any external application, such as **ALM Rules**, **ALM Webhooks**, or even tools like **Postman**.

**Step 1: Set the Request Type to `POST`**

* In the Postman interface, locate the dropdown menu to the left of the URL input field.
* Click on it and select `POST`. This is a crucial step because you are sending data to the server to trigger an action, which is the standard use case for a `POST` request.

**Step 2: Enter the API Endpoint URL**

```
https://<domain>/webhook/tenant/{tenant}/project/{ProjectID}?secretkey=<secretkey>
```

* <**Domain**> → This will be provided during the ReleaseOwl solution implementation.
* **{Tenant}**  → Replace with your tenant ID.
* **{ProjectID}**  → Replace with your project ID.
* <**Secret Key**> → This will be provided during ReleaseOwl Solution implementation

**Step 3: Configure the Request Body**

This is the most critical part, as the data you send in the body is what ReleaseOwl's Message Listener will read and act upon.

**Request Body (JSON format)**

```
{
  "UserStoryId": "<external-user-story-id>",
  "EventName": "Pipelinemessage",
  "message": {
    "<messageName>": {
    }
  }
}
```

**Field Descriptions**

* **UserStoryId** → This value links the external message to the specific User Story in ReleaseOwl that has an active pipeline running. The pipeline will only proceed if the `userStoryId` in the request body matches the one associated with the waiting pipeline activity.
* **EventName** → A mandatory field that must have the value `"Pipelinemessage"`. This is the non-negotiable field. The Message Listener task is specifically configured to wait for an event with this exact name. Sending any other value will cause the event to be ignored.
* **Message** → An optional object to pass additional details.
  * **MessageName**→ Must match the message name configured in the **Message Listener task** (in the **“Wait for Message”** step).

**Important Note**

When you configure a **Message Listener task** in your pipeline, you specify a **Message Name** in the **“Wait for Message”** step.

* In the JSON payload, replace **\<messageName>** with the **exact, case-sensitive name** you configured in the task.
* This value becomes the **key inside the `message` object**.
* If the names do not match, the pipeline will continue waiting because the event will not be recognized.

<figure><img src="https://releaseowl.gitbook.io/user-story-dependencies/~gitbook/image?url=https%3A%2F%2F1282312313-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FSnDqxvUfUkMbScdvMYGA%252Fuploads%252FgO2UGUk1iuHcAQ56ZYxZ%252Fimage.png%3Falt%3Dmedia%26token%3Dfde3d7b4-b78a-43ac-bcc3-8351c06f3ea9&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ae41388b&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="https://releaseowl.gitbook.io/user-story-dependencies/~gitbook/image?url=https%3A%2F%2F1282312313-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FSnDqxvUfUkMbScdvMYGA%252Fuploads%252F860CYcpQ8gJ9NcUZwVdA%252Fimage.png%3Falt%3Dmedia%26token%3Deabb91d3-15b7-4d21-a34d-f1656f05585f&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=d4bb87e&#x26;sv=2" alt=""><figcaption></figcaption></figure>

**Step 4: Send the Request and Verify**

* Once the URL and the JSON body are correctly configured, click the blue `Send` button in the top right corner of the Postman interface.
* Postman will send the request, and you will see the response in the bottom panel.
*   **Verification**:

    * The expected response is a `200 OK` status code, as shown in the image. This indicates that ReleaseOwl successfully received and processed the request.



    <figure><img src="https://releaseowl.gitbook.io/user-story-dependencies/~gitbook/image?url=https%3A%2F%2F1282312313-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FSnDqxvUfUkMbScdvMYGA%252Fuploads%252FxhUJDbkAHUCA5Cmp6MUr%252Fimage.png%3Falt%3Dmedia%26token%3Dfd5bede7-507a-4886-803a-0b4025d8d2cc&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=3ba81c8d&#x26;sv=2" alt=""><figcaption></figcaption></figure>
*   You can then check the **ReleaseOwl Pipeline Activity** view for the corresponding **User Story**. The **Message Listener** task should have completed, and the pipeline should have moved on to the next step.



    <figure><img src="https://releaseowl.gitbook.io/user-story-dependencies/~gitbook/image?url=https%3A%2F%2F1282312313-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FSnDqxvUfUkMbScdvMYGA%252Fuploads%252FMnFagu5IvboxtiDeMALo%252Fimage.png%3Falt%3Dmedia%26token%3D8e694e4e-fa19-4af7-b0ba-42633a0c8b0c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=626164f5&#x26;sv=2" alt=""><figcaption></figcaption></figure>
