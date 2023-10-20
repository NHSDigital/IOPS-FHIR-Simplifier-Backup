### Overview
Simplifier is the chosen platform for NHS England IG development. Further information about Simplifier can be found on the [Simplifier homepage](https://simplifier.net).

### Simplifier Projects
The NHS England IG [Project](https://simplifier.net/nhs-england-implementation-guide) consists of a collection of FHIR assets and a number of published Implementation Guides. These are developed and released using the Simplifier platform in an [organisation account](https://simplifier.net/organization/nhsdigital) owned by NHS England. 


### Simplifier Implementation Guides

There will be one IG in development and several published guides. There will be a version IG detailing the versions that are published etc.

### Overview of GitHub Setup

This section gives a brief overview on how GitHub and Simplifier is integrated with each other. Simplifier has the functionality of linking a project with one branch within one GitHub repository. In the case of the NHS England Implementation Guide project, Simplifier points to the stu1_develop branch within the NHS England FHIR Implementation Guide repository in GitHub. 

The FHIR assets on GitHub are manually imported into Simplifier using the 'Reimport' function. However, files such as diagrams are not stored in GitHub and are imported manually via Simplifier File Manager.

The current approach is illustrated below:
<br>

{{render:GitHubSetup}}

Diagram 1: Re-import FHIR assets from GitHub into Simplifier 

Diagram 2: Import images/diagrams into Simplifier via File Manager


{{render:ToolingPlatformsetup}}
{{render:ToolingPlatformsetup2}}

---
