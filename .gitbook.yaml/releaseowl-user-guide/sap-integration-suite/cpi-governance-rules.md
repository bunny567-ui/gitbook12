# CPI Governance Rules

The CPI Rules section in ReleaseOwl provides a centralized configuration interface to enforce governance policies and best practices for SAP Cloud Platform Integration (CPI) artifacts. These rules ensure that artifacts comply with security, coding, and operational standards

By configuring CPI Rules, administrators can establish policies that improve security, consistency, and reliability in CPI development and deployments.

## 1. Key Objectives of CPI Rules

* Standardization: Enforce consistent development practices across artifacrs
* Security Compliance: Restrict insecure configurations (e.g., clear text authentication).
* Governance: Enable rule-based validation to prevent policy violations.
* Custom Policies: Define naming conventions and resource allowances.

## 2. Accessing CPI Rules

1. Navigate to Administration → Static Code Analysis → CPI Rules from the sidebar menu.
2. The CPI Rules Dashboard displays a list of pre-configured rules and customization options.

## 3. Configuring CPI Rules

### 3.1 Enabling/Disabling Rules

* Check or uncheck the checkbox next to each rule to enable or disable it.
* Enabled rules will be enforced during artifact deployments and validations.

### 3.2 Configuring Custom Policies

Use the dropdown fields for the following:

| **Rule**                                        | **Description**                                                                                                                                       |
| ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Clear Text Basic Auth Not Allowed**           | Blocks sender channels that use Basic Authentication, as the username and password are transmitted in an insecure format.                             |
| **Matching Process Direct Channels Required**   | Ensures that every ProcessDirect sender channel has a corresponding ProcessDirect receiver channel, preventing broken internal connections.           |
| **Multi Condition Type Routers Not Allowed**    | Prevents Router steps from using multiple condition types within the same router configuration.                                                       |
| **Unencrypted DataStore Write Not Allowed**     | Flags Data Store write operations where the **Encrypt Stored Message** option is disabled.                                                            |
| **Unencrypted Endpoints Not Allowed**           | Flags endpoints that use unsecured protocols such as HTTP or FTP instead of secure protocols like HTTPS or SFTP.                                      |
| **Client Cert Sender Channel Auth Not Allowed** | Prevents sender channels from using client certificate-based authentication.                                                                          |
| **CSRF Protection Required**                    | Requires Cross-Site Request Forgery (CSRF) protection to be enabled for HTTP-based sender channels.                                                   |
| **iFlow Description Required**                  | Ensures that every integration flow (iFlow) includes a description before validation or deployment.                                                   |
| **Allowed Scripting Languages**                 | Restricts Script steps to the selected scripting languages (for example, Groovy or JavaScript). Any other scripting language is flagged.              |
| **Allowed Receiver Adapters**                   | Allows only the selected receiver (outbound) adapters to be used. All other receiver adapters are flagged during validation.                          |
| **Allowed Sender Adapters**                     | Allows only the selected sender (inbound) adapters to be used. All other sender adapters are flagged during validation.                               |
| **Allowed XSLT Versions**                       | Restricts XSLT mappings to the selected XSLT versions (for example, 2.0 or 3.0).                                                                      |
| **Allowed Mapping Types**                       | Restricts mappings to the selected mapping types, such as Message Mapping, Operation Mapping, or XSLT Mapping.                                        |
| **Duplicate Resources Not Allowed**             | Flags duplicate resource types (such as scripts, mappings, WSDLs, or other artifacts) that are copied across multiple iFlows instead of being reused. |
| **Allowed User Roles**                          | Restricts sender channel authorization to the specified user roles. Any role not included in the configured list is flagged.                          |

### 3.3 Naming Conventions

The **Naming Conventions** section allows administrators to define custom naming rules for CPI artifacts using XML-based validation policies.

Each naming rule contains:

* **`<scheme>`** – Defines the validation logic.
* **`<message>`** – Error message displayed when validation fails.
* **`<apply-to>`** –  Specifies the CPI artifact or component to which the naming convention rule applies. Select the appropriate value based on the artifact you want to validate.

| **Category**                  | **Supported `<apply-to>` Values**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Integration Flow**          | `iflow.name`, `iflow.id`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Generic Channels**          | `channel.name`, `sender-channel.name`, `receiver-channel.name`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Sender Channel Adapters**   | `advancedeventmesh-sender-channel.name`, `amqp-sender-channel.name`, `ariba-sender-channel.name`, `as2-sender-channel.name`, `as4-sender-channel.name`, `azurestorage-sender-channel.name`, `data-store-sender-channel.name`, `dropbox-sender-channel.name`, `ftp-sender-channel.name`, `https-sender-channel.name`, `idoc-sender-channel.name`, `jms-sender-channel.name`, `kafka-sender-channel.name`, `mail-sender-channel.name`, `microsoft-sharepoint-sender-channel.name`, `odata-sender-channel.name`, `processdirect-sender-channel.name`, `rabbitmq-sender-channel.name`, `sftp-sender-channel.name`, `slack-sender-channel.name`, `smb-sender-channel.name`, `soap-sender-channel.name`, `splunk-sender-channel.name`, `successfactors-sender-channel.name`, `xi-sender-channel.name`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Receiver Channel Adapters** | `advancedevenmesh-receiver-channel.name`, `amazondynamodb-receiver-channel.name`, `amazoneventbridge-receiver-channel.name`, `amqp-receiver-channel.name`, `anaplan-receiver-channel.name`, `ariba-receiver-channel.name`, `as2-receiver-channel.name`, `as4-receiver-channel.name`, `azurestorage-receiver-channel.name`, `coupa-receiver-channel.name`, `dropbox-receiver-channel.name`, `elster-receiver-channel.name`, `facebook-receiver-channel.name`, `ftp-receiver-channel.name`, `http-receiver-channel.name`, `odata-receiver-channel.name`, `hubspot-receiver-channel.name`, `idoc-receiver-channel.name`, `jdbc-receiver-channel.name`, `jira-receiver-channel.name`, `jms-receiver-channel.name`, `kafka-receiver-channel.name`, `ldap-receiver-channel.name`, `mail-receiver-channel.name`, `mdi-receiver-channel.name`, `microsoft-sharepoint-receiver-channel.name`, `netsuite-receiver-channel.name`, `odc-receiver-channel.name`, `openconnectors-receiver-channel.name`, `processdirect-receiver-channel.name`, `rabbitmq-receiver-channel.name`, `rfc-receiver-channel.name`, `servicenow-receiver-channel.name`, `sftp-receiver-channel.name`, `slack-receiver-channel.name`, `smb-receiver-channel.name`, `snowflake-receiver-channel.name`, `soap-receiver-channel.name`, `splunk-receiver-channel.name`, `successfactors-receiver-channel.name`, `sugarcrm-receiver-channel.name`, `twitter-receiver-channel.name`, `workday-receiver-channel.name`, `xi-receiver-channel.name` |
| **Mappings**                  | `mapping.name`, `message-mapping.name`, `xslt-mapping.name`, `operation-mapping.name`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Scripts**                   | `script.name`, `groovy-script.name`, `js-script.name`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Integration Components**    | `sender.name`, `receiver.name`, `content-modifier.name`, `filter.name`, `xml-validator.name`, `edi-validator.name`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Data Store Operations**     | `data-store-operations.name`, `get-data-store-operations.name`, `select-data-store-operations.name`, `delete-data-store-operations.name`, `write-data-store-operations.name`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

### Supported Naming Rules

The following naming rules are supported :&#x20;

#### 1. starts-with

Ensures that an artifact name begins with a specified prefix.

**Example**

{% code overflow="wrap" expandable="true" %}
```xml
<naming>    <scheme>        <starts-with>IF_</starts-with>    </scheme>    <message>iFlow ID must start with "IF_"</message>    <apply-to>iflow.id</apply-to></naming>
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```angular-html
Result
Passes: IF_OrderToCash
Fails: OrderToCash
```
{% endcode %}

#### 2. ends-with

Ensures that an artifact name ends with a specified suffix.

**Example**

{% code overflow="wrap" %}
```xml
<naming>    <scheme>        <ends-with>_MM</ends-with>    </scheme>    <message>Message mapping name must end with "_MM"</message>    <apply-to>message-mapping.name</apply-to></naming>
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
Result
Passes :  Customer_MM
Fails : Customer_MM
```
{% endcode %}

#### 3. equals

Requires the artifact name to exactly match the specified value.

The optional **ignore-case="yes"** attribute enables case-insensitive matching.

**Example**

{% code overflow="wrap" expandable="true" %}
```xml
<naming>    <scheme>        <equals ignore-case="yes">SetHeaders</equals>    </scheme>    <message>The content modifier must be named "SetHeaders"</message>    <apply-to>content-modifier.name</apply-to></naming>
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
Result
Passes : SetHeaders
        setheaders
Fails  :SetHeader
```
{% endcode %}

#### 4. regex

Validates the artifact name using a Java regular expression.

**Example**

{% code overflow="wrap" expandable="true" %}
```xml
<naming>    <scheme>        <regex>^GRV_[A-Z][A-Za-z0-9]*$</regex>    </scheme>    <message>Groovy script name must match ^GRV_[A-Z][A-Za-z0-9]*$</message>    <apply-to>groovy-script.name</apply-to></naming>
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
Result
Passes :: GRV_MapPayload
Fails ::grv_mapPayload
         MapPayload
```
{% endcode %}

#### 5. not

Negates a validation rule.

**Example**

{% code overflow="wrap" expandable="true" %}
```xml
<naming>    <scheme>        <not>            <ends-with>_TEST</ends-with>        </not>    </scheme>    <message>iFlow name must not end with "_TEST"</message>    <apply-to>iflow.name</apply-to></naming>
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
Result
Passes :: OrderToCash
Fails :: OrderToCash_TEST
```
{% endcode %}

#### 6. and

Requires all nested conditions to be satisfied.

**Example**

{% code overflow="wrap" %}
```xml
<naming>    <scheme>        <and>            <starts-with>IF_</starts-with>            <not>                <ends-with>_OLD</ends-with>            </not>        </and>    </scheme>    <message>iFlow name must start with "IF_" and must not end with "_OLD"</message>    <apply-to>iflow.name</apply-to></naming>
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
Result
Passes: IF_OrderToCash
Fails: IF_OrderToCash_OLD
       OrderToCash
```
{% endcode %}

#### 7. or

Requires at least one of the specified conditions to be satisfied.

**Example**

{% code overflow="wrap" expandable="true" %}
```xml
<naming>    <scheme>        <or>            <starts-with>Z_</starts-with>            <starts-with>Y_</starts-with>        </or>    </scheme>    <message>Custom iFlow ID must start with "Z_" or "Y_"</message>    <apply-to>iflow.id</apply-to></naming>
```
{% endcode %}

{% code overflow="wrap" expandable="true" %}
```
Result
Passes : Z_Custom
          Y_Custom
Fails :A_Custom
```
{% endcode %}

## 4. Save Configuration

* Once all configurations are updated, click on the Save button at the top-right corner.

<figure><img src="../../.gitbook/assets/image (6) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
