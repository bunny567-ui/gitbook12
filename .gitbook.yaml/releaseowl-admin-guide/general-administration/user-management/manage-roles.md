# Manage Roles

The Manage Roles feature in the **Administration View** allows administrators to create, edit, and delete roles to manage user privileges within the platform.

## Create Role

To create a new role:

1. Click on the **Create Role** button located at the top right corner of the screen.
2. Fill in the required details, such as the **Role Name** and **Description**.
3. Click **Save** to create the new role.

<figure><img src="../../../.gitbook/assets/image (1161).png" alt=""><figcaption></figcaption></figure>

4. Duplicate role names are not allowed. If the role name already exists, you will be prompted to enter a unique name.

<figure><img src="../../../.gitbook/assets/image (1162).png" alt=""><figcaption></figcaption></figure>

5. The newly created role will appear in the list of available roles.

<figure><img src="../../../.gitbook/assets/image (1015).png" alt=""><figcaption></figcaption></figure>

## Assign Role Actions

Role Actions define the permissions and access levels associated with a role. To assign the role actions to an existing role:

1. Click the **Edit** icon next to the role name.

<figure><img src="../../../.gitbook/assets/image (1163).png" alt=""><figcaption></figcaption></figure>



2. The **Role Actions** screen is displayed.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## Role Actions

The **Role Actions** screen allows administrators to define and manage permissions assigned to a role. Users assigned to a role inherit all permissions configured for that role, enabling controlled access to specific features and operations within the platform. Permissions are grouped into functional categories to simplify role management.

### Change Management

**Change Management** is where the team plans and tracks its work in sprints and user stories, and moves each change from development through to production.

| Role Action                           | What it does                                                                                |
| ------------------------------------- | ------------------------------------------------------------------------------------------- |
| Create/Edit Sprint                    | Lets the user create a new sprint or change an existing one's name, dates or goal.          |
| Sync Sprints                          | Pulls the latest sprints in from the connected planning tool, such as Jira or Azure DevOps. |
| Cancel Sprint                         | Lets the user stop or close a sprint before it is finished.                                 |
| Create/Edit User stories              | Lets the user create a user story or change its details.                                    |
| Sync User stories                     | Pulls the latest user stories in from the connected planning tool.                          |
| Update User Story Status              | Lets the user change a story's status, for example from "In Progress" to "Done".            |
| Promote User stories                  | Moves a user story and all its linked changes to the next stage, for example DEV → QA.      |
| Change Release Pipeline of User Story | Lets the user switch which release pipeline a user story is deployed through.               |

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

### Pipelines

**Pipelines** is where the team sets up and runs the automated steps that build, test and deploy changes across SAP systems.

| Role Action                     | What it does                                                                                                          |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Create Build Pipeline           | Lets the user set up a new pipeline that builds and checks the code automatically.                                    |
| Edit Build Pipeline             | Lets the user change a build pipeline's stages or settings.                                                           |
| Run Build Pipeline              | Lets the user start a build pipeline run.                                                                             |
| Delete Build Pipeline           | Lets the user permanently remove a build pipeline.                                                                    |
| Archive/Active Build Pipeline   | Lets the user archive a build pipeline that isn't used, or make it active again.                                      |
| Create Release Pipeline         | Lets the user set up a new pipeline that deploys changes from one landscape to the next, for example DEV → QA → PROD. |
| Edit Release Pipeline           | Lets the user change a release pipeline's stages, approvals or target systems.                                        |
| Run Release Pipeline            | Lets the user start a deployment through a release pipeline.                                                          |
| Delete Release Pipeline         | Lets the user permanently remove a release pipeline.                                                                  |
| Abort Release Pipeline          | Lets the user stop a deployment that is in progress.                                                                  |
| Archive/Active Release Pipeline | Lets the user archive a release pipeline that isn't used, or make it active again.                                    |

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

### Release Package

**Release Package** is where several changes are grouped into one bundle so they can be deployed together as a single release.

| Role Action                                | What it does                                                                                    |
| ------------------------------------------ | ----------------------------------------------------------------------------------------------- |
| Create Release Package                     | Lets the user create a new bundle of user stories, transports or artifacts to release together. |
| Edit Release Package                       | Lets the user add or remove items in a release package or change its details.                   |
| Delete Release Package                     | Lets the user permanently remove a release package.                                             |
| Lock Release Package                       | Freezes a release package so nobody can change its contents.                                    |
| Unlock Release Package                     | Unfreezes a locked release package so it can be edited again.                                   |
| Promote Release Package                    | Moves the whole release package to the next stage, for example QA → PROD.                       |
| Change Release Pipeline of Release Package | Lets the user switch which release pipeline the package is deployed through.                    |

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

### Transport Management

**Transport Management** is where ABAP transport requests are created, released, imported and tracked across the SAP landscape.

| Role Action                   | What it does                                                                                                |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Create Transport              | Lets the user create a new transport request in the SAP system from ReleaseOwl.                             |
| Edit Transport                | Lets the user change a transport's description or other details.                                            |
| Release Transport             | Releases a transport in the source system so it is ready to be imported.                                    |
| Import Transport              | Imports a transport into a target system such as QA or PROD.                                                |
| Sync Transports From SAP      | Pulls the latest transports from the SAP system into ReleaseOwl.                                            |
| Manage Critical Objects       | Lets the user keep the list of sensitive objects that need extra checks before they are moved.              |
| Retrofit Transports           | Copies changes from one track back into another, for example from the maintenance line to the project line. |
| Remove Transport From Project | Takes a transport out of the project so it is no longer tracked there.                                      |
| Promote Transports ✅          | Moves a transport to the next stage in its pipeline.                                                        |
| Import via ToC                | Imports a Transport of Copies first, so the change can be tested before the real transport moves.           |
| Manage External Transports    | Lets the user handle transports that were created outside ReleaseOwl.                                       |

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

### gCTS Transport

**gCTS Transport** is where Git-based ABAP changes (gCTS) are merged between branches and any conflicts are fixed.

| Role Action                     | What it does                                                                       |
| ------------------------------- | ---------------------------------------------------------------------------------- |
| Create gCTS Merge Configuration | Lets the user set up rules for merging one gCTS branch into another.               |
| Edit gCTS Merge Configuration   | Lets the user change existing gCTS merge rules.                                    |
| Execute gCTS Merge              | Runs the gCTS branch merge.                                                        |
| Delete gCTS Merge Configuration | Lets the user permanently remove a gCTS merge configuration.                       |
| Resolve gCTS merge conflicts    | Lets the user fix conflicts that come up during a gCTS merge.                      |
| Resolve Transport Conflicts     | Lets the user fix clashes, for example when two transports change the same object. |

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

### CPI Management

**CPI Management** is where SAP Cloud Integration (CPI) packages and iFlows are tracked, configured, tested and deployed.

| Role Action                             | What it does                                                                                                 |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Add/Remove Packages from Project        | Lets the user choose which CPI packages the project manages.                                                 |
| Sync CPI Artifacts from CPI Environment | Pulls the latest iFlows and other artifacts from the CPI tenant.                                             |
| Assign User Story to CPI Artifact       | Links a CPI artifact to a user story so it moves along with that story.                                      |
| Edit IFlow Configuration                | Lets the user change an iFlow's externalized parameters (URLs, credentials, and so on) for each environment. |
| Download CPI Artifact                   | Lets the user download a CPI artifact as a zip file.                                                         |
| Rollback CPI Deployment                 | Puts the previously deployed version of an artifact back in place.                                           |
| Generate CPI Testcases                  | Creates test cases for iFlows automatically.                                                                 |
| ImportSettings                          | Lets the user set how CPI artifacts are imported or deployed into the target tenant.                         |
| Update CPI Testcases                    | Lets the user change existing CPI test cases.                                                                |
| Run CPI Testcases                       | Runs the CPI test cases to check the iFlows work correctly.                                                  |

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

### API Management

**API Management** is where API proxies and providers are tracked, configured and moved between API Management tenants.

| Role Action                             | What it does                                                                                |
| --------------------------------------- | ------------------------------------------------------------------------------------------- |
| Sync API Artifacts from API Environment | Pulls the latest API proxies, providers and other artifacts from the API Management tenant. |
| Assign User Story to API Artifact       | Links an API artifact to a user story so it moves along with that story.                    |
| Edit API Configuration                  | Lets the user change API settings, such as the target endpoint, for each environment.       |
| Download API Artifact                   | Lets the user download an API artifact.                                                     |
| Add/Remove Packages from Project        | Lets the user choose which API packages the project manages.                                |
| ImportSettings                          | Lets the user set how API artifacts are imported into the target tenant.                    |

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

### Integration Advisor

**Integration Advisor** is where message guidelines (MIGs) and mapping guidelines (MAGs) are tracked and moved between tenants.

| Role Action                                       | What it does                                                                             |
| ------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Add/Remove Artifacts from Project                 | Lets the user choose which MIGs and MAGs the project manages.                            |
| Sync Artifact from Environment                    | Pulls the latest MIGs and MAGs from the tenant.                                          |
| Assign User Story to Integration Advisor Artifact | Links a MIG or MAG to a user story so it moves along with that story.                    |
| Download Integration Advisor Artifact             | Lets the user download a MIG or MAG.                                                     |
| ImportSettings                                    | Lets the user set how Integration Advisor artifacts are imported into the target tenant. |

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

### B2B Scenarios

**B2B Scenarios** is where Trading Partner Management artifacts, such as partner agreements, are tracked and moved between tenants.

| Role Action                               | What it does                                                             |
| ----------------------------------------- | ------------------------------------------------------------------------ |
| Add/Remove Artifacts from Project         | Lets the user choose which B2B artifacts the project manages.            |
| Edit Partner Directory Data Configuration | Lets the user change Partner Directory values for each environment.      |
| Download B2B Agreements                   | Lets the user download trading partner agreements.                       |
| ImportSettings                            | Lets the user set how B2B artifacts are imported into the target tenant. |

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

### SAP Analytics Cloud

**SAP Analytics Cloud** is where SAC content, such as stories and models, is moved from a source SAC tenant to a target one.

| Role Action                                    | What it does                                                                                        |
| ---------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Add/Remove Packages from Project               | Lets the user choose which SAC content packages the project manages.                                |
| Sync SAC Network Item from Sap Analytics Cloud | Pulls the latest Content Network items from SAC.                                                    |
| Assign User Story to SAC Network Item          | Links a SAC item to a user story so it moves along with that story.                                 |
| Edit SAC Package Configuration                 | Lets the user change a SAC package's settings for each target tenant.                               |
| ImportSettings                                 | Lets the user set how SAC content is imported, for example whether existing content is overwritten. |

<figure><img src="../../../.gitbook/assets/image (2339).png" alt=""><figcaption></figcaption></figure>

### SAP Datasphere

**SAP Datasphere** is where Datasphere packages, such as views and models, are tracked and moved between tenants.

| Role Action                      | What it does                                                                   |
| -------------------------------- | ------------------------------------------------------------------------------ |
| Add/Remove Packages from Project | Lets the user choose which Datasphere packages the project manages.            |
| Sync Package from Environment    | Pulls the latest packages from the Datasphere tenant.                          |
| Assign User Story to SDS Package | Links a Datasphere package to a user story so it moves along with that story.  |
| Edit SDS Package Configuration   | Lets the user change a package's settings for each environment.                |
| ImportSettings                   | Lets the user set how Datasphere packages are imported into the target tenant. |

<figure><img src="../../../.gitbook/assets/image (2340).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (2341).png" alt=""><figcaption></figcaption></figure>

### SAP Public Cloud

**SAP Public Cloud** is where S/4HANA Public Cloud artifacts are tracked and moved between systems.

| Role Action                       | What it does                                                                      |
| --------------------------------- | --------------------------------------------------------------------------------- |
| Add/Remove Artifacts from Project | Lets the user choose which Public Cloud artifacts the project manages.            |
| Sync Artifact from Environment    | Pulls the latest artifacts from the Public Cloud system.                          |
| Assign User Story to PC Artifact  | Links a Public Cloud artifact to a user story so it moves along with that story.  |
| ImportSettings                    | Lets the user set how Public Cloud artifacts are imported into the target system. |

<figure><img src="../../../.gitbook/assets/image (2342).png" alt=""><figcaption></figcaption></figure>

### Central Business Configuration

**Central Business Configuration** is where CBC configuration content is tracked and moved between systems.

| Role Action                       | What it does                                                             |
| --------------------------------- | ------------------------------------------------------------------------ |
| Sync Artifact from Environment    | Pulls the latest CBC configuration artifacts from the system.            |
| Assign User Story to CBC Artifact | Links a CBC artifact to a user story so it moves along with that story.  |
| ImportSettings                    | Lets the user set how CBC artifacts are imported into the target system. |

<figure><img src="../../../.gitbook/assets/image (2343).png" alt=""><figcaption></figcaption></figure>

### RAP Application

**RAP Application** is where ABAP RESTful (RAP) applications are added to a project and managed there.

| Role Action            | What it does                                             |
| ---------------------- | -------------------------------------------------------- |
| Create RAP Application | Lets the user add a new RAP application to the project.  |
| Edit RAP Application   | Lets the user change a RAP application's settings.       |
| Delete RAP Application | Lets the user remove a RAP application from the project. |

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

### BTP Application

**BTP Application** is where SAP BTP applications, such as CAP or MTA apps, are added to a project and set up for build and deployment.

| Role Action            | What it does                                                                       |
| ---------------------- | ---------------------------------------------------------------------------------- |
| Create BTP Application | Lets the user add a new BTP application to the project.                            |
| Edit BTP Application   | Lets the user change a BTP application's repository, build or deployment settings. |
| Delete BTP Application | Lets the user remove a BTP application from the project.                           |

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

### Test Automation

**Test Automation** is where automated tests are set up and run to check changes before they move forward.

| Role Action               | What it does                                                                  |
| ------------------------- | ----------------------------------------------------------------------------- |
| Create Test Configuration | Lets the user set up a new automated test suite or connection to a test tool. |
| Edit Test Configuration   | Lets the user change an existing test setup.                                  |
| Run Test Configuration    | Runs the automated tests.                                                     |
| Delete Test Configuration | Lets the user permanently remove a test setup.                                |

<figure><img src="../../../.gitbook/assets/image (2344).png" alt=""><figcaption></figcaption></figure>
