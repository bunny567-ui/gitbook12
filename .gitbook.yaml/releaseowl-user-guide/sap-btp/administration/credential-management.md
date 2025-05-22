# Credential Management

## **Register BTP Credentials**

1. From the left-hand menu, select Credential Manager under the Administration section.
2. Click on the Register Credential button in the top-right corner of the screen.
3. In the Register Credential form, provide the following details:

* **Credential Name**: Enter a unique name for the credential to easily identify it.
* **Credential Type**: Select SAP Cloud Environment from the dropdown list.
* **Authentication Type**: Choose the authentication method. In this case, select Basic.
* **User Name**: Enter the username for the cloud environment.
* **Password**: Enter the corresponding password.

4. Once all fields are filled, click the **Save** button to register the credential.
5. A confirmation message will appear if the registration is successful.
6. The newly registered credential will appear in the **List of Credentials** section.

<figure><img src="../../../.gitbook/assets/image (1221).png" alt=""><figcaption></figcaption></figure>

7. **For Authentication Type OAuth2** – Instead of password, authorization tokens are issued to verify an identity between consumers and service providers. OAuth 2 provides better security than basic authentication as the initial requests for credentials are made under the SSL protocol and its access object is a transitory token.

{% hint style="info" %}
**Note:** For further information on getting Client Id, Client Secret and Auth Token URL, please refer to the link - [https://help.sap.com/docs/CLOUD\_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/19af5e205fe14af6a4f8a9fd80d4dc92.html](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/19af5e205fe14af6a4f8a9fd80d4dc92.html)
{% endhint %}

8. Save the changes to access your BTP user account.
9. The newly created credential gets listed in the Credential Manager screen.

<figure><img src="../../../.gitbook/assets/image (1222).png" alt=""><figcaption></figcaption></figure>
