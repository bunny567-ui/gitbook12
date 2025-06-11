# Types of Tasks

When creating a release pipeline in ReleaseOwl, tasks define the steps to be executed across different stages of the pipeline. Clicking **"Add"** under the **Tasks** section allows you to choose from various predefined task types based on your project requirements.

**Common Task Types (Available for All Project Types)**

* **Approvals** – Configure mandatory approval steps from stakeholders before proceeding.
* **Manual Task** – Add a manual checkpoint requiring user intervention or confirmation.
* **Callout** – Trigger external REST APIs or custom logic using the ReleaseOwl Callout Framework.
* **Test Execution** – Integrate automated test executions into your pipeline.
* **User Story Status Update** – Automatically update linked Jira user stories based on pipeline progress.

**Project-Specific Task Types**

* **Wait for Promotion** – (Only for On-Premise and SAP CPI projects) Pauses pipeline progression until promotion is triggered manually or conditionally.
* **Validation** – (Only for On-Premise and SAP CPI projects) Used to validate deployments through scripts or external checks before moving forward.
* **Deployment** – Varies based on the project type (e.g., SAP ABAP, SAP CPI, API Management). Each project type has its own deployment mechanism configured accordingly.

These task types enable flexible and governed pipeline execution tailored to your SAP and cloud landscape.
