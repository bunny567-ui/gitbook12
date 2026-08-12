# Administration

Before an MTAR application can be created, the connections it relies on must exist. These are registered once in the Administration area and then referenced by name throughout the application and pipeline configuration.

### Registering Credentials

Two kinds of credentials are used by MTAR delivery:

•    SCM (Git) credentials — used to read the repository, create branches, raise pull requests, and merge. Typically a username plus a personal access token.

* SAP Cloud credentials — used by the build/deploy tooling to authenticate to the target SAP BTP environment

