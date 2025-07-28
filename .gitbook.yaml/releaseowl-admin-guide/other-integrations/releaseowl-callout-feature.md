# ReleaseOwl Callout Feature

Callout is a feature of making a call to an external web service or sending an HTTP request and receiving the response. Each REST callout request is associated with an HTTP method and an endpoint. A REST API callout is the process of a client application submitting a request to an API and that API retrieving the requested data from the third-party system say external server or program and delivering it back to the client.

{% hint style="info" %}
**Note:** Currently, we support callouts for only **ServiceNow.**
{% endhint %}

## **Registering Callout**

This section is for registering REST API Callouts for ServiceNow.

1\. In **Administration**, go to **Callouts**.

2\. In page displayed, click **Register Callout.**\


<figure><img src="../../.gitbook/assets/image (8) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3\. Fill in the required details.

| **Name**              | Enter any name of your choice for the callout being registered.                                                                                                                                                                                                                                                                                                                                                                                                               |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **System Type**       | ServiceNow for ServiceNow API calling and Others for any generic REST/HTTP URL call                                                                                                                                                                                                                                                                                                                                                                                           |
| **Credential**        | Select the Basic Auth credential that you have registered in the credential Manager.                                                                                                                                                                                                                                                                                                                                                                                          |
| **URL Path**          | It specifies the address where the service is located. In case of ServiceNow, Instance Base URL will be populated automatically from the ServiceNow credential. User must enter the path for the required REST API.                                                                                                                                                                                                                                                           |
| **HTTP Method**       | <p>HTTP request like GET, POST, PUT, and DELETE.<br><br><strong>GET</strong> - It helps in retrieving resources identified by the URL <strong>PUT</strong> - It allows to update or replace the resource sent to the request body. <strong>POST</strong> - It creates a resource or post data to the server. <strong>DELETE</strong> - It deletes the resource identified by the URL<br><br>Select the option based on the type of the REST API that is being called out.</p> |
| **Payload JSON**      | <p>Payload JSON string is for POST and PUT types of requests that are passed from ReleaseOwl to the third-party system.<br><br>Payload supports the parameters, which can be replaced in the Release Pipeline execution with values configured during Release Pipeline creation.<br>Parameters are specified with enclosed double curly braces. For ex: {{}}</p>                                                                                                              |
| **Response JSON**     | The response JSON string upon calling the third-party REST API.                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Unique Identifier** | <p>Unique ID created by the third-party system for a particular REST API call in case of POST type request. This will be useful to track the tasks when callouts are used in the Release Pipeline.<br>The expression specified in the field will be evaluated on the response JSON from the REST API call.</p>                                                                                                                                                                |

\


4\. You can check whether the established connection to the third-party REST API is successful or not by clicking the Test button.

5\. Once the connection is verified, you can save the callout.

<figure><img src="../../.gitbook/assets/image (9) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Adding a Callout Task in Release Pipeline**

You can add callout as a Task in the Release Pipeline.

1\. When adding a new task in Pipeline stage, select **Callout Task**, then the following screen is displayed:\


<figure><img src="../../.gitbook/assets/image (10) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2\. Fill in the required details:

| **Name**               | Enter any name of your choice for the callout task being created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Callouts**           | Choose the required callout from the drop down.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Config Params**      | Parameters specified in the Payload JSON can be passed during run-time through the Config Params option.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Pipeline Execution** | <p><strong>Continue on Failure</strong> – If selected, the Release Pipeline Execution will continue even if the callout fails.<br>If the option is left <strong>unchecked</strong>, then the pipeline execution fails if it encounters any error in calling out the external API.<br><strong>Wait on Task</strong> – If selected, then approval task will be created after the callout execution even if callout fails or succeeds. Users can open the task and retry callout execution in case of callout failure.<br>If the option is left <strong>unchecked</strong>, it will act as a normal web service call which calls out external API and continues based on the response of the external API.</p> |
| **Assign To**          | <p><strong>User</strong> – The approver (user) can be selected from the available list of users for approving the pending task in order to complete the Release Pipeline execution when Wait on Task option is chosen.<br><br><strong>Role</strong> - The pending task can be approved by any user with the user role that is selected in order to complete the Release Pipeline execution when Wait on Task option is chosen.</p>                                                                                                                                                                                                                                                                          |
| **Message**            | Any message that is to be conveyed to the task approver can be mentioned here.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

3. When you click the **Config Params** button, the configuration screen is displayed. Here, enter the variable parameter names as defined in the **Payload JSON**, along with their corresponding values. These parameters will be passed at runtime during the execution of the **Release Pipeline**.
4. After entering the required values, click **Save** to apply the changes.\


<figure><img src="../../.gitbook/assets/image (387).png" alt=""><figcaption></figcaption></figure>

## **System Defined Parameters**

### **System Defined Parameters for a Callout Task - Generic**

* Below are the variables available for using as values in the configure parameters for a **Callout Task**.

| **${jobins.jobCycleName}**   | Cycle name given while triggering the Release Pipeline.                                   |
| ---------------------------- | ----------------------------------------------------------------------------------------- |
| **${jobins.instantiatedBy}** | Email ID of the person who triggered the Release Pipeline                                 |
| **${jobins.label}**          | Release Pipeline Name                                                                     |
| **${jobins.status}**         | Status of the instance/cycle/>                                                            |
| **${jobins.endTime}**        | <p>End time when instance is completed.<br>(YYYY-MM-DDTHH24:MM:SS.000+0000)</p>           |
| **${jobins.createTime}**     | <p>Represents the time when instance was created.<br>(YYYY-MM-DDTHH24:MM:SS.000+0000)</p> |
| **${jobins.startTime}**      | <p>Represents the time when instance was started<br>(YYYY-MM-DDTHH24:MM:SS.000+0000)</p>  |

\


### **System Defined Parameters specific to the Release Pipelines of type SAP BTP**

| **${jobins.inputs.buildJobName}** | Name of the build pipeline used as an input for the Release Pipeline.                                                                |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **${jobins.inputs.buildNumber}**  | Build number of the build pipeline (given as input in the Release pipeline), artifact is used for deploying in the Release Pipeline. |
