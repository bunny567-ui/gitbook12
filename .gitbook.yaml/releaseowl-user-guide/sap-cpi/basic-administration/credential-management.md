# Credential Management

You have to register the SAP BTP login credentials to access the SAP CPI environment with ReleaseOwl first.

Register a new credential from the Administration view as follows:

1\. Navigate to the Credential Manager screen.

2\. Click the Register Credential link.

3\. Select the Credential Type – SAP Cloud Environment.

4\. Provide any Credential Name of your choice.

5\. For Authentication Type Basic - provide your username and password.\


<figure><img src="https://www.docs.releaseowl.com/assets/img/credential-management-1.jpg" alt=""><figcaption></figcaption></figure>

6\. For Authentication Type OAuth2 – Instead of password, authorization tokens are issued to verify an identity between consumers and service providers. OAuth 2 provides better security than basic authentication as the initial requests for credentials are made under the SSL protocol and its access object is a transitory token.

For further information on getting Client Id, Client Secret and Auth Token URL, please refer to the link - https://help.sap.com/docs/CLOUD\_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/19af5e205fe14af6a4f8a9fd80d4dc92.html\


<figure><img src="https://www.docs.releaseowl.com/assets/img/credential-management-2.jpg" alt=""><figcaption></figcaption></figure>

7\. Save the changes to access your BTP user account.

8\. The newly created credential gets listed in the Credential Manager screen.
