# Create Release Package with User Stories

Release Package is a collection of one or more user stories or transports that are validated and deployed as a single entity.

### To create a release package:

1\. Go to **Release** and click **Release Packages.**

2\. The following screen is displayed\


<figure><img src="../../.gitbook/assets/image (1032).png" alt=""><figcaption></figcaption></figure>

3\. Click **Create New Release Package.**

The following screen is displayed for an Integration Suite (CPI) project:

**Note:** You can create a Release Package with only User Stories for an SAP Integration Suite project.\


<figure><img src="../../.gitbook/assets/image (1031).png" alt=""><figcaption></figcaption></figure>

4\. Enter the name of the new release package in **Name** and give a **Description.**

5\. You can select the Release Pipeline which you want to trigger for deployment by promoting the release package.

6\. By default, the Promote from (Stage) will be Dev. The stages that are added to a Release Pipeline that which is associated with the Release Package appears in the dropdown.

If you add QA, UAT and Prod stages in the release pipeline, then QA and UAT are shown along with the option Dev in the Promote from (Stage) dropdown.

Prod will **not** be shown as there is no further stage to which the user stories can be promoted as it is the final stage.

7\. Clicking **Add Stories for Promotion,** will add user stories that are not part of any other release package and are ready to be promoted from the selected Promote from (Stage).

8\. Click **Add User Story** and click the required user stories from the displayed list. By this, you can select all the user stories which you want to promote at once using the release package which are readily available in the Promote from (Stage).

9\. Click **Save.**

10\. You can customize the columns seen in the **Create/Edit Release Package** screen by clicking the Settings Gear icon next to **Add Transport / Add User Story** option.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/create-release-package-with-user-stories-5.jpg" alt=""><figcaption></figcaption></figure>

11\. Once created, you can see the newly created release package in the Release Package page.
