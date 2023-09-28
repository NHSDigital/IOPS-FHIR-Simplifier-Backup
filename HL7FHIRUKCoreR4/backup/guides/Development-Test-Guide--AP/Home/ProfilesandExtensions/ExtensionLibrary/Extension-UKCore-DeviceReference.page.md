## StructureDefinition Extension-UKCore-DeviceReference


<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'ExtensionUKCoreDeviceReference'
select
	Canonical_URL: url,
	Description: description,
	Profile_Purpose: purpose
```

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{{pagelink:Profile-DiagnosticReport,text:DiagnosticReport.performer}}<br>
{{pagelink:Profile-DiagnosticReport,text:DiagnosticReport.resultsInterpreter}}</td>
</tr>
</table>

</div>
<br>

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Tree View" class="tabcontent" style="display:block">
  <h3>Tree View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeviceReference}}
</div>
<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeviceReference}}
</div>
<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeviceReference}}
</div>
<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-DeviceReference}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Device Reference</b> - An example to illustrate the extension which is used to indicate the performer of a Diagnostic Report was software as a medical device.<br>
  {{pagelink:Example-UKCore-DiagnosticReport-Extension-DeviceReference}}<br>
  NOTE: The above example references {{pagelink:Example-UKCore-Device-SoftwareAsAMedicalDevice}}
  <br><br>
</div>

### Guidance
The resource being referenced SHALL conform to the following [Profile UKCore-Device](https://simplifier.net/hl7fhirukcorer4/ukcoredevice).

---