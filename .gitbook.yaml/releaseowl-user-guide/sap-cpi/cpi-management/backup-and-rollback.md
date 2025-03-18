# Backup & Rollback

The Enable Rollback option is one among the various Deployment Actions that can be performed at the time of deployment. Enable Rollback option will create a backup of the existing deployment version so that whenever any deployment fails or if there is any problem with the deployment, you can rollback the changes.

Rollback is available for CPI artifacts that are deployed to design time in addition to those published to run time. While creating a release pipeline, you must enable the option to rollback as a prerequisite. Click rollback in the deployment screen to rollback while running release pipelines. All the details pertaining to the deployment of the artifact is specified in the deployment task.

The following screen is displayed on adding a deployment task. Select the checkbox – Enable Rollback and Save the changes.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/Backup%20&#x26;%20Roll%20back-1.jpg" alt=""><figcaption></figcaption></figure>

You can view the Release Pipeline execution status from User Stories screen by navigating to the Pipeline Activity as shown below:\


<figure><img src="https://www.docs.releaseowl.com/assets/img/Backup%20&#x26;%20Roll%20back-2.jpg" alt=""><figcaption></figcaption></figure>

Click on the Pipeline Activity option. You can find the Rollback option under Deployment section. At any point of time i.e., during or after the deployment done by the execution of the Release Pipeline, you can rollback to previous version by clicking the Rollback option available.

To rollback to the previous version, click on Rollback and in the confirmation pop-up that appears, click Yes. Rollback process starts.

**Rollback Logs**

Rollback Logs are available for CPI artifacts that are deployed to design time in addition to those published to run time. To rollback a build, click Rollback in the status page.

Once rollback is enabled, you can see the rollback status in the deployment logs.

<figure><img src="../../../.gitbook/assets/image (359).png" alt=""><figcaption></figcaption></figure>

\
