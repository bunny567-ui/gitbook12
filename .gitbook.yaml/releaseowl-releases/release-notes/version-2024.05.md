# Version 2024.05

The **2024.05** release focuses on a variety of enhancements, bug fixes, and new features designed to improve the release pipeline. This update includes improvements to the import functionality, conflict resolution during deployments, backend optimizations, and updates to the user interface.

### **Release Notes**

| **Date**        | <p>17 Oct 2024</p><p><br></p>                                                                                                         |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| **Version**     | hotfix-2024-04-1                                                                                                                      |
| **Description** | This hotfix addresses key improvements in import parameter handling, transport domain preferences, and sprint synchronization issues. |

### **Bug Fixes and Enhancements**

Before you share the page, review the contents of each Jira issue and remove any sensitive data.

| **Issue** | **Summary**                                                                                         | **Issue Type** |
| --------- | --------------------------------------------------------------------------------------------------- | -------------- |
| RP-934    | Notify users checkbox should be on top of schedule time checkbox in deployment task                 | Bug            |
| RP-933    | Peer review checkbox should be only for CPI and Multiverse project types                            | Bug            |
| RP-931    | UI changes to release pipeline both design time and runtime                                         | Story          |
| RP-930    | Backend implementation for the gcts branch switch                                                   | Story          |
| RP-926    | Exception when a smartForm TR is being retrofitted that does not have any conflicts.                | Bug            |
| RP-922    | Retrofit: Status is not changing to In progress and null pointer exception for validation report    | Story          |
| RP-914    | In build pipeline check for sap cves                                                                | Story          |
| RP-913    | CVEs Table (Create, Read, Update, Delete) in project settings                                       | Story          |
| RP-912    | A separate gcts merge task in release pipeline                                                      | Story          |
| RP-911    | A Separate toc deploy task in release pipeline                                                      | Story          |
| RP-909    | Retrofit: Retrofit is started but getting information popup as not started.                         | Story          |
| RP-906    | Provide implementation of merge conflict resolution and pushing the changes to Repository.          | Story          |
| RP-905    | UI Changes related to conflict resolution screen that occur during Merge operation.                 | Story          |
| RP-904    | Backend changes in rate-workflow for handling Merge operation.                                      | Story          |
| RP-903    | Backend changes in rate-workflow and rate-sap-tms-server for implementing Merge Operation           | Story          |
| RP-902    | Provide an option to add "Merge" operation as separate task in release pipeline UI                  | Story          |
| RP-901    | Backend changes in rate-workflow and rate-sap-tms-server for release transport request              | Story          |
| RP-900    | Changes in the release pipeline UI to add "Release Transport Request" task                          | Story          |
| RP-899    | Backend changes related to rate-workflow and rate-tms-server                                        | Story          |
| RP-898    | Changes in Release Pipeline UI                                                                      | Story          |
| RP-897    | Provide a separate workflow task for performing a branch merge operation.                           | Story          |
| RP-896    | A separate workflow task for releasing Transport request                                            | Story          |
| RP-895    | Current onPremise deploy task should have an option to import via TOC                               | Story          |
| RP-892    | UI changes related to Aborted status in ReleasePipeline instance.                                   | Story          |
| RP-891    | Userstory report generation                                                                         | Story          |
| RP-889    | Default import parameters in env creation                                                           | Story          |
| RP-888    | Import params at TransportDomain controller level, and order of preference is TR, Env, then default | Story          |
| RP-887    | FreshService integration                                                                            | Story          |
| RP-886    | Closed sprints are not syncing                                                                      | Bug            |
| RP-885    | Malware check is not visible for bsp apps                                                           | Story          |
| RP-876    | Import Settings Not Functioning Correctly for Group Import                                          | Bug            |
| RP-873    | Unable to Differentiate Projects with Same Release Pipeline name                                    | Bug            |
| RP-872    | User role validation issue at deployment                                                            | Bug            |
| RP-871    | Unable to upload the Fiori build to backend system.                                                 | Bug            |
| RP-868    | Import log not getting added to the toc created during import via toc option in releaseowl          | Bug            |
| RP-865    | Creating a new release pipeline with an existing name updates the existing pipeline instead         | Bug            |
| RP-849    | Rest API for aborting a process                                                                     | Story          |
| RP-841    | Integration Flow Mock testing                                                                       | Story          |
| RP-840    | Generate Userstory ChangeLog in the form of PDF                                                     | Story          |
| RP-831    | Sequence of Deployment: TR, CPI, SAC, SDS, API proxies, MTAR                                        | Story          |
| RP-812    | Retrofit view and apis                                                                              | Story          |
| RP-809    | TOC - Add objects based on Versioning                                                               | Story          |
| RP-805    | Validate TR before retrofit starts.                                                                 | Story          |
| RP-804    | Object syntax validation after conflict resolution.                                                 | Story          |
| RP-799    | In Retrofit conflict screen, Object content should come from object version associated to the TR    | Story          |
| RP-784    | All Apps should start independent of rate-admin-server                                              | Story          |
| RP-783    | Miscellaneous ECC                                                                                   | Story          |
| RP-782    | Miscellaneous S4                                                                                    | Story          |
| RP-781    | Retrofit ECC                                                                                        | Story          |
| RP-780    | Retrofit S4                                                                                         | Story          |
| RP-779    | ABAP Package for Retrofit and Miscellaneous Changes New Patch                                       | Story          |
| RP-766    | BTP: Release pipeline deploy logs show Success, but pipeline is failed (QA Env)                     | Bug            |
| RP-706    | RO backend implementation of the new SAP On-premise API                                             | Story          |
| RP-696    | Need user story details at release pipeline execution level                                         | Task           |
| RP-676    | CPI: Naming convention for artifacts                                                                | Bug            |
| RP-660    | CPI Value Mapping: Status fails if name/ID have spaces in redeploy                                  | Bug            |
| RP-612    | ATC variant configuration in ReleaseOwl                                                             | Task           |
| RP-592    | Implementation                                                                                      | Story          |
| RP-591    | Analysis                                                                                            | Story          |
| RP-590    | Events via Redis for external/internal app communication                                            | Story          |
| RP-580    | Implementation                                                                                      | Story          |
| RP-579    | Analysis                                                                                            | Story          |
| RP-578    | TR auto sequencing based on TR validation and Buffer sequencing.                                    | Story          |
| RP-572    | Implementation                                                                                      | Story          |
| RP-571    | Solution Design                                                                                     | Story          |
| RP-570    | Analysis                                                                                            | Story          |
| RP-569    | BPCA Integration                                                                                    | Story          |

