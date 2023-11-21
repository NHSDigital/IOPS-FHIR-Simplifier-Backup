---
topic: Profile-Specimen
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen
---

# StructureDefinition-UKCore-Specimen

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreSpecimen'
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
	name = 'UKCoreSpecimen'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'Detailed')">Detailed</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
  <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table}}
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
<b>Blood Specimen</b> - An example to illustrate a blood specimen for a patient.<br/>
{{pagelink:Example-UKCore-Specimen-BloodSpecimen}}
<br><br>
<b>Composition Reference</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to reference a Patient or RelatedPerson within Specimen.collection.collector.<br>
{{pagelink:Example-UKCore-Extension-CollectionCollector}}
<br><br>
<b>High Risk Specimen</b> - An example to illustrate using the HL7 core-defined Extension specimen-specialHandling to record why a specimen should be treated as a high risk.<br/>
{{pagelink:Example-UKCore-Extension-SpecialHandling}}
<br><br>
<b>Median Cubital Vein</b> - An example to illustrate the extension for a referenced body site.<br>
{{pagelink:Example-UKCore-Extension-BodySiteReference}}
<br><br>
<b>Sample Category</b> - An example to illustrate the extension to show the Genomics classification of a sample.<br>
{{pagelink:Example-UKCore-Extension-SampleCategory}}
<br><br>
<b>Urine Sample</b> - An example to illustrate a urine specimen for a patient.<br>
{{pagelink:Example-UKCore-Specimen-UrineSpecimen}}
</div>


<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen'
```
</span>
</div>

<div id="Detailed" class="tabcontent">
  <h3>Detailed Descriptions</h3>
{{dict}}
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Specimen/~issues?level=File">Report Issue for UKCore-Specimen</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Specimen profile:

- Query for specimen information
- Exchange specimen information used in Observations and DiagnosticReport

<hr class="thickline">

## Profile Specific Implementation Guidance: ##



<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Specimen.status</code></td>
<td>The availability of the specimen.</td>
</tr>
<tr>
<td><code>Specimen.type</code></td>
<td>The kind of material that forms the specimen.</td>
</tr>
<tr>
<td><code>Specimen.subject</code></td>
<td>Where the specimen came from.</td>
</tr><tr>
<td><code>Specimen.receivedTime</code></td>
<td>The time when specimen was received for processing.</td>
</tr><tr>
<td><code>Specimen.request</code></td>
<td>Why the specimen was collected.</td>
</tr>
</table>

---