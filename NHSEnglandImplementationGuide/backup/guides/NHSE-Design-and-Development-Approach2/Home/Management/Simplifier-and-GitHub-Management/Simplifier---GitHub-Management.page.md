

### Overview
Simplifier is the chosen platform for NHS England IG development. Further information about Simplifier can be found on the [Simplifier homepage](https://simplifier.net).

### Simplifier Projects
The NHS England IG [Project](https://simplifier.net/nhs-england-implementation-guide) consists of a collection of FHIR assets and a number of published Implementation Guides. These are developed and released using the Simplifier platform in an [organisation account](https://simplifier.net/organization/nhsdigital) owned by NHS England. 


### Simplifier Implementation Guides

There will be one IG in development and several published guides. There will be a version IG detailing the versions that are published etc.

### Overview of GitHub Setup
This section gives a brief overview of how GitHub is used with Simplifier for version control of the NHS England FHIR assets. Simplifier has the functionally of linking a project with a GitHub repository. The components of a NHS England Implementation Guide are managed in either GitHub or Simplifier. The Simplifier Project will contain all components but will not be the master for many. The current approach is illustrated below:

{{render:ToolingPlatformsetup}}
{{render:ToolingPlatformsetup2}}

Simplifier will synchronise the project every time a commit(change) is detected in the master branch of the GitHub repository, this is standard behaviour and is not detailed in this guide but further information is contained in the [Firely documentation](https://docs.fire.ly/projects/Simplifier/data_governance_and_quality_control/simplifierGithub.html#). 

---
