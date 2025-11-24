# GIT Ops

## **Prerequisites**

1. Create new project of type SAP BTP (MTAR) or SAP HANA XSA (MTAR)
2. Register BTP Credentials and BTP Environment with ReleaseOwl.
3. Create and run one or more Build Pipelines with changes done at GT repository level.

### **Commits**

When you trigger the build, all the commits done on the repository right from the previous build run are pulled and shown to the user.

The commits done can be selected and assigned to a user story to track their deployment.<br>

<figure><img src="../../.gitbook/assets/image (1223).png" alt=""><figcaption></figcaption></figure>

### **Assign User Stories to GIT Commits**

Select the user story and click Assign User Story. Select the user story.\
<br>

<figure><img src="../../.gitbook/assets/image (1224).png" alt=""><figcaption></figcaption></figure>

You can also automatically assign a user story to a particular commit by specifying #ID in the Commit message that you specify in BitBucket or GITHub.

**Note:** Mention the external user story ID if project is integrated with external ALM tool, else provide ReleaseOwl user story ID.<br>

<figure><img src="../../.gitbook/assets/image (1225).png" alt=""><figcaption></figcaption></figure>

Thereafter when you trigger the build and click on commits, you get to see that the commit gets assigned to the user story automatically and the commit message given in the **Bitbucket** or **GITHub i**s seen under the **Commit Message** as shown below:

<figure><img src="../../.gitbook/assets/image (1226).png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://www.docs.releaseowl.com/assets/img/Git-Ops-4.jpg" alt=""><figcaption></figcaption></figure>
