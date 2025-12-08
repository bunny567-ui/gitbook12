# Abortion and Promotion via External Tools

This section explains how to perform **User Story Abortion** and **User Story Promotion** in ReleaseOwl using external tools such as **Postman or Jira**. These API-based operations enable external systems like **Jira** or other CI/CD tools to trigger user story lifecycle events in ReleaseOwl automatically.

#### Prerequisites

Before triggering user story abortion or promotion from external systems, ensure the following:

1. An **ALM integration** is already configured and attached to the project.&#x20;

<figure><img src="../../../.gitbook/assets/image (1592).png" alt=""><figcaption></figcaption></figure>

2. The project has an **external User Story ID** from an ALM system (e.g., Jira, ServiceNow).

<figure><img src="../../../.gitbook/assets/image (1593).png" alt=""><figcaption></figcaption></figure>

3. The **user story** is attached to a **valid release pipeline** within ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### User Story Abortion&#x20;

The **User Story Abortion** event is used to abort a specific user story from an external system. This can be triggered through a webhook or API request.

#### Triggering the Message from an External Tool <a href="#triggering-the-message-from-an-external-tool-e.g.-postman" id="triggering-the-message-from-an-external-tool-e.g.-postman"></a>

The User Story Abortion can be triggered from any external application, such as **ALM Rules**, **ALM Webhooks**, or even tools like **Postman**.

**Step 1: Set the Request Type to `POST`**

* In the Postman interface, locate the dropdown menu to the left of the URL input field.
* Click on it and select `POST`. This is a crucial step because you are sending data to the server to trigger an action, which is the standard use case for a `POST` request.

**Step 2: Enter the API Endpoint URL**

```
https://<domain>/webhook/tenant/{tenant}/project/{ProjectID}?secretkey=<secretkey>
```

* <**Domain**> → This will be provided during the ReleaseOwl solution implementation.
* **{Tenant}** → Replace with your tenant ID.
* **{ProjectID}** → Replace with your project ID.
* <**Secret Key**> → This will be provided during ReleaseOwl Solution implementation

**Step 3: Configure the Request Body**

This is the most critical part, as the data included in the request body is what ReleaseOwl reads and processes to perform the corresponding user story action.

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

**Request Body (JSON format)**

```
  {
  userStoryId: <external-user-story-id>,
  eventName: usAbort,
  initiatedBy: <user-email-id>,
  abortMsg: Aborted due to failed validation or manual interruption 
  }
    
```

**Key Fields**

* `userStoryId`: Identifier of the linked user story.
* `eventName`: Must be `"usAbort"`.
* `initiatedBy`: Email of the user performing the abortion.
* `abortMsg`:  Reason for abortion.

**System Action:**\
The user story pipeline stops execution, and the status updates to _Aborted_ in ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### User Story Promotion

The **User Story Promotion** event is used to promote a user story to the next stage in the pipeline through an external system. This ensures automation continuity between ALM tools and ReleaseOwl pipelines.

#### Triggering the Promotion from an External Tool (e.g., Postman)

User Story Promotion can also be triggered from tools such as **ALM Rules**, **ALM Webhooks**, or **Postman**.

**Step 1: Set the Request Type to POST**

In Postman, click the dropdown beside the request URL and select **POST**. This allows the system to send the promotion request to ReleaseOwl.

**Step 2: Enter the API Endpoint URL**

```
https://<domain>/webhook/tenant/{tenant}/project/{ProjectID}?secretkey=<secretkey>
```

* <**Domain**> → This will be provided during the ReleaseOwl solution implementation.
* **{Tenant}** → Replace with your tenant ID.
* **{ProjectID}** → Replace with your project ID.
* <**Secret Key**> → This will be provided during ReleaseOwl Solution implementation

**Step 3: Configure the Request Body**

```json
{
  "userStoryId": "<external-user-story-id>",
  "eventName": "usPromotion",
  "initiatedBy": "<user-email-id>"
}
```

**Field Descriptions:**

* **userStoryId** → External user story identifier (e.g., from Jira).
* **eventName** → Must be `"usPromotion"` to trigger the promotion event.
* **initiatedBy** → Email ID of the user initiating the promotion.

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

**System Action:**\
The user story pipeline advances to the next stage as defined in the release pipeline, and the user story status is updated accordingly in ReleaseOwl.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
