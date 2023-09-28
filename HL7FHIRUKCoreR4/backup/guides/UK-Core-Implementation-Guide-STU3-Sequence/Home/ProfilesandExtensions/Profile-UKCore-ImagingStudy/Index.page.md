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
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json}}
</div>

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