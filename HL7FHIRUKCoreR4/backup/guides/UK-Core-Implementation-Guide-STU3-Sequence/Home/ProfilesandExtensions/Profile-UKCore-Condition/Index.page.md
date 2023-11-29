---
topic: Profile-Condition
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition
---

# StructureDefinition-UKCore-Condition

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreCondition'
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
	name = 'UKCoreCondition'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Bleeding From Ear</b> - An example to illustrate a patient bleeding from ear.<br/>
{{pagelink:Example-UKCore-Condition-BleedingFromEar}}
<br/><br/>
<b>CodingSCT DescId</b> - An example to illustrate the extension which adds a SNOMED CT description Id to CodeableConcept.<br/>
{{pagelink:Example-UKCore-Extension-CodingSCTDescId}}
<br/><br/>
<b>Condition Episode</b> - An example to illustrate the extension which is used to indicate the episodicity status of a condition.<br/>
{{pagelink:Example-UKCore-Extension-ConditionEpisode}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Condition/~issues?level=File">Report Issue for UKCore-Condition</a>.
</div>
</nocheck>


### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Condition profile:

- Query for a Patient’s current or historical conditions
- Record or update a Patient’s conditions

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
<td><code>Condition.clinicalStatus</code></td>
<td>The clinical status of the condition.</td>
</tr>
<tr>
<td><code>Condition.verificationStatus</code></td>
<td>The verification status to support the clinical status of the condition.</td>
</tr>
<tr>
<td><code>Condition.severity</code></td>
<td>A subjective assessment of the severity of the condition as evaluated by the clinician.</td>
</tr>
<tr>
<td><code>Condition.code </code></td>
<td>Identification of the condition, problem or diagnosis.</td>
</tr>
<tr>
<td><code>Condition.subject</code></td>
<td>Indicates the patient or group who the condition record is associated with.</td>
</tr>
<tr>
<td><code>Condition.recorder</code></td>
<td>Individual who recorded the record and takes responsibility for its content.</td>
</tr>
</table>

---