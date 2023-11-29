---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdmissionMethod
---
## StructureDefinition Extension-UKCore-AdmissionMethod

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreAdmissionMethod'
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
<td>{{pagelink:Profile-Encounter,text:Encounter.hospitalization}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Admission Method</b>- An example to illustrate the extension for an encounter to support the method by which an individual was admitted into hospital.<br>
  {{pagelink:Example-UKCore-Extension-AdmissionMethod}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-AdmissionMethod/~issues?level=File">Report Issue for Extension-UKCore-AdmissionMethod</a>.
</div>

<h3 id="guidance-admissionmethod">Extension Specific Guidance</h3>
There is a binding within this extension to a {{pagelink:ValueSet-UKCore-AdmissionMethod}}.

---