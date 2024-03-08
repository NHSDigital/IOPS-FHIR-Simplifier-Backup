---
subject: https://fhir.nhs.uk/England/StructureDefinition/Extension-England-FlagRemovalReason
---

## StructureDefinition Extension-England-FlagRemovalReason

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionEnglandFlagRemovalReason'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```
</div>

<table id="addToTranspose">
<tr><td>Context of Use: </td>
<td><a href='https://simplifier.net/guide/ukcoreimplementationguideassetsindevelopment/Home/ProfilesandExtensions/Profile-UKCore-Flag' target="_blank">Flag</td>
</tr>
</table>
<br>

{{render:Home-Profiles-and-Extensions-ExtensionsTemplate}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  Various Examples to illustrate the outcome of an attempted system operation on flag status, error or warning codes in response to a request.
<h4><a href='https://simplifier.net/guide/Female-Genital-Mutilation-Implementation-Guide2/Home/Build/Examples' target="_blank">Examples-Female-Genital-Mutilation (FGM)</a></h4>
</div>

<div id="Feedback" class="tabcontent">
<h4><a href='https://simplifier.net/NHS-England-Implementation-Guide/Extension-England-FlagRemovalReason/~issues?level=File' target="_blank">Propose a change to Extension-England-FlagRemovalReason</a></h4>
</div>

<h3>Extension Specific Guidance</h3>
There is a binding within this extension to {{pagelink:ValueSet-England-FlagRemovalReason}}

---
    