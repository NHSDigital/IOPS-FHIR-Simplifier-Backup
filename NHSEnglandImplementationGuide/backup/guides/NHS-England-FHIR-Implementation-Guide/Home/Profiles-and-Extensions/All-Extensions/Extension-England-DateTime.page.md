---
subject: https://fhir.nhs.uk/England/StructureDefinition/Extension-England-DateTime
---

## StructureDefinition Extension-England-DateTime

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionEnglandDateTime'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>

<table id="addToTranspose">
<tr><td>Context of Use: </td>
<td><a href='https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization?version=current' target="_blank">Organization</a>, <a href='https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/Profile-UKCore-OrganizationAffiliation?version=current' target="_blank">OrganizationAffiliation</a></td>
</tr>
</table>
<br>

{{render:Home-Profiles-and-Extensions-ExtensionsTemplate}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Note:</b>There is currently no example that uses this extension. An example will be added in a future release.<br>
</div>

<h3>Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-England-TypedDateTime}}.

---