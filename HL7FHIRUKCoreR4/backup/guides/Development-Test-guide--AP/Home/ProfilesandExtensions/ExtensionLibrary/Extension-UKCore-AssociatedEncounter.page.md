---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AssociatedEncounter
---
## StructureDefinition Extension-UKCore-AssociatedEncounter

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreAssociatedEncounter'
select
	Canonical_URL: url,
  Status: status,
  Current_Version: version,
  Last_Updated: date,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-FamilyMemberHistory,text:FamilyMemberHistory}}</td>
</tr>
</table>

</div>
<br>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Associated Encounter</b> - An example to illustrate using the extension to indicate the encounter for which the family members condition was recorded.<br>
{{pagelink:Example-UKCore-Extension-AssociatedEncounter}}
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-AssociatedEncounter/~issues?level=File">Report Issue for Extension-UKCore-AssociatedEncounter</a>.
</div>


<h3 id="guidance-associatedencounter">Extension Specific Guidance</h3>
The resource being referenced SHALL conform to the following {{pagelink:Profile-Encounter}}.

---
