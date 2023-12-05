---
topic: Profile-Composition
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition
---

# StructureDefinition-UKCore-Composition

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreComposition'
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
	name = 'UKCoreComposition'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Discharge</b> - An example to illustrate a composition containing a discharge summary.<br/>
{{pagelink:Example-UKCore-Composition-Discharge}}
<br/><br/>
<b>CareSetting Type</b> - An example to illustrate the care setting of a FHIR document.<br/>
{{pagelink:Example-UKCore-Extension-CareSettingType}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Composition/~issues?level=File">Report Issue for UKCore-Composition</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Composition profile:

- Query for a specific patient document or document type
- Query for recent patient documents
- Create a new document or update an existing document 

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

<h3> Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Composition.status</code></td>
<td>The workflow/clinical status of this composition.</td>
</tr>
<tr>
<td><code>Composition.type</code></td>
<td>Specifies the particular kind of composition.</td>
</tr>
<tr>
<td><code>Composition.subject</code></td>
<td>Who and/or what the composition is about.</td>
</tr>
<tr>
<td><code>Composition.author</code></td>
<td>Identifies who is responsible for the information in the composition.</td>
</tr>
<tr>
<td><code>Composition.confidentiality</code></td>
<td>The code specifying the level of confidentiality of the Composition.</td>
</tr>
<tr>
<td><code>Composition.custodian</code></td>
<td>Identifies the organization or group who is responsible for ongoing maintenance of and access to the composition/document information.</td>
</tr>
</table>

---
