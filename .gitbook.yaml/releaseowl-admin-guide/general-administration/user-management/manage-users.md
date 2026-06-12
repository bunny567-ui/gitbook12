# Manage Users

This functionality allows administrators to effectively oversee and control user access within the system.

### License Overview

Provides insights into the number of licenses across the following categories:

* User License&#x20;
* Admin Licenses

Displays the total, used, and available licenses, facilitating efficient resource management.

<figure><img src="../../../.gitbook/assets/image (1877).png" alt=""><figcaption></figcaption></figure>

### User Details

Lists all registered users along with the following details:

* **User Type**: Specifies whether the user is an **Admin** or **Standard User**.

<figure><img src="../../../.gitbook/assets/image (1878).png" alt=""><figcaption></figcaption></figure>

#### Create User

This section explains how to create a new user and configure the required roles, environments, and project access.

To create a new user:

1. Navigate to the **Users** section.
2. Click the **Create** button to add a new user.

<figure><img src="../../../.gitbook/assets/image (1879).png" alt=""><figcaption></figcaption></figure>

3. The **User Creation form** will open. Enter the required user details:
   * **First Name**
   * **Last Name**
   * **Email ID**
   * **User Type**

**User Type** : The **User Type** determines the level of access granted to the user.

1. **Tenant Admin**&#x20;

Users assigned the **Tenant Admin** role have administrative privileges across the tenant. Tenant Admins can perform all actions available under the **Administration** menu, including:

* Creating and managing users
* Creating and managing projects
* Configuring and editing environments
* Managing tenant-level settings and configurations
* Performing other administrative operations available within the platform

2. **User**

Users assigned the **User** role have access only to the projects to which they are assigned. Based on their project permissions, they can:

* Access assigned projects
* View and work on project-related tasks
* Review and approve tasks&#x20;
* Perform actions permitted within their assigned role and project scope

<figure><img src="../../../.gitbook/assets/image (1948).png" alt=""><figcaption></figcaption></figure>

4. Click the **Create** button to save the user.

<figure><img src="../../../.gitbook/assets/image (1947).png" alt=""><figcaption></figcaption></figure>

5. Once the user is created, the newly created user will appear in the **Users Details** list.

<figure><img src="../../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Managing User Details

1. Click the **Arrow ( > )** icon next to the user to open the **User Details** page.

<figure><img src="../../../.gitbook/assets/image (1880).png" alt=""><figcaption></figcaption></figure>

2. In the **Projects** section, users can view and manage all projects associated with the selected user.
3. To add projects to the user, click the **+ Add** button in the **Projects** section.

<figure><img src="../../../.gitbook/assets/image (1882).png" alt=""><figcaption></figcaption></figure>

4. A popup window will appear displaying the list of existing projects.
5. Select the required project(s) to associate with the user.

<figure><img src="../../../.gitbook/assets/image (1885).png" alt=""><figcaption></figcaption></figure>

4. The selected projects will be displayed in the Projects table.
5. Enable the **Project Admin** checkbox if the user should have administrative access for the selected project.

<figure><img src="../../../.gitbook/assets/image (1883).png" alt=""><figcaption></figcaption></figure>



6. To manage project-specific roles and environment permissions, click the **Actions** button corresponding to the project.
7. Select **Edit** to open the configuration page.

<figure><img src="../../../.gitbook/assets/image (1884).png" alt=""><figcaption></figcaption></figure>

8. In the **Edit** page, users can:
   * Assign the required roles
   * Grant deployment permissions for selected environments based on project requirements

<figure><img src="../../../.gitbook/assets/image (1886).png" alt=""><figcaption></figcaption></figure>

### Lock&#x20;

The **Lock** feature allows administrators to control access to the system for selected users. When a user is locked, they are prevented from logging in or performing any operations until their access is restored.

**To perform the Lock operation:**

1. Select one or more users by clicking the checkbox beside their names.
2. Click the **Lock** button.
3. The selected users will be locked and denied access to the system until unlocked.

<figure><img src="../../../.gitbook/assets/image (11) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Unlock**

The **Unlock** feature allows administrators to restore access to users who were previously locked. Once unlocked, users can log in and resume their activities in the system.

**To perform the Unlock operation:**

1. Select one or more users by clicking the checkbox beside their names.
2. Click the **Unlock** button.&#x20;
3. The selected users will regain access to the system.

<figure><img src="../../../.gitbook/assets/image (12) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Show**

It allows users to filter and view the user list based on their role or status, such as Admin, User or Locked Users.

<figure><img src="../../../.gitbook/assets/image (13) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Filter**

It is used to search for users based on their **name** or **email ID**.

<figure><img src="../../../.gitbook/assets/image (14) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Import**&#x20;

The **Import** option allows administrators to import user and role information into the system.

1. To perform an import, click the **Import** button available on the screen.
2.  When the **Import** button is clicked, the following options are displayed:

    * **Import Users**
    * **Import Projects and Roles**



<figure><img src="../../../.gitbook/assets/image (1887).png" alt=""><figcaption></figcaption></figure>

3. Select the appropriate option based on the type of data you want to import.
4. In the **Import Details** section, click the **Browse** button to select the required file from your local system.
5. After selecting the file, proceed with the import process.
6. Before importing the data, ensure that the file follows the required format and import procedure.
7. Click the **Download** button to download the sample template and detailed import instructions.
8. Prepare the import file according to the provided template to avoid validation or import errors.

<figure><img src="../../../.gitbook/assets/image (16) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Download**&#x20;

The **Download** option provides sample templates that help users prepare the correct file format for importing data into the system.

1. When you click the **Download** button, the following template options are displayed:
   * **User Template**
   * **Projects/Roles Template**
2. These templates act as reference samples that define the required structure and format for the import file.
3. Download the appropriate template based on the type of data you want to import.
4. Use the downloaded template to prepare your Excel file by following the same data structure and format.
5. Preparing the file according to the provided template helps avoid validation issues and import errors during the import process.

<figure><img src="../../../.gitbook/assets/image (17) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

