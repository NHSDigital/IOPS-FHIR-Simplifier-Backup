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
<td><a href='https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization?version=current' target="_blank">Organization</td>
</tr>
</table>
<br>

{{render:Home-Profiles-and-Extensions-ExtensionsTemplate}}



<h3>Extension Specific Guidance</h3>
There is a binding within this extension to <a href='https://simplifier.net/guide/nhs-england-implementation-guide-stu1/home/terminology/all-valuesets/valueset-england-DateTime.page.md?version=current' target="_blank">ValueSet-England-PeriodType</a>.

---
    