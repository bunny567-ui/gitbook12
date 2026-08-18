# Stop Condition Task

Stops the release pipeline when a condition is met. This task is mainly used in **MTAR (SAP BTP) pipelines**, where the run is driven by Jenkins build inputs — the condition checks the Jenkins input data (build name/number) supplied when the pipeline is triggered, and stops the run if the input is not valid for the stage.

<figure><img src="../../../.gitbook/assets/image (2186).png" alt=""><figcaption></figcaption></figure>

| Field           | Type       | Description                                                                           |
| --------------- | ---------- | ------------------------------------------------------------------------------------- |
| **Name**        | Text       | Task name. Only letters, numbers, underscores (`_`), and periods (`.`) are permitted. |
| **Description** | Text       | Description of what the condition guards (e.g., "Condition for stopping pipeline").   |
| **Condition**   | Expression | The stop condition, evaluated at runtime against the pipeline run context.            |

#### How it works

When the pipeline reaches this task, the condition is evaluated against the run's input data:

* **Condition is true** — the task executes and the pipeline run is **stopped** at this point. Subsequent tasks (e.g., the deployment) do not execute.
* **Condition is false** — the task is passed over and the pipeline **continues** with the next task.
