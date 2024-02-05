---
topic: Profile-DiagnosticReport
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport
usage: http://hl7.org/fhir/StructureDefinition/DiagnosticReport
issue: UKCore-DiagnosticReport
---

# StructureDefinition-UKCore-DiagnosticReport

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Composition Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to send a composition resource with a diagnostic report.<br>
  {{pagelink:Example-UKCore-Extension-CompositionReference}}
  <br><br>
  <b>Diagnostic Report Note</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to add notes and annotations to a diagnostic report.<br>
  {{pagelink:Example-UKCore-Extension-Note}}
  <br><br>
  <b>Diagnostic Studies Report</b> - An example to illustrate a diagnostic studies report containing a specimen and observation for a patient.<br/>
{{pagelink:Example-UKCore-DiagnosticReport-Lab-DiagnosticStudiesReport}}
<br><br>
 <b>Device Reference</b> - An example to illustrate the extension which is used to indicate the performer of a Diagnostic Report was a device.<br>
  {{pagelink:Example-UKCore-Extension-DeviceReference}}<br>
  NOTE: The above example references {{pagelink:Example-UKCore-Device-SoftwareAsAMedicalDevice}}
</div>
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core DiagnosticReport profile:

- Query for a specific patient test result
- Query for recent test results
- Record or update a test result

Services that should consider using the  UK Core DiagnosticReport profile are:

- Pathology
- Genomics
- Lab Result

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

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
</div>

---
