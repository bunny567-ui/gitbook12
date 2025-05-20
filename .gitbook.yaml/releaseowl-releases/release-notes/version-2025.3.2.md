# Version 2025.3.2

## **New Features** <a href="#new-features" id="new-features"></a>

#### **Application Header – Notifications**

* Added a **notification icon** in the application header to display important messages such as upcoming hotfixes and recent deployment details.
* Notifications are now shown as message strips within the app for improved visibility and user awareness.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252FX8OZimRvNkr88css3cdc%252Fimage.png%3Falt%3Dmedia%26token%3Ddf9f4893-0ded-4218-81f5-eb205265ccd9&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=f3757eaf&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1007).png" alt=""><figcaption></figcaption></figure>

**Release – Release Pipeline**

*   Introduced the "**Notify Promotion User**" option for all deployment tasks.

    * When enabled, an email notification is sent to the user who promoted the user story, regardless of the task's success or failure.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252FuANqDPGnQKuSv3ssUiIJ%252Fimage.png%3Falt%3Dmedia%26token%3De76108cd-770f-407a-ad8b-9d9d2132ede7&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=2106abb2&#x26;sv=2" alt=""><figcaption></figcaption></figure>
* Manual tasks linked to user stories can now be completed directly within the release pipeline.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252FXVXmytUAH4dgia1az3AH%252Fimage.png%3Falt%3Dmedia%26token%3D0816983b-4799-457a-9ac7-c0e0925c2c4e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=db49a7f7&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Validation Report – gCTS Transport**

* Integrated a dependency check for gCTS transport to detect object-level dependencies during the process.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252FaUki9fdmPcCNK9kxYQYm%252Fimage.png%3Falt%3Dmedia%26token%3D26aa3a7d-ab60-4341-a1db-29f910b21f2c&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e229fe54&#x26;sv=2" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (5) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### **Improvements** <a href="#improvements" id="improvements"></a>

#### **Release – Release Pipeline**

* Fixed an issue where duplicate stage names were not being validated. The system now correctly prevents the use of duplicate stage names.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252FMp27QGcQkABtiiu0JxzC%252Fimage.png%3Falt%3Dmedia%26token%3D02e5ec62-72de-4bdf-b158-da11f8687eb5&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=81ef217a&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Build – Transport Management**

*   Added a dropdown filter to the **Transport ID** column.

    * The filter supports both gCTS and non-gCTS transports for easier navigation and filtering.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252FYy9WuITYJko8HkTxoQNi%252Fimage.png%3Falt%3Dmedia%26token%3D9e61fba2-8229-48d3-9ed4-1f73c4067a5e&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=e270f6b1&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **CPI Test Generator – Test Case Creation**

*   Implemented input validation to prevent the use of special characters in CPI test case names.

    * This ensures naming consistency and avoids execution issues.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252FyEicZyNFx2lgM2RD3DXm%252Fimage.png%3Falt%3Dmedia%26token%3Df17a89f0-08ce-4b4e-a402-b34a0d84f09b&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=bf74c08c&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **CPI Test Generator – Test Run Details**

*   Added an "**Added"** label for unmatched paths where the expected value is null.

    * Enhances message comparison visibility in test results.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252Fw21LneXaMp1lTHTeukZh%252Fimage.png%3Falt%3Dmedia%26token%3D239305d3-36b1-4e9e-af0b-ea0f82b7a259&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=cee23118&#x26;sv=2" alt=""><figcaption></figcaption></figure>

#### **Release – Pipeline Activity – CPI Deployment / API Deploy Logs / Integration Advisor**

*   Introduced a "**Manual Completion**" option for failed or timed-out deployments.

    * Users can manually deploy artifacts and continue with the pipeline if all artifacts are successfully completed.



    <figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252FimbZELy48jLfY979NqQk%252Fimage.png%3Falt%3Dmedia%26token%3D16fd6e58-8920-4545-b3dc-941e94901287&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=dd2fe54c&#x26;sv=2" alt=""><figcaption></figcaption></figure>
* Added a new column, **Already Deployed**, in the CPI deployment logs to indicate artifacts already deployed in retries or manual completions.

<figure><img src="https://releaseowl.gitbook.io/~gitbook/image?url=https%3A%2F%2F2324742889-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F20Vxn9KxdCY20y3qv6p2%252Fuploads%252F2ws5IFIe6sHCs1SDWp3B%252Fimage.png%3Falt%3Dmedia%26token%3D1ecfaf68-4fd5-4618-b850-01859d4c21ae&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=35118fa3&#x26;sv=2" alt=""><figcaption></figcaption></figure>

* Refresh button now fetches the CPI runtime artifact deploy status and updates the runtime status in the deployment log.

<figure><img src="../../.gitbook/assets/image (1009).png" alt=""><figcaption></figcaption></figure>

#### **Build – CPI Management – IFlow Configuration**

* Editing **timer configuration parameters** (such as start time, recurrence, etc.) is **not supported** directly from ReleaseOwl.

<figure><img src="../../.gitbook/assets/image (1008).png" alt=""><figcaption></figcaption></figure>

#### **User Story and Test Evidence Attachments**

* Attachments larger than **1MB** are now **restricted** in User Stories and Test Evidence tasks to ensure optimal performance and storage usage.

<figure><img src="../../.gitbook/assets/image (1010).png" alt=""><figcaption></figcaption></figure>

#### **Release – Pipeline Activity**

* Viewing of **gCTS task details** is now enabled within **executed pipeline activities** for improved traceability and insight.

<figure><img src="../../.gitbook/assets/image (1011).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1012).png" alt=""><figcaption></figcaption></figure>

### **Bug Fixes** <a href="#bug-fixes" id="bug-fixes"></a>

#### **Administration – Manage Roles**

*   Fixed an issue where duplicate role names were not accepted.

    * The system now properly handles and validates unique role names as intended.

    <figure><img src="../../.gitbook/assets/image (1013).png" alt=""><figcaption></figcaption></figure>

