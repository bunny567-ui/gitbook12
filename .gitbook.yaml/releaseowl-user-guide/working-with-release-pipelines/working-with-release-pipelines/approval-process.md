# Approval Process

If the deployment needs any **prior approval**, then the user has to add an **Approval Task** **before** the **Deployment Task** while creating the Release Pipeline. An Approval Task can be added as follows:\


<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

**Fill in the required details:**

| **Field**                      | **Description**                                                                                                                                                                      |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Name**                       | Enter any name of your choice for the approval task being created.                                                                                                                   |
| **Assign To**                  | **User** – The approver (user) can be selected from the available list of users for approving the task. **Role** – The task can be approved by any user with the selected user role. |
| **Message**                    | Any message that is to be conveyed to the task approver can be mentioned here.                                                                                                       |
| **Story Assignee**             | The task will be assigned to the user who is the assignee of the related story in the pipeline.                                                                                      |
| **Disable Email Notification** | Users will not receive the approval email link but will get a notification only about the final status (approved/rejected).                                                          |

{% hint style="info" %}
**Note:** The Approval Tasks assigned to a user appear under his/her **My Tasks** section upon logging in to **ReleaseOwl**. The user can either **accept** or **reject**.
{% endhint %}
