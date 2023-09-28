---
topic: Profile-DiagnosticReport-Lab-56818
---

# StructureDefinition-UKCore-DiagnosticReport-Lab

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 6. This is a new Profile added to UK Core and should undergo review in this STU2 ballot.
</div>

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
{{pagelink:Example-UKCore-DiagnosticReport-DiagnosticStudiesReport}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core DiagnosticReport Lab profile:

- Query for a specific patient laboratory test result
- Query for recent laboratory test results
- Record or update a laboratory test result

Services that should consider using the  UK Core DiagnosticReport profile are:

- Lab Result

---

## Profile Specific Implementation Guidance: ##

This is a derived profile of {{pagelink:Profile-DiagnosticReport-54417}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.
<br><br>
The DiagnosticReport-Lab profile is expected to reference either:
- a set a laboratory observations (Observation-Lab) that are grouped under one observation (Observation-LabGroup), for example a urea and electrolyte test that contains many sub tests,
- a single laboratory observation (Observation-Lab) that does not form part of a group of tests, for example Serum ferritin level,
- combinations of the above, for example a blood test may include multiple grouped tests such as Urea and electrolytes, Liver function tests, Full blood count, each having a single instance of Observation-LabGroup, along with single tests such as Serum C reactive protein level, eGFR using creatinine and Serum ferritin level, each having a single instance of Observation-Lab.
<br><br>
{{render: Derived-Profiles-Lab-Example }}{: .img-responsive }


### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink:Profile-DiagnosticReport-54417}} table, along with the following.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>DiagnosticReport.performer</code></td>
<td>Responsible diagnostic service.</td>
</tr>
</table>

---