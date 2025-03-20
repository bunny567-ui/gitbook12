# gCTS

**gCTS (Git-enabled Change and Transport System)** is an offering from SAP that allows us to manage ABAP (Advanced Business Application Programming) change and transport management processes using Git as an external version management system. By integrating Git with the traditional SAP transport system, gCTS enables developers to leverage Git's powerful version control capabilities, branching strategies, and collaboration features in the context of SAP ABAP development.

## **Key Features**

1. **Git Integration:** gCTS integrates Git repositories with SAP systems, allowing ABAP developers to store their source code, configurations, and other development artifacts in Git repositories.
2. **Version Control:** Developers can take advantage of Git's version control features, such as branching, merging, and code reviews, to manage ABAP source code changes more efficiently.
3. **Continuous Integration and Delivery (CI/CD):** By using Git and gCTS, SAP customers can set up CI/CD pipelines for ABAP development. This enables automation of testing, deployment, and release processes, leading to faster and more reliable software delivery.
4. **Collaboration:** Developers can collaborate more effectively by using Git's collaboration features, such as pull requests and code reviews, to review and discuss code changes before they are merged into the main codebase.
5. **Traceability and Auditing:** gCTS provides traceability and auditing capabilities, allowing organizations to track changes made to the SAP systems and ensuring compliance with regulatory requirements.

## **gCTS Integration with ReleaseOwl**

\
The integration of **gCTS** (Git-enabled Change and Transport System) with ReleaseOwl is a powerful combination for SAP customers. By integrating gCTS with ReleaseOwl, organizations can leverage the functionalities of Git repositories and establish robust Continuous Integration and Continuous Delivery (CI/CD) processes for their **ABAP** (Advanced Business Application Programming) development. The integration of **gCTS** with **ReleaseOwl** offers a streamlined and efficient approach to managing **ABAP** development, enabling organizations to deliver high-quality **SAP** applications faster, with reduced risks, and improved collaboration among team members. To **enable** **gCTS** we require a **Git platform host**, an **ABAP** **system** in which code will be developed, and a **CI server** (which is optional) which can be used to automate development cycle. Below are the prerequisites which are required to **enable** **gCTS** for **ABAP** system:\


* An **SAP S/4 HANA 1909** or **2022** system
* An **SAP** **machine** (with **version 11** or **higher**) or comparable **JRE**
* Import relevant **SAP Central note** and based on **SP level**
* Create **gCTS** related **working directories** at **OS** level.

Once the prerequisites are met and the **ABAP** system is ready, you can proceed with the **configuration** which is of 3 steps:

1. **gCTS configuration** on **ABAP system**
2. **Git enablement**
3. **CI/CD pipeline configuration in ReleaseOwl**

Perform the below steps in the ABAP system to complete the gCTS configuration.\


* Validate required **SAP notes** are
* **Authorizations**
* Validate **required ports** are
* **gCTS Fiori UI enablement**
* Set **parameters, Initialize systems.**

**Systems in use** here to **guide** the **user** the **steps involved -**

* **Access** to either **GitHub** or **BitBucket**
* **Access** to the **gCTS** environment of **SAP** (**S4 2022**). Here – **S4D** (main **Dev** system), **S4Q** (**QA** system) and **S4V** (**virtual** **system** for **production**).
* Each **package** should be **linked** to one **repository**.

### **Steps** involved:

* Create a **new** **repository** in the **GITHub** (here- **ZKRK\_GCTS\_SALES**).
* Open **gCTS** environment for the **SAP** using the **Fiori** app **URL** (use **SAP gCTS ABAP** system **credentials** to login).

A blank screen is displayed by default.

![](<../../.gitbook/assets/image (352).png>)\
\
Search for **gcts**. Select the option **Git-enabled CTS – Manage Repositories**.\
\
![](<../../.gitbook/assets/image (394).png>)\
\
Already **existing** **repositories** that are **linked** to the **gCTS** environment in use are listed.\
\
![](<../../.gitbook/assets/image (351).png>)\
\
Click **Create** to create a repository.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-4.jpg)\
\
Fill the required details as follows:\
\


<figure><img src="../../.gitbook/assets/image (350).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (393).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (395).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (392).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (391).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (390).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (389).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (388).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://www.docs.releaseowl.com/assets/img/gcts-3.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://www.docs.releaseowl.com/assets/img/gcts-2.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="https://www.docs.releaseowl.com/assets/img/gcts-1.jpg" alt=""><figcaption></figcaption></figure>

| **URL**         | Enter the **URL** of the **GIT** **repository** that you want to link with the **SAP gCTS** environment.                                                                                                                                                                                   |   |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | - |
| **Description** | Relevant description can be entered, or the default description text can be left as is.                                                                                                                                                                                                    |   |
| **vSID**        | Enter any name of your choice. A **virtual** **system** gets created in the **Transport Route** with the name entered against **vSID** field. **Note**: For every **unique** **GIT** **repository**, there should be a **virtual system Transport** **Route** in **SAP gCTS** environment. |   |
| **Role**        | Select **Developer**                                                                                                                                                                                                                                                                       |   |
| **Type**        | Select **GitHub**                                                                                                                                                                                                                                                                          |   |
| **Visibility**  | Select **Private**                                                                                                                                                                                                                                                                         |   |

\
\
\
\
Click on **Save**. A new repository gets created.\
\
**Note**:\


<figure><img src="https://www.docs.releaseowl.com/assets/img/gcts-5.jpg" alt=""><figcaption></figcaption></figure>

1. When a new repository is created, a **new** **transport** **layer** gets created. This can be found in the parameters that created by default upon creating a repository under the **Configuration** The Transport **Layer** name will be **Z\<vSID>**
2. This **Transport Layer** will also be seen in the **Transport** **Routes** screen in **SAP gCTS system**

\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-6.jpg)\
\
3\) To **clone** the **repository, authorisation** is required. Navigate to the **Configuration** tab and **add** **two** **parameters** for the repository created.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-7.jpg)\
\
Click **Create**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-8.jpg)\
\
Select the **configuration** **parameter** **CLIENT\_VCS\_AUTH\_USER** And enter the **GITHub user id** against the field **Value** and **Save** the changes.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-9.jpg)\
\
**Add** the **second parameter** by name **CLIENT\_VCS\_AUTH\_TOKEN** as follows and **save** the changes:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-10.jpg)\
\
The **two** newly created **configuration** **parameters** are shown as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-11.jpg)\
\
4\) Create **branches (dev** from **main** branch and **qa** from **dev** branc&#x68;**)** as required in the **GITHub** for the **repository** created as shown below:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-12.jpg)\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-13.jpg)\
\
5\) Navigate to the **SAP gCTS** application and **clone** the **ABAP** **system** repository with that in **GITHub** as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-14.jpg)\
\
The **local** **copy** of **GITHub** **repository** gets **cloned** to the **local SAP ABAP** system. The **latest** **commits** to the **repository** can be viewed.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-15.jpg)\
\
6\) For every repository, there will be **one active branch** and in **SAP gCTS** system, it is the **main** **branch** by **default**. Any changes done in the **SAP**, will be **saved** to the **main** Based on the requirement, the **active** **branch** can be set as follows (here – the **active** **branch** is **set** to **dev** which is otherwise **main** by **default**):\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-16.jpg)\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-17.jpg)\
\
7\) Create the **same** **package** in **SAP ABAP** system as in the **SAP gCTS** environment as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-18.jpg)\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-19.jpg)\
\
8\) Enter all the required details and **ensure** to **select** the **Transport** **Layer** that gets **created** while **creating** the **repository** in the **SAP gCTS** environment and **Save** the changes.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-20.jpg)\
\
9\) The system will prompt the user to **create** a **transport request**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-21.jpg)\
\
**Create** a **new** **transport request**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-22.jpg)\
\
Click **Save**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-23.jpg)\
\
The **package** gets **created**.\
\
10\) Now, **create** a **class** as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-24.jpg)\
\
Enter all the required details as shown:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-25.jpg)\
\
**Choose** appropriate **package** and **Save** the changes.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-26.jpg)\
\
The system will prompt the user to **associate** the **package** with a **transport request**. Select the **newly** **created** **transport request** and **save** the changes.\
\
**11) Make** required **changes** to the **class**, **save** them, and **activate** the **objects**\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-27.jpg)\
\
**12) Release** the **task** associated with the **transport request** in use.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-28.jpg)\
\
**13) Register** the **Transport Manager Credential** in **Credential Manager** section in **ReleaseOwl** as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-29.jpg)\
\
**14) Register** the **Transport Domain Controller** in **ReleaseOwl** application as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-30.jpg)\
\
**Note**: Clicking **Get Systems** will fetch the details of **all** the **systems** available in the specific **system landscape**. Also, the **newly** **created** **SAP system ID - RKS** is **seen** in this screen.\
\
**15) Register** the **GITHub** credential in the **Credential** **Manager**\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-31.jpg)\
\
**Note: GITHub APIs** can be **accessed** only via **Personal Access Tokens** and **not** by **username** and **password.** For further information on the **Personal Access Tokens, please refer to the link -** [**https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token**](https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)\
\
**16) Register** the **dev** **ABAP** **system** in **ReleaseOwl** as follows: **Note:** Ensure to select the required **role** as **Development** and **credential** for each **repository.** Also, **SAP system** should be **SAP Development system** (here **S4D**) and **not** the **gCTS Virtual System (RKD)** **.**\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-32.jpg)\
\
17\) Set-up **QA gCTS** system for **pushing** the **changes** from **Dev** system to **QA** Login to **QA SAP gCTS** system with **SAP ABAP** credentials.\
\
18\) **Create** a **repository** with **same** **name** as that **created** in **dev**\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-33.jpg)\
\
Fill in the required details as follows:\
\


| **URL**         | Enter the **URL** of the **GIT** **repository** that you want to link with the **SAP gCTS** environment. |
| --------------- | -------------------------------------------------------------------------------------------------------- |
| **Description** | Relevant description can be entered, or the default description text can be left as is.                  |
| **vSID**        | Enter the name of the **virtual** **system** that was created in the **SAP gCTS** **Dev** environment.   |
| **Role**        | Select **Provided**                                                                                      |
| **Type**        | Select **GitHub**                                                                                        |
| **Visibility**  | Select **Private**                                                                                       |

\
19\) **Add** the **two configuration parameters** as done in the **Dev** environment **- CLIENT\_VCS\_AUTH\_USER** and CLIENT\_VCS\_AUTH\_TOKEN.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-34.jpg)\
\
20\) **Clone** the repository created in **SAP gCTS** environment to the **ABAP**\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-35.jpg)\
\
21\) **Switch** the **active branch** to **qa** from the **main branch**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-35.jpg)\
\
22\) **Register** the **same** **ABAP** **system** in **ReleaseOwl** for **QA**. Login to **ReleaseOwl** and **add** an **ABAP system** as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-36.jpg)\
\
**Note:** Ensure to select the required **role** as **Provided** and appropriate **credential** for each **repository.** Also, **SAP system** should be **SAP Development system** (here **S4Q**) and **not** the **gCTS Virtual System (RKS)** **.**\
\
23\) Ensure to **add** the appropriate **SAP ABAP environment** in the **project** that is in use in **ReleaseOwl** as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-37.jpg)\
\
24\) **Create** a **user story** in **ReleaseOwl.**\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-38.jpg)\
\
**25) Add** the **transport** **request** to the **user** **story** and **save** the **changes**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-39.jpg)\
\
**26) Release** the **transport** **request** from **ReleaseOwl**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-40.jpg)\
\
27\) The **associated** **commits** of the **transport** **request** can be **viewed** once the **transport** **request** is **released**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-41.jpg)\
\
28\) In **GITHub**, on **refreshing** the **repository**, **all** the **new** **objects** get **loaded** in the **dev**\
\
**Note:** Whenever a **transport request** which is **associated** with **gCTS** is **released**, all the **changes** will be **pushed** to **GIT**.\
\
29\) The **changes** will **not** be **pushed** to **qa** **unless** you **import** the **transport** **request** to **qa**.\
\
30\) **Create** a **release** **pipeline** in **ReleaseOwl** and ensure to **add** a **deployment** **task** as follows and **save** the **changes**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-42.jpg)\
\
31\) There are other few Tasks in pipeline which can be used based on requirement.

1.
   1. gCTS Merge Task:
      1. This Task is used when a hotfix changes need to be merged to other development branches
      2. After a major release of a project, the changes from the master branch can be merged to other development branches.

![](https://www.docs.releaseowl.com/assets/img/gcts-43.jpg)\
\


2. gCTS Activate
   1. This Task is used when a system needs to be updated to latest commit of the associated branch.

![](https://www.docs.releaseowl.com/assets/img/gcts-44.jpg)\
\


3. gCTS Switch:
   1. This task is used when a branch associated to the system needs to be changed to another branch for e.g. if a UAT system is pointing to “QA” branch and a hotfix needs to be verified then this task can used to switch to “Hotfix” branch.

\
![](https://www.docs.releaseowl.com/assets/img/gcts-45.jpg)\
\
32\) **Associate** the **release** **pipeline** created with the **project** **in** **use** under **Project** **Settings** as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-46.jpg)\
\
33\) **Grant** **permission** to the **user** for **deploying** in the required **environments** under **Project** **Settings** > **Users** > **Security**, **without** which the **user** will **not** be able to **deploy** the **changes** to the required **environments**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-47.jpg)\
\
34\) Now, **promote** the **user story** to **qa** as follows:\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-48.jpg)\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-49.jpg)\
\
Click **OK**. **Check** for any **approval** **tasks** that are in **waiting** status for **deployment** to take place.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-50.jpg)\
\
35\) Once the **approver** **approves** the **task**, the **deployment** **starts**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-51.jpg)\
\
36\) Click on **Go to Pipeline Activity**.\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-52.jpg)\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-53.jpg)\
\
37\) **Check** the **Deployment Logs.**\
\
<img src="https://www.docs.releaseowl.com/assets/img/gcts-54.jpg" alt="" data-size="original">\
\
![](https://www.docs.releaseowl.com/assets/img/gcts-55.jpg)\
\
38\) Once the **deployment** is **successful**, check whether the **changes** are **pushed** to the **qa** branch in the **GIT** repository.\
\
<img src="../../.gitbook/assets/image (353).png" alt="" data-size="original">\
\
**Login** to the **SAP** **gCTS** and **check** whether the **latest** **commits** are **available** in **QA**.\
\
39\) Now **login** to **S4Q (QA) ABAP** For the **very first transport** that is **released** from **ReleaseOwl**; the **package**, **class** and **objects** – **all** of them get **pushed** to **QA ABAP** system. For the **subsequent** **transports** **released**, the **changes** done to the **objects** are **pushed** to **SAP QA gCTS** **Fiori** and **ABAP** systems.

<figure><img src="https://www.docs.releaseowl.com/assets/img/gcts-56.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** **Without** **ReleaseOwl** in place, the **changes** **pushed** to **SAP QA gCTS Fiori** are to be **manually** **pulled** to **SAP ABAP** system in **QA**. **With** **ReleaseOwl**, **once** the **transport** **associated** with the **repository** **changes** in **SAP Dev gCTS** **Fiori** is **released**, it **automatically** takes care of **pushing** the **changes** **both** to **QA gCTS Fiori** and **ABAP** **QA** systems.
{% endhint %}
