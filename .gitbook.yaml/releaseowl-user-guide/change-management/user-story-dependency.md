# User Story Dependency

ReleaseOwl includes a **User Story Dependency Check** as part of the validation process. This feature ensures that user stories follow the correct execution sequence during deployments — helping avoid conflicts, blockers, or missed dependencies.

To enable this functionality:

1. Define the **Landscape Stages** (e.g., DEV → QA → PROD).
2. Map each stage to its corresponding target system using **Landscape Stage System Mapping**.
3. Navigate to the Release Pipeline and open the relevant stage containing the Validation Task.
4. In the task configuration, enable **User Story Dependency Check**.

<figure><img src="../../.gitbook/assets/image (1301).png" alt=""><figcaption></figcaption></figure>

5. The **Validation Report** includes a **User Story Dependency Check** tab, which displays the status as either **Success** or **Failure** based on the sequence validation of dependent user stories.

<figure><img src="../../.gitbook/assets/image (1302).png" alt=""><figcaption></figcaption></figure>

### Managing User Story Dependencies

To add or remove dependent user stories:

1. Open the desired user story and click on the **Dependencies** option.

<figure><img src="../../.gitbook/assets/image (1303).png" alt=""><figcaption></figcaption></figure>

2. Use the dropdown to select either **Depends On** or **Dependent On**, based on the type of relationship you want to define.

* **Depends On** – if the current user story depends on others.
* **Depended On** – if other user stories depend on the current one.

<figure><img src="../../.gitbook/assets/image (1334).png" alt=""><figcaption></figcaption></figure>

3. Click the **+ Add** button.

<figure><img src="../../.gitbook/assets/image (1335).png" alt=""><figcaption></figcaption></figure>

4. Select the required **project** and **active sprint**.

<figure><img src="../../.gitbook/assets/image (1305).png" alt=""><figcaption></figcaption></figure>

5. Check the checkbox next to the user story ID(s) you want to add as dependencies.

<figure><img src="../../.gitbook/assets/image (1306).png" alt=""><figcaption></figcaption></figure>

6. Click **Add** to confirm the selection.

<figure><img src="../../.gitbook/assets/image (1307).png" alt=""><figcaption></figcaption></figure>

7. Click the **Save** button to apply the changes.

<figure><img src="../../.gitbook/assets/image (1308).png" alt=""><figcaption></figcaption></figure>

8. When you select **Depended On**, the system displays a list of user stories that are directly dependent on the current one.

<figure><img src="../../.gitbook/assets/image (1336).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
**Note:** Dependencies cannot be added to user stories that are in _In-Progress_ status.
{% endhint %}

#### **User Story Dependency Validation Rules in the Validation Task**

The **Validation Task** has been enhanced to handle various scenarios involving user story dependencies based on **Landscape Stage Mapping** and **project relationships**. Below are the key validation rules and the corresponding exception behaviors:

1. **Multiple Target Stages for the Same System (Declared in Landscape Stage Mapping)**

* If **multiple target stages** are mapped to the **same system** for a given landscape:
* The Validation Task expects the dependent user story to be deployed in **all mapped target system**.
*   If the deployment is **missing in any one** of the target systems, the **validation fails**.

    <figure><img src="../../.gitbook/assets/image (1309).png" alt=""><figcaption></figcaption></figure>

2. **Dependent User Story in a Different Project (No Landscape Stage Mapping)**

* If the dependent user story belongs to a **different project** and **no Landscape Stage Mapping** is defined:
* The **Validation Task throws an exception**, as it cannot determine the corresponding target system or stage to validate the dependency.

3. **Dependent User Story in the Same Project (No Landscape Stage Mapping)**

* If the dependent user story belongs to the **same project** and **no Landscape Stage Mapping** is defined:
* The **current target stage** is used to validate whether the dependent user story has already been deployed.
* **No exception is raised** in this case, even without a defined landscape stage mapping.

### Cyclic Dependency

When managing user story dependencies in **ReleaseOwl**, it is important to maintain a clear and logical order of execution between user stories. One common validation error that users may encounter is related to **cyclic dependencies**. A **cyclic dependency** occurs when user stories depend on each other in a circular fashion. For example:

* **User Story A** depends on **User Story B**
* **User Story B** (directly or indirectly) depends on **User Story A.**

When you attempt to add a dependency that results in a cyclic relationship, ReleaseOwl throws an **error** and **blocks the dependency creation**.

<figure><img src="../../.gitbook/assets/image (1310).png" alt=""><figcaption></figcaption></figure>
