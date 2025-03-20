# Working with Build Pipelines

**Build**

Build Section in ReleaseOwl enables developers to create the MTAR artifacts and validate the changes thoroughly for early feedback.

**Build Pipeline (SAP BTP)**

Artifact

Artifact is a folder or a zip file containing files needed during a deployment of software to an environment.

Build Pipeline

A pipeline is the sequence of activities you execute, one at a time, in the form of a workflow configured in your Continuous Integration and Delivery platform

A Build Pipeline is used to generate Artifacts out of Source Code. Build Pipelines can be created and run with Release Owl. It fetches the source from GIT Repository and package the application as MTA artifact.

MTA

An MTA is logically a single application, consisting of multiple related and interdependent parts called modules that are developed using different technologies and designed to run on different target runtime environments, with a single, consistent lifecycle.

Further information on SAP BTP App Development can be found by accessing the below mentioned link:

[https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/d04fc0e2ad894545aebfd7126384307c.html?q=Multitarget%20Application](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/d04fc0e2ad894545aebfd7126384307c.html?q=Multitarget%20Application)

MTAR File Generation

The MTA archive builder is a standalone command-line tool that builds a deployment-ready MTAR (.mtar file) from the artifacts of an MTA project according to the project’s MTA development descriptor (mta.yaml file).

The build process and the resulting MTA archive depend on the target platform on which the archive will be deployed which can be **SAP BTP** or **SAP HANA extended application services (XSA)**, advanced model environment as these two are supported currently by ReleaseOwl.

**Prerequisites**

1. Create new project of type SAP BTP (MTAR) or SAP HANA XSA (MTAR)
2. Register BTP Credentials and BTP Environment with ReleaseOwl before starting to work with Build Pipelines.

**Create New Build Pipeline**

To create a new build pipeline:

1. Go to **Build** and click **Build Pipeline (SAP BTP)**.
2. In the page displayed, click **Create New Build Pipeline.**
3. Based on your type of application, **choose SAP BTP (MTAR)** or **SAP HANA XSA (MTAR).**

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-1.jpg)\
\


Creating a new build pipeline is a seven-step process.

1\. **Pipeline Name:** Enter a name to identify the release pipeline. Once saved, this name cannot be changed.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-2.jpg)\
\


2\. **Select Repo Type:** Choose the required version management system (GITHub or BitBucket) and its related credentials.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-3.jpg)\
\


3\. **Select Repo:** It lists all the repositories of the user. Choose the git repository that will be used to fetch changes, for creating MTAR artifacts.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-4.jpg)\
\


**Note:** In case of SAPGit there's no repo selection. Instead, explicitly provide repo URL.

4\. **Select Branch:** All the branches related to the selected repo displayed here. Choose a branch for which you want to build the MTAR artifact.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-5.jpg)\
\


5\. **Builder:** For cloud applications, MTA builder is supported now. MTA builder is used to create an MTAR file.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-6.jpg)\
\


6\. **Scheduler:** You can schedule your build pipeline in three ways.

| **Manual**   | You can manually trigger a build from the corresponding build pipeline from the list of pipelines.                                                                                                      |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Schedule** | Schedule a build to be run daily at a chosen time.                                                                                                                                                      |
| **WebHook**  | <p>WebHook URL should be updated in GIT repository. Once the GIT repo is updated with webhook, the pipeline is triggered with every commit.<br>Note: If SAPGit is chosen, WebHook is not supported.</p> |

Upon selecting the Schedule option, the user is allowed to select the time when the execution of the build pipeline is to be scheduled.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-7.jpg)\
\


Upon selecting the WebHook option, the user is allowed to select GIT or ALM or both GIT and ALM.

![](https://www.docs.releaseowl.com/assets/img/recent-1%20SAP%20BTP.jpg)\
\


**Note:** ALM option is shown only when the current working project in ReleaseOwl is integrated with any project setup in any ALM such as JIRA, ServiceNow or Azure DevOps.

![](https://www.docs.releaseowl.com/assets/img/recent-1%20SAP%20BTP-1.jpg)\
\


Also, on selecting ALM, the webhook URL gets generated after the build pipeline is saved as follows:

![](https://www.docs.releaseowl.com/assets/img/recent-1%20SAP%20BTP-2.jpg)\
\


Any change made in GIT and/or ALM triggers the WebHook resulting in the execution of the build pipeline.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-8.jpg)\
\


7\. **Email Id:** Enter an email id to receive build notifications. Multiple email Ids can be specified by separating them with comma (,).

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-9.jpg)\
\


**Note:** By default, the person who created the build pipeline receives the notification emails irrespective of whether any email distribution list is specified or not in the Email ID field.

8\. **Tool Integrations:** Select SonarQube and choose the related credentials from the drop down.

**Note:** ReleaseOwl supports SonarQube, either on your premise or use ReleaseOwl’s default SonarQube integration.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-10.jpg)\
\


Click **Review**. The following page is displayed:

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-11.jpg)\
\


Click **Submit**, a new build pipeline is created. This pipeline is displayed in the **Build Pipeline** page.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-12.jpg)\
\


**Actions**

Multiple actions can be performed on a build. These actions include:

* Build Now
* Commits
* Edit
* Delete

**Build Now**

Click **Build Now**, to trigger a build pipeline. A build can be triggered multiple times.

**Logs**

Once a build is triggered, build logs of all the stages are displayed in the page.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-13.jpg)\
\


**View Individual Logs**

To view individual build logs:

1\. Go the required stage and click **Logs**.

2\. Click on the links in the log, to be redirected to its related pages.

![](https://www.docs.releaseowl.com/assets/img/Working%20with%20Build%20Pipelines-14.jpg)\
