---
topic: Profile-ImagingStudy
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-ImagingStudy
usage: http://hl7.org/fhir/StructureDefinition/ImagingStudy
issue: UKCore-ImagingStudy
---
# StructureDefinition-UKCore-ImagingStudy

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>CT Chest Scan</b> - An example to illustrate sharing CT scan imagery.<br>
{{pagelink:Example-UKCore-ImagingStudy-CTChestScan}}
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Imaging Study profile:

- <i>Query and share DICOM images</i>

<hr class="thickline">

## Profile Specific Implementation Guidance: ##


### Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>ImagingStudy.status</code></td>
<td>The current state of the ImagingStudy.</td>
</tr>
<tr>
<td><code>ImagingStudy.modality</code></td>
<td>All series modality if actual acquisition modalities.</td>
</tr>
<tr>
<td><code>ImagingStudy.subject</code></td>
<td>Who or what is the subject of the study.</td>
</tr>
<tr>
<td><code>ImagingStudy.encounter</code></td>
<td>The encounter with which this imaging study is associated</td>
</tr>
<tr>
<td><code> ImagingStudy.series</code></td>
<td>Each study has one or more series of images or other content.</td>
</tr>
</table>
</div>

---