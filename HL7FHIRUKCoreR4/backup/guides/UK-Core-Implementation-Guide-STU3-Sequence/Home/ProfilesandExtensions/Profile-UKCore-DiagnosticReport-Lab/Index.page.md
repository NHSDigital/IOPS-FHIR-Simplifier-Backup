---
topic: Profile-DiagnosticReport-Lab
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab
usage: http://hl7.org/fhir/StructureDefinition/DiagnosticReport
issue: UKCore-DiagnosticReport-Lab
---

# StructureDefinition-UKCore-DiagnosticReport-Lab

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Diagnostic Studies Report</b> - An example to illustrate a diagnostic studies report containing a specimen and observation for a patient.<br/>
{{pagelink:Example-UKCore-DiagnosticReport-Lab-DiagnosticStudiesReport}}
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core DiagnosticReport Lab profile:

- Query for a specific patient laboratory test result
- Query for recent laboratory test results
- Record or update a laboratory test result

Services that should consider using the  UK Core DiagnosticReport profile are:

- Lab Result

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

This is a derived profile of {{pagelink:Profile-DiagnosticReport}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.
<br><br>
The DiagnosticReport-Lab profile is expected to reference either:
- a set of laboratory observations (Observation-Lab) that are grouped under one observation (Observation-LabGroup), for example a urea and electrolyte test that contains many sub tests,
- a single laboratory observation (Observation-Lab) that does not form part of a group of tests, for example Serum ferritin level,
- combinations of the above, for example a blood test may include multiple grouped tests such as Urea and electrolytes, Liver function tests, Full blood count, each having a single instance of Observation-LabGroup, along with single tests such as Serum C reactive protein level, eGFR using creatinine and Serum ferritin level, each having a single instance of Observation-Lab.
<br><br>

<div id="renderParent" title="Structure of Derived Lab Profiles">
{{render: Derived-Profiles-Lab-Example }}
</div>

---

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport}}.

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