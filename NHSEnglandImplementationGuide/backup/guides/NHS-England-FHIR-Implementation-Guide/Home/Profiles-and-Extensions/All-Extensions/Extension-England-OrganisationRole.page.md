---
subject: https://fhir.nhs.uk/England/StructureDefinition/Extension-England-OrganisationRole
---

## StructureDefinition Extension-England-OrganisationRole

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionEnglandOrganisationRole'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>

<table id="addToTranspose">
<tr><td>Context of Use: </td>
<td><a href='https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization' target="_blank">Organization</a>, <a href='https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/Profile-UKCore-OrganizationAffiliation' target="_blank">OrganizationAffiliation</a></td>
</tr>
</table>
<br>

{{render:Home-Profiles-and-Extensions-ExtensionsTemplate}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  None provided at this time.
</div>

<div id="Feedback" class="tabcontent">
<h4><a href='https://simplifier.net/NHS-England-Implementation-Guide/Extension-England-OrganisationRole/~issues?level=File' target="_blank">Propose a change to Extension-England-OrganisationRole</a></h4>
</div>

<h3>Extension Specific Guidance</h3>
There is a binding within this extension to {{pagelink:ValueSet-England-OrganisationRole}}

---
    