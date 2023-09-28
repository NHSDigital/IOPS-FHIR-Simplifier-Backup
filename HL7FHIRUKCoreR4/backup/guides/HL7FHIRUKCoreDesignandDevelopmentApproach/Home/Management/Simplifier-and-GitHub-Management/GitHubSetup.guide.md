## {{page-title}}

### Overview of GitHub Setup
This section gives a brief overview of how GitHub is used with Simplifier for version control of the UK Core FHIR assets. Simplifier has the functionally of linking a project with a GitHub repository. The components of a UK Core Implementation Guide are managed in either GitHub or Simplifier. The Simplifier Project will contain all components but will not be the master for many. The current approach is illustrated below:

{{render:Github-setup}}

Simplifier will synchronise the project every time a commit(change) is detected in the master branch of the GitHub repository, this is standard behaviour and is not detailed in this guide but further information is contained in the [Firely documentation](https://docs.fire.ly/projects/Simplifier/data_governance_and_quality_control/simplifierGithub.html). 

---

