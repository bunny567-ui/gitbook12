# Create Release Package with Transports

Release Package is a collection of one or more user stories or transports that are validated and deployed as a single entity.

To create a release package:

1\. Go to **Release** and click **Release Packages.**

2\. The following screen is displayed\


<figure><img src="https://www.docs.releaseowl.com/assets/img/create-release-package-with-user-stories-1.jpg" alt=""><figcaption></figcaption></figure>

3\. Click **Create New Release Package.**

The following screen is displayed for an on-premise project:

**Note:** Transports option can be seen only for On-Premise Projects.\
\


<figure><img src="https://www.docs.releaseowl.com/assets/img/create-release-package-with-user-stories-4.jpg" alt=""><figcaption></figcaption></figure>

4\. Enter the name of the new release package in **Name** and give a **Description.**

5\. You can select the Release Pipeline which you want to trigger for deployment by promoting the release package.

6\. By default, the Promote from (Stage) will be Dev. The stages that are added to a Release Pipeline that which is associated with the Release Package appears in the dropdown.

If you add QA, UAT and Prod stages in the release pipeline, then QA and UAT are shown along with the option Dev in the Promote from (Stage) dropdown.

Prod will **not** be shown as there is no further stage to which the user stories can be promoted as it is the final stage.

7\. Clicking **Add Transports for Promotion,** will add transports that are not part of any other release package and are ready to be promoted from the selected Promote from (Stage).

8\. Click **Add Transport** and click the required transports from the displayed list. By this, you can select all the transports which you want to import at once using the release package which are readily available in the Promote from (Stage).

9\. Selecting **Auto Sequence** option will enable the import of transports added using **Add Transport** in the order they are available in the STMS Import queue.

10\. Click **Save.**

11\. You can customize the columns seen in the **Create/Edit Release Package** screen by clicking the Settings Gear icon next to **Add Transport / Add User Story** option.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/create-release-package-with-user-stories-5.jpg" alt=""><figcaption></figcaption></figure>

12\. Once created, you can see the newly created release package in the Release Package page.
