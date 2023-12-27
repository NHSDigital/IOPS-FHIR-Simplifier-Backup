---
topic: Profile-ImagingStudy
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-ImagingStudy
---
# StructureDefinition-UKCore-ImagingStudy

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreImagingStudy'
select
	Canonical_URL: url,
  Status: status,
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
	name = 'UKCoreImagingStudy'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>CT Chest Scan</b> - An example to illustrate sharing CT scan imagery.<br>
{{pagelink:Example-UKCore-ImagingStudy-CT-ChestScan}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-ImagingStudy'
  and status = 'active'
```
</span>
<br><br>
  This Profile is referenced in the following Extensions: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-ImagingStudy'
```
</span>
<br><br>
  This Profile is referenced in the following Profiles: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type !='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-ImagingStudy'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-ImagingStudy/~issues?level=File">Report Issue for UKCore-ImagingStudy</a>.
</div>
</nocheck>

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

<hr class="thickline">