# Reports

The **Reports** section is available within the **Project View** and provides comprehensive insights into deployment activities. It includes two key reports:

* **Deployment Reports**
* **Task Reports**
* **Pipeline Reports**

These reports help teams monitor deployment progress, validate successful deployments, and maintain traceability across environments.

### Deployment Report

The Deployment Report offers detailed insights into the deployment status of User Stories, Transports, CPI artifacts, BTP artifacts, and Multiverse artifacts within the selected project.

**How to Generate the Report:**

1. Navigate to the **Reports** section in the **Project View**.
2. Click on the type of the deployment user story that you want to do.

<figure><img src="../.gitbook/assets/image (2316).png" alt=""><figcaption></figcaption></figure>

3. Select the following parameters:

* **From Date**
* **End Date**
* **Environment**
* **Target System**

4. Click **GO** to generate the report.

<figure><img src="../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Report Details:**

The generated report displays:

* User Story identifiers
* Deployment date and time
* Environment and Target System details
* Deployment status

This report helps teams track user story deployments and confirm successful completion. You can also **export the report in PDF or Excel format**.

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1)   (3).png" alt=""><figcaption></figcaption></figure>

### Tasks

The Task Report provides an overview of all the **tasks related to User Stories, Transports, and CPI artifacts**.&#x20;

**How to Generate the Report:**

1. Go to the **Reports** section in the **Project View**.
2. Click on **Task Reports** &#x20;

<figure><img src="../.gitbook/assets/image (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Select the following parameters:

* **From Date**
* **End Date**

4. Click **GO** to generate the report. It provides details of releasepipeline, tasksource, assigne and action.&#x20;

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Pipeline Reports

The Pipeline Reports give you an audit trail for your release pipelines. For a chosen period they show which User Stories (and which CPI or API artifacts) were deployed through a pipeline stage, who promoted them, who approved them, and how each deployment was carried out. Use them as evidence for audits, release sign-offs and change-management reviews.

The Reports section in the Project View has three tabs: Deployment Reports, Task Reports and Pipeline Reports. The Pipeline Reports contain three reports:

1. User Story Deployment Pipeline Report
2. CPI Artifacts Deployment Pipeline Report
3. API Artifacts Deployment Pipeline Report

<figure><img src="../.gitbook/assets/image (2326).png" alt=""><figcaption></figcaption></figure>

#### User Story Deployment Pipeline Report

This report tells you, for each User Story that reached the selected stages, who promoted it, who approved it and what was deployed, and whether promotion and approval were done by different people.

#### Generate the report

1. Open the User Story Deployment Pipeline Report tile.
2. Enter the filters:&#x20;

| **Filter**            | **Description**                                                                                               |
| --------------------- | ------------------------------------------------------------------------------------------------------------- |
| **From Date**         | Start of the period to audit.                                                                                 |
| **To Date**           | End of the period to audit.                                                                                   |
| **Release Pipeline**  | The release pipeline whose deployments you want to audit.                                                     |
| **Stages**            | One or more stages of that pipeline can be added here. Only promotions into the selected stages are reported. |

* &#x20;Click **Go** to generate the report.

<figure><img src="../.gitbook/assets/image (2327).png" alt=""><figcaption></figcaption></figure>

* Click **Hide Filters** to give the table more room, and use the gear icon to choose which columns are shown. Scroll to the right to see all columns.

#### Report Details

Each row represents a User Story at a specific pipeline stage. If multiple stages are selected, a User Story that has reached more than one selected stage appears once for each stage.

| **Column**                | **Description**                                                                                                                                                                                                                   |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **User Story ID**         | The unique ReleaseOwl ID of the User Story.                                                                                                                                                                                       |
| **External ID**           | The ID of the User Story in the connected ALM tool, if available.                                                                                                                                                                 |
| **Summary**               | The title of the User Story.                                                                                                                                                                                                      |
| **Release Package**       | The release package associated with the deployment, if the User Story was included in a release package.                                                                                                                          |
| **Stage**                 | The pipeline stage being audited.                                                                                                                                                                                                 |
| **Promotion**             | The pipeline stage from which the User Story was promoted.                                                                                                                                                                        |
| **Promoted By**           | The user who promoted the User Story to the stage.                                                                                                                                                                                |
| **Promoted On**           | The date and time when the User Story was promoted to the stage.                                                                                                                                                                  |
| **Approvals\_n**          | A group of columns for each approval task in the pipeline, showing the approver, approval date and time, and any comment entered. If a deputy approved on behalf of another user, the details also identify the user represented. |
| **Deployments**           | A group of columns for each deployment task in the pipeline, showing the user who performed the deployment, the deployment date and time, the target environment, and the deployment result.                                      |
| **Segregation of Duties** | The **Segregation of Duties** column compares the person who promoted a story with the people who approved it. Each result is a link: click it to open a short explanation of why the row got that result.                        |

<figure><img src="../.gitbook/assets/image (2331).png" alt=""><figcaption></figcaption></figure>

#### CPI Artifacts Deployment Pipeline Report

This report lists every CPI artifact that was deployed by the selected pipeline and stages, together with the audit information of the User Story it belongs to.

1. Open the CPI Artifacts Deployment Pipeline Report tile.
2. Enter From Date, To Date, Release Pipeline and Stages as described above.
3. Click Go.

<figure><img src="../.gitbook/assets/image (2329).png" alt=""><figcaption></figcaption></figure>

#### Report Details

Unlike the User Story report, this report displays the deployed artifact details at the beginning of each row, followed by the associated User Story and deployment information.

| **Column**                      | **Description**                                                                                                              |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Artifact Name**               | Displays the name of the deployed SAP Cloud Integration (CPI) artifact.                                                      |
| **Artifact Type**               | Displays the type of artifact.                                                                                               |
| **Version**                     | Displays the version of the artifact that was deployed.                                                                      |
| **Package**                     | Displays the CPI package that contains the artifact.                                                                         |
| **User Story ID … Promoted On** | Displays the User Story ID and the associated stage, promotion, and approval details, as described in the User Story report. |
| **Manual Completion**           | For manually completed deployments, displays the corresponding icon for manually completed deployments.                      |

<figure><img src="../.gitbook/assets/image (2330).png" alt=""><figcaption></figcaption></figure>

#### API Artifacts Deployment Pipeline Report

This report works exactly like the CPI Artifacts report, but lists the SAP API Management artifacts (for example API proxies) deployed by the selected pipeline and stages. Each row shows the Artifact Name, Artifact Type and Version, followed by the story, promotion, approval and manual-deployment columns.

1. Open the API Artifacts Deployment Pipeline Report tile.
2. Enter From Date, To Date, Release Pipeline and Stages.
3. Click Go.

#### Export a report

1. Generate the report with Go.
2. Click Export in the top-right corner.
3. The report is downloaded as an Excel workbook. The export contains all records for the selected filters, not only the page you are viewing. Attach the exported file as deployment evidence for audits and release sign-offs.

<figure><img src="../.gitbook/assets/image (2332).png" alt=""><figcaption></figcaption></figure>
