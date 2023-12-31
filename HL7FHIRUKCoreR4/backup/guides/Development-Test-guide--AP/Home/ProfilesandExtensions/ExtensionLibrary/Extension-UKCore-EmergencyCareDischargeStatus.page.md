---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-EmergencyCareDischargeStatus
---
## StructureDefinition Extension-UKCore-EmergencyCareDischargeStatus

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreEmergencyCareDischargeStatus'
select
	Canonical_URL: url,
  Status: status,
  Current_Version: version,
  Last_Updated: date,
	Description: description,
	Profile_Purpose: purpose
```
</div>
<br>

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-Encounter,text:Encounter}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Emergency Care Discharge Status</b>- An example to illustrate the extension which is used to indicate the status of an individual on discharge from an Emergency Care Department.<br>
  {{pagelink:Example-UKCore-Extension-EmergencyCareDischargeStatus}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-EmergencyCareDischargeStatus/~issues?level=File">Report Issue for Extension-UKCore-EmergencyCareDischargeStatus</a>.
</div>

<h3 id="guidance-emergencycaredischargestatus">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-EmergencyCareDischargeStatus}}.

---