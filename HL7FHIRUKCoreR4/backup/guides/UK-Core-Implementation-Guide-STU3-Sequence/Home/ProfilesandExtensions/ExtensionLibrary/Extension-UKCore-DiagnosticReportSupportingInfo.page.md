---
subject: http://hl7.org/fhir/5.0/StructureDefinition/extension-DiagnosticReport.supportingInfo
---
## StructureDefinition Extension-UKCore-DiagnosticReportSupportingInfo

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreDiagnosticSupportingInfo'
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
  <b>TBC</b>
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-DiagnosticReportSupportingInfo/~issues?level=File">Report Issue for Extension-UKCore-DiagnosticReportSupportingInfo</a>.
</div>

<h3 id="guidance-diagnosticreportsupportinginfo">Extension Specific Guidance</h3>

Where possible, it is expected that the resource being referenced SHOULD conform to one of the following UK Core profiles:

- [http://hl7.org/fhir/StructureDefinition/Citation](Citation)
- {{pagelink:Profile-DiagnosticReport}}
- {{pagelink:Profile-Observation}}
- {{pagelink:Profile-Procedure}}


---