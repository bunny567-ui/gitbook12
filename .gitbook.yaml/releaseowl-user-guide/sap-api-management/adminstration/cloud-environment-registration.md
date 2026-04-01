# Environment Registration

ReleaseOwl seamlessly integrates with SAP API Management to enable continuous integration and delivery of API artifacts.  To register the SAP API Environment, you must first register the API credential. Follow the[ link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-user-guide/sap-api-management/adminstration/credential-management)and complete the credential setup.

### API Environment Registration

1. Navigate to Environments from the Administration menu.
2. Select API Management and click on register API Management.
3. Provide the following details and click on **Save.**

| **Field**        | **Description**                                                |
| ---------------- | -------------------------------------------------------------- |
| Name             | Enter a unique name for the SAP API Environment.               |
| Host URL         | Copy the URL from the created SAP API Management instance.     |
| OAuth Credential | Select the OAuth credential created in the credential manager. |
| Environment Type | Select the environment type (e.g., Dev, QA, Prod).             |

<figure><img src="../../../.gitbook/assets/image (1751).png" alt=""><figcaption></figcaption></figure>

4. Once an environment is created, the **Linked Projects** section becomes available. This section displays a list of all projects that are currently associated with or utilizing the selected environment.

<figure><img src="../../../.gitbook/assets/image (1752).png" alt=""><figcaption></figcaption></figure>

### Adding Environments to Project

* To add environments to project, follow the [link ](https://releaseowl.gitbook.io/releaseowl-docs/releaseowl-admin-guide/general-administration/project-management)and complete the setup.

<figure><img src="../../../.gitbook/assets/image (1759).png" alt=""><figcaption></figcaption></figure>
