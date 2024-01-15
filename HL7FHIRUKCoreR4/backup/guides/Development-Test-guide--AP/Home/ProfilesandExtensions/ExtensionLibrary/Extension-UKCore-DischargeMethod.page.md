---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DischargeMethod
---
## StructureDefinition Extension-UKCore-DischargeMethod

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreDischargeMethod'
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
  <b>Discharge Method</b>- An example to illustrate the extension for an encounter to support the method of discharge from a hospital.<br>
  {{pagelink:Example-UKCore-Extension-DischargeMethod}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-DischargeMethod/~issues?level=File">Report Issue for Extension-UKCore-DischargeMethod</a>.
</div>


<h3 id="guidance-dischargeme">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-DischargeMethod}}.

---