# Update User Story Fields Task

In projects with defined workflows, certain fields must be updated to enable transition from one state to another. The **Update User Story Fields Task** facilitates updating the required fields to ensure successful state transitions and alignment with the external ALM system.

This task operates by:

* Retrieving configured user story fields from the integrated ALM system
* Mapping and updating those fields within the ReleaseOwl user story context
* Ensuring that any changes made in the source system are consistently reflected

It also supports bidirectional consistency by maintaining synchronization between ReleaseOwl and external ALM tools, reducing dependency on manual updates. A **Update User Story Fields Task** can be added as follows:

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### **User Story Field Task Configuration**

| **Field**           | **Description**                                   | **Action to Perform**                                                                                                                                                                                                    |
| ------------------- | ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Name**            | Name of the User Story Field Task                 | Enter a valid name using letters, numbers, underscores (\_) or periods (.) (e.g., _Update\_User\_Story\_Fields\_QA_).                                                                                                    |
| **Description**     | Purpose of the task                               | Provide a clear description of the task, such as updating required user story fields for workflow transitions.                                                                                                           |
| **Assign To**       | Defines who will perform the task                 | <p>Select from the available options: </p><p><strong>User:</strong> Select a specific user responsible for completing the task. </p><p><strong>Role:</strong> Any user with the selected role can complete the task.</p> |
| **ALM Integration** | Integration with external ALM system (e.g., JIRA) | Select the required ALM integration to enable synchronization of user story fields.                                                                                                                                      |
| **Update Fields**   | Fields to be updated in the user story            | Configure the required fields (Custom Field Label, Custom Field ID, Field Type) that must be updated to support workflow state transitions.                                                                              |

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

#### **Update Fields**

The **Field Type** defines how the selected custom field from the ALM system (e.g., JIRA) is handled and updated within the task.

When configuring **Update Fields**, click on **Add** to open the _Add Custom Field_ dialog. Here, you must provide the following details:

* **Custom Field Label:**\
  Specify the display name of the field as defined in JIRA. It will be get into back end call and will get the custom field label
* **Custom Field ID:**\
  The unique identifier of the field in JIRA. This is automatically fetched and mapped by the system.
*   **Field Type:**\
    The field type is automatically determined based on the JIRA field configuration. The following types are supported:

    * **Text:**\
      Use this type when the field accepts free text input. You can enter values directly (for example, _testing 123_), which will be updated in the corresponding JIRA field.

    <figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

    *   **List:**\
        Use this type when the field is a predefined list in JIRA (e.g., _Resolution_ field).

        * In **JIRA Cloud**, the allowed values are automatically fetched and populated by the system.
        * In **JIRA On-Premise**, the allowed values must be provided manually. These values should match the display names of the options configured in JIRA (e.g., Resolution list values).

        <figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

#### **Completing the Update User Story Fields Task**

1. After adding the **Update User Story Fields Task** to the User Story, **save and promote** the User Story.
2. Navigate to the **My Tasks** section.
3. Locate the assigned task and click on **Complete** to open it.

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

4. You can select the Resolution value from the available list configured in **Jira** (either Cloud or On-Premise). Once selected, click on the **Update** button. This action will update the corresponding field in the User Story within Jira.

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

5. In the Pipeline Activity, you can view the details of the **Resolution List** that has been selected and applied.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
