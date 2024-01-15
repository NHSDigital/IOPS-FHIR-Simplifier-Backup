---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationPrescribingOrganizationType
---
## StructureDefinition Extension-UKCore-MedicationPrescribingOrganizationType

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreMedicationPrescribingOrganizationType'
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
<td>{{pagelink:Profile-MedicationStatement,text:MedicationStatement}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}


<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Prescribing Organisation</b>- An example to illustrate the type of organisation or setting responsible for authorising and issuing a medication, but not the organisation or setting delivering the patient care.<br>
  {{pagelink:Example-UKCore-Extension-MedicationPrescribingOrganizationType}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-MedicationPrescribingOrganizationType/~issues?level=File">Report Issue for Extension-UKCore-MedicationPrescribingOrganizationType</a>.
</div>


<h3 id="guidance-medicationprescribingorganizationtype">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-MedicationPrescribingOrganizationType}}.

---