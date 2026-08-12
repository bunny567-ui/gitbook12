# SAP BTP

ReleaseOwl provides native, end-to-end CI/CD and change management for SAP Business Technology Platform (BTP) applications whose source code is maintained in Git. This guide describes how to configure and operate the delivery of MTA archive (MTAR) applications — for example applications built with the Cloud Application Programming model (CAP) — from a developer’s change all the way to production, including approvals, quality checks, hotfixes, and pull-request automation.

#### Supported Git providers

MTAR applications can be sourced from any of the following version control systems:

•    Bitbucket

•    GitHub

•    Azure DevOps

•    GitLab

#### Branching models

ReleaseOwl supports two branching strategies for delivering user-story changes. A given MTAR application uses exactly one of them — the two models are mutually exclusive and the model is fixed once the application is created.

<table data-header-hidden><thead><tr><th valign="top"></th><th valign="top"></th></tr></thead><tbody><tr><td valign="top">Model</td><td valign="top">How changes are captured and promoted</td></tr><tr><td valign="top">Feature Branch Model</td><td valign="top">The user associates a feature branch with the user story. As the user story advances through the release pipeline, that same feature branch is merged into each environment branch in turn (Development → QA → Production).</td></tr><tr><td valign="top">Cherry-Pick Model</td><td valign="top">The user selects the specific commits related to the user story. Commits are populated from the application’s development branch (the landscape branch flagged as “Development Branch”). Those commits are cherry-picked onto the target environment branches during promotion.</td></tr></tbody></table>

#### End-to-end configuration flow

The remainder of this guide follows the natural order in which objects are configured and used:

1\.   Register Credentials and Environments in the Administration area.

2\.   Create the MTAR Application and its Landscape Configuration.

3\.   Configure the Build Pipelines used by the landscape.

4\.   Add changes to a User Story — Feature Branch or Cherry-Pick.

5\.   Build the Release Pipeline and its tasks.

6\.   Promote User Stories and Release Packages.

7\.   Deliver Hotfixes (§9), resolve conflicts and handle failures.

8\.   Automate Pull-Request task completion with Git webhooks.

#### Prerequisites

•    A ReleaseOwl tenant with a Project created, and permission to configure applications and release pipelines.

•    A Git repository containing the MTAR application source, reachable from ReleaseOwl.

•    Git credentials (username + token/password) and the target SAP Cloud environment connection details, registered in the Administration area.

•    One or more Build Pipelines capable of producing the MTAR artifact.
