---
topic: Profile-DiagnosticReport-54417
---

# StructureDefinition-UKCore-DiagnosticReport

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreDiagnosticReport'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'UKCoreDiagnosticReport'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Composition Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to send a composition resource with a diagnostic report.<br>
  {{pagelink:Example-UKCore-DiagnosticReport-Extension-CompositionReference}}
  <br><br>
  <b>CT Chest Scan Report</b> - An example to illustrate a diagnostic report containing an imaging study for a patient.<br/>
{{pagelink:Example-UKCore-DiagnosticReport-CTChestScan}}<br>
  NOTE: The above example references {{pagelink:Example-UKCore-ImagingStudy-CTChestScan}}
  <br><br>
  <b>Diagnostic Report Note</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to add notes and annotations to a diagnostic report.<br>
  {{pagelink:Example-UKCore-DiagnosticReport-Extension-Note}}
  <br><br>
  <b>Diagnostic Studies Report</b> - An example to illustrate a diagnostic studies report containing a specimen and observation for a patient.<br/>
{{pagelink:Example-UKCore-DiagnosticReport-Lab-DiagnosticStudiesReport}}
<br><br>
 <b>Device Reference</b> - An example to illustrate the extension which is used to indicate the performer of a Diagnostic Report was a device.<br>
  {{pagelink:Example-UKCore-DiagnosticReport-Extension-DeviceReference}}<br>
  NOTE: The above example references {{pagelink:Example-UKCore-Device-SoftwareAsAMedicalDevice}}
<br><br>
  <b>ECG Report</b> - An example to illustrate a diagnostic report for an ECG.<br/>
{{pagelink:Example-UKCore-DiagnosticReport-ECG}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core DiagnosticReport profile:

- Query for a specific patient test result
- Query for recent test results
- Record or update a test result

Services that should consider using the  UK Core DiagnosticReport profile are:

- Pathology
- Genomics
- Lab Result

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>DiagnosticReport.status</code></td>
<td>The status of the diagnostic report.
</td>
</tr>
<tr>
<td><code>DiagnosticReport.category</code></td>
<td>A code that classifies the clinical discipline, department or diagnostic service that created the report.</td>
</tr>
<tr>
<td><code>DiagnosticReport.code</code></td>
<td>A code or name that describes this diagnostic report.</td>
</tr>
<tr>
<td><code>DiagnosticReport.subject</code></td>
<td>The subject of the report - usually, but not always, the patient</td>
</tr>
<tr>
<td><code>DiagnosticReport.encounter</code></td>
<td>Health care event when test ordered.</td>
</tr>
<tr>
<td><code>DiagnosticReport.issued</code></td>
<td>Clinically relevant time/time-period for report.</td>
</tr>
<tr>
<td><code>DiagnosticReport.result</code></td>
<td>Observations that are part of this diagnostic report.</td>
</tr>
</table>

---
