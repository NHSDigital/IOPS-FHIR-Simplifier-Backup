---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-LegalStatus
---
## StructureDefinition Extension-UKCore-LegalStatus

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreLegalStatus'
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
<td>{{pagelink:Profile-Encounter,text:Encounter}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Legal Status</b>- An example to illustrate the extension which is used to indicate a patient's legal status on admission or discharge.<br>
  {{pagelink:Example-UKCore-Extension-LegalStatus}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-LegalStatus/~issues?level=File">Report Issue for Extension-UKCore-LegalStatus</a>.
</div>

<h3 id="guidance-legalstatus">Extension Specific Guidance</h3>
There are two bindings within this extension. `legalStatusContext` element to {{pagelink:ValueSet-UKCore-LegalStatusContext}}
, and `legalStatusClassification` element to {{pagelink:ValueSet-UKCore-LegalStatusClassification}}.

---