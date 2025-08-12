# Message Listener

The **Message Listener Task** in ReleaseOwl is designed to **wait for specific message events** from an external ALM (Application Lifecycle Management) system and **act upon receiving them** during pipeline execution. It pauses the release pipeline until the expected event or status change is received from the integrated system, ensuring that deployments only proceed when required external conditions are met.

### Prerequisites

Before using the Message Listener Task, make sure that:

* The project has an **external User Story ID** from an ALM system (e.g., Jira, ServiceNow).

<figure><img src="../../../.gitbook/assets/image (1413).png" alt=""><figcaption></figcaption></figure>

* An **ALM integration** is already configured and attached to the project.

<figure><img src="../../../.gitbook/assets/image (1412).png" alt=""><figcaption></figcaption></figure>

### Triggering the Message Listener

You can trigger the Message Listener by sending a **POST** request from a third-party tool such as **Postman**.

* https:///ratesaptms/webhook/tenant/{tenant}/project/{ProjectID}?secretkey=
* Replace `<domain>` with your ReleaseOwl domain.
* Replace `{tenant}`, `{ProjectID}`, and `<secretkey>` with your actual tenant ID, project ID, and secret key.

### **Request Body (JSON format)**

```json
jsonCopyEdit{
  "UserStoryId": "<external-user-story-id>",
  "InitiatedBy": "<initiator-name-or-id>",
  "EventName": "Pipelinemessage",
  "message": {
  "test":{
  "Startdate" : "",
  "action": ""
  }
}
```

{% hint style="info" %}
**Note:** The  **`test`** object name in the `message` section **must match exactly** the name configured in the **"Wait for Message"** step of the Message Listener task.\

{% endhint %}

<figure><img src="../../../.gitbook/assets/image (1415).png" alt=""><figcaption></figcaption></figure>

**Field Descriptions:**

* **UserStoryId** – External User Story ID from your ALM system.
* **InitiatedBy** – The name or ID of the person or system triggering the event.
* **EventName** – Event name that will be matched by the Message Listener (e.g., `"Pipelinemessage"`).
* **message** –  Optional object to pass additional details.
* **test** – Must match the "**Wait for Message**" configuration in the task.
* **Startdate** – Custom field for start date information.
* **action** – Custom field for action description.

### How to Add a Message Listener Task

* Go to your **Project View** in ReleaseOwl.
* Click on **Release Pipelines**.
* Select **Create New Release Pipeline** (or edit an existing pipeline).

<figure><img src="../../../.gitbook/assets/image (1416).png" alt=""><figcaption></figcaption></figure>

* Add an **Approval Task** if required.
* Add the **Message Listener Task**.&#x20;

<figure><img src="../../../.gitbook/assets/image (1418).png" alt=""><figcaption></figcaption></figure>

* In the **Assign Variables** screen, map variables to event message properties using the format:

${resp.\<message-object>.\<property>

* Save the pipeline.

<figure><img src="../../../.gitbook/assets/image (1419).png" alt=""><figcaption></figcaption></figure>

### User Story Promotion

* Promote the User Story  directly in ReleaseOwl.
* Open the **Pipeline Activity** view.

<figure><img src="../../../.gitbook/assets/image (1408).png" alt=""><figcaption></figcaption></figure>

* Locate the **Message Listener** task.
* Click **Send Message** to open the message form and view the event payload details.&#x20;

<figure><img src="../../../.gitbook/assets/image (1407).png" alt=""><figcaption></figcaption></figure>

* Click **Save** the pipeline will **automatically move to the next step**.

<figure><img src="../../../.gitbook/assets/image (1406).png" alt=""><figcaption></figcaption></figure>
