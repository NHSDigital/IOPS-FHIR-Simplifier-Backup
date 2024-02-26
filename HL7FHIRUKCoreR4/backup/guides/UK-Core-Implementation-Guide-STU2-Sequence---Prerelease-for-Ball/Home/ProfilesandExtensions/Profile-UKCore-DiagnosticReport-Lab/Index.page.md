---
topic: Profile-DiagnosticReport-Lab-56818
---

# StructureDefinition-UKCore-DiagnosticReport-Lab

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreDiagnosticReportLab'
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
	name = 'UKCoreDiagnosticReportLab'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Diagnostic Studies Report</b> - An example to illustrate a diagnostic studies report containing a specimen and observation for a patient.<br/>
{{pagelink:Example-UKCore-DiagnosticReport-Lab-DiagnosticStudiesReport}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core DiagnosticReport Lab profile:

- Query for a specific patient laboratory test result
- Query for recent laboratory test results
- Record or update a laboratory test result

Services that should consider using the  UK Core DiagnosticReport profile are:

- Lab Result

The DiagnosticReport-Lab profile is expected to reference either:
- a set of laboratory observations (Observation-Lab) that are grouped under one observation (Observation-LabGroup), for example a urea and electrolyte test that contains many sub tests,
- a single laboratory observation (Observation-Lab) that does not form part of a group of tests, for example Serum ferritin level,
- combinations of the above, for example a blood test may include multiple grouped tests such as Urea and electrolytes, Liver function tests, Full blood count, each having a single instance of Observation-LabGroup, along with single tests such as Serum C reactive protein level, eGFR using creatinine and Serum ferritin level, each having a single instance of Observation-Lab.

<br>
The workflow below shows a possible way to group a set of related laboratory observations into the derived {{pagelink:Profile-Observation-Group-67431}}, which is then referenced within a diagnostic report. Seperate laboratory observations MAY be directly referenced within the diagnostic report.
<br>

{{render: Derived-Profiles-Lab-Example }}{: .img-responsive }

<br>
Depending upon the countries or trusts workflow, an alternative is to have any separate laboratory observations referenced in a {{pagelink:Profile-Observation-Group-67431}} before being referenced in the diagnostic report. Although this creates extra resources it standardises the workflow. 

{{render:Derived-Profiles-Lab-Example-Extra-Group}}{: .img-responsive }

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
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
<td>The subject of the report - a patient</td>
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
</div>

---