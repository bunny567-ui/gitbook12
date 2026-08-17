# Pipeline Tasks

When creating a release pipeline in ReleaseOwl, tasks define the steps to be executed across different stages of the pipeline. Clicking **"Add"** under the **Tasks** section allows you to choose from various predefined task types based on your project requirements.

**Common Task Types (Available for All Project Types)**

* **Approvals** – Configure mandatory approval steps from stakeholders before proceeding.
* **Manual Task** – Add a manual checkpoint requiring user intervention or confirmation.
* **Callout** – Trigger external REST APIs or custom logic using the ReleaseOwl Callout Framework.
* **Test Execution** – Integrate automated test executions into your pipeline.
* **User Story Status Update** – Automatically update linked Jira user stories based on pipeline progress.

#### Project-type-specific task types

In addition to the common types, each project type contributes its own tasks — for example, **Deployment** tasks for the target platform, **Pull Request** and **Merge** tasks for Git-based BTP applications (see _Pull Request Task_), and transport import tasks for SAP On-Premise pipelines. These are described in their respective sections.

Together, these task types enable flexible, governed pipeline execution tailored to your SAP and cloud landscape: approvals and manual checkpoints enforce control, callouts and status updates integrate the surrounding toolchain, and test executions keep quality gates inside the pipeline itself.

