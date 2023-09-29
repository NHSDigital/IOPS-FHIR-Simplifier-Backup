## {{page-title}}


The profile is provided for implementation guidance:
- a returned UKCore-PractitionerRole resource will not reference the profile in the Resource.meta. 

<br>

## Conformance Rules

PratitionerRole resources are returned as included resources as part of a GET /AuditEvent interaction.

A searchset Bundle will be returned on the GET /AuditEvent interaction ({{pagelink:Home/Design/Interactions.page.md}}). 

The Bundle will contain 0 to Many CareTeam resources matching the NHSNumber searchParmeter and 0 to Many resources matching  included PractitionerRole resources.

<iframe src="https://simplifier.net/guide/uk-core-implementation-guide-stu3-sequence/home/profilesandextensions/profile-ukcore-operationoutcome?version=current" frameBorder="0" height="800px" width="100%"></iframe>


