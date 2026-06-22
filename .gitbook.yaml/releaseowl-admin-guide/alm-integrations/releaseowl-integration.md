# ReleaseOwl Integration

The ALM Integrations module supports integration with ReleaseOwl, enabling users to configure and manage ReleaseOwl projects directly through a dedicated integration interface.

#### Configuring a ReleaseOwl Integration

1. Navigate to **ALM Integrations**.
2. Click **Add Integration**.
3. Select **ReleaseOwl** as the external system.
4. Choose the required **Project Workflow Type**:
   * Scrum
   * Kanban
5. Save the configuration.

<figure><img src="../../.gitbook/assets/image (1996).png" alt=""><figcaption></figcaption></figure>

#### Managing Workflow Statuses

The integration setup allows users to configure workflow-specific statuses used within the selected project. Statuses can be mapped by selecting the **Journey\_** **Arrive**  button.

Examples of statuses include:

* To Do
* In Progress
* Completed

Users can add, edit, or remove statuses as required to align with their project workflow.&#x20;

<figure><img src="../../.gitbook/assets/image (1997).png" alt=""><figcaption></figcaption></figure>

#### Managing Work Item Types

The integration setup also supports the configuration of work item types.

Examples of types include:

* Bug
* Task
* Story

Users can maintain these types based on the requirements of the selected workflow.

<figure><img src="../../.gitbook/assets/image (1998).png" alt=""><figcaption></figcaption></figure>

#### Integration Configuration Restrictions

A project can only be associated with one workflow integration configuration at a time.

For example:

* If a project is already configured with a **Scrum** workflow integration, the same project cannot be added again under another ReleaseOwl integration configuration.
* To configure the project with a different workflow setup, the existing integration must first be deleted and then recreated with the desired configuration.

This restriction helps maintain data consistency and prevents duplicate project mappings across multiple workflow configurations.

