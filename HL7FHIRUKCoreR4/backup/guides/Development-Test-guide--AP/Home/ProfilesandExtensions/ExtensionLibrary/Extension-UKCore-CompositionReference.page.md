---
subject: http://hl7.org/fhir/5.0/StructureDefinition/extension-DiagnosticReport.composition
---

## StructureDefinition Extension-UKCore-CompositionReference

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreCompositionReference'
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
<td>{{pagelink:Profile-DiagnosticReport,text:DiagnosticReport}}</td>
</tr>
</table>

</div>
<br>


{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Composition Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to send a composition resource with a diagnostic report.<br>
  {{pagelink:Example-UKCore-Extension-CompositionReference}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-CompositionReference/~issues?level=File">Report Issue for Extension-UKCore-CompositionReference</a>.
</div>

---