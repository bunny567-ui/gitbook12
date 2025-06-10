# Settings

The settings section consists of two components: component management and freeze period management.

## Component Management

The Component Management section helps in organizing and managing software components used in ReleaseOwl workflows.

1. Navigate to **Settings** and select **Components**.
2. Click on the **Create** button to add a new component.

<figure><img src="../../.gitbook/assets/image (8) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Provide the **Component Name** and a brief **Description**.
4. Click **Save** to create the component.

<figure><img src="../../.gitbook/assets/image (9) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

5. You can also use the **default components** provided by ReleaseOwl without creating custom components.

<figure><img src="../../.gitbook/assets/image (10) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Freeze Period Management

The Freeze Period Management feature allows you to define timeframes during which deployments or changes are restricted, ensuring stability during critical business operations.

1. Navigate to **Settings** and select **Freeze Period**.

<figure><img src="../../.gitbook/assets/image (12) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Click on **Create Freeze Period**.

<figure><img src="../../.gitbook/assets/image (11) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Provide the **Name**, **Description**, **Start Date**, and **End Date**.
4. Enable the freeze period by selecting the **checkbox**.
5. Click **Save** to create the freeze period.

<figure><img src="../../.gitbook/assets/image (14) (1) (1).png" alt=""><figcaption></figcaption></figure>

6. Once created, the freeze period will appear in the list of existing freeze periods.

<figure><img src="../../.gitbook/assets/image (15) (1) (1).png" alt=""><figcaption></figcaption></figure>

**To assign environments to a freeze period:**

1. Click on the **Actions** button next to the  created freeze period and select **Edit**.

<figure><img src="../../.gitbook/assets/image (16) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. You will go to the freeze period configuration screen.
3. Scroll down to the **Environments** section and click on the **Add** button.
4. Select the environments you want to associate with this freeze period.

<figure><img src="../../.gitbook/assets/image (17) (1).png" alt=""><figcaption></figcaption></figure>

5. Click the **Save** button to apply the changes.

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

#### Waiting Releases

When a **freeze period** is active in ReleaseOwl, any releases scheduled for deployment to environments included in the freeze will be **put on hold**.

**To view and manage waiting releases:**

1. Click on the **Actions** button next to the created freeze period.
2. Select **Waiting Releases** from the menu.
3. A pop-up window will appear showing the releases that have been **paused** due to the freeze period.
4. Click on the **Resume** button to resume the deployment.

<figure><img src="../../.gitbook/assets/image (1183).png" alt=""><figcaption></figcaption></figure>
