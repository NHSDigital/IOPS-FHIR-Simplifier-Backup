---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeviceReference
---
## StructureDefinition Extension-UKCore-DeviceReference


<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreDeviceReference'
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
<td>{{pagelink:Profile-DiagnosticReport,text:DiagnosticReport.performer}}<br>
{{pagelink:Profile-DiagnosticReport,text:DiagnosticReport.resultsInterpreter}}</td>
</tr>
</table>

{{page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Device Reference</b> - An example to illustrate the extension which is used to indicate the performer of a Diagnostic Report was software as a medical device.<br>
  {{pagelink:Example-UKCore-Extension-DeviceReference}}<br>
  NOTE: The above example references {{pagelink:Example-UKCore-Device-SoftwareAsAMedicalDevice}}
  <br><br>
</div>
<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/Extension-UKCore-DeviceReference/~issues?level=File">Report Issue for Extension-UKCore-DeviceReference</a>.
</div>

<h3 id="guidance-devicereference">Extension Specific Guidance</h3>
Where possible, it is expected that the resource being referenced SHOULD conform to [UKCore-Device](https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/ProfileUKCore-Device?version=current).

---