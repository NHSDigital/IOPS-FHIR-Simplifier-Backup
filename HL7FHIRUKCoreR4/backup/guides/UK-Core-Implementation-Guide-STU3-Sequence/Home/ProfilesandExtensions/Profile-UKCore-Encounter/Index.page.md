---
topic: Profile-Encounter
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter
---
# StructureDefinition-UKCore-Encounter

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreEncounter'
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
	name = 'UKCoreEncounter'
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

  <b>Admission Method</b>- An example to illustrate the extension for an encounter to support the method by which an individual was admitted into hospital.<br>
  {{pagelink:Example-UKCore-Extension-AdmissionMethod}}
  <br><br>

  <b>Discharge Method</b>- An example to illustrate the extension for an encounter to support the method of discharge from a hospital.<br>
  {{pagelink:Example-UKCore-Extension-DischargeMethod}}
  <br><br>

  <b>Emergency Care Discharge Status</b>- An example to illustrate the extension which is used to indicate the status of an individual on discharge from an Emergency Care Department.<br>
  {{pagelink:Example-UKCore-Extension-EmergencyCareDischargeStatus}}
  <br><br>

<b>Inpatient Encounter</b> - An example to illustrate an inpatient encounter.
<br>{{pagelink:Example-UKCore-Encounter-InpatientEncounter}}
  <br><br>

  <b>Legal Status</b>- An example to illustrate the extension which is used to indicate a patient's legal status on admission or discharge.<br>
  {{pagelink:Example-UKCore-Extension-LegalStatus}}
  <br><br>
  
  <b>Outcome of Attendance</b>- An example to illustrate the extension which is used to indicate the outcome of an outpatient attendance.<br>
  {{pagelink:Example-UKCore-Extension-OutcomeOfAttendance}}
  <br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Encounter profile:

- Query for a specific patient encounter
- Query for recent patient encounters
- Record or update an encounter

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
<td><code>Encounter.identifier</code></td>
<td>Identifier(s) by which this encounter is known.</td>
</tr>
<tr>
<td><code>Encounter.class</code></td>
<td>Concepts representing classification of patient encounter such as ambulatory (outpatient), inpatient, emergency, home health or others due to local variations.</td>
</tr>
<tr>
<td><code>Encounter.subject</code></td>
<td>The patient or group present at the encounter.</td>
</tr>
<tr>
<td><code>Encounter.participant</code></td>
<td>The list of people responsible for providing the service.</td>
</tr>
<tr>
<td><code>Encounter.participant.individual</code></td>
<td>Persons involved in the encounter other than the patient.</td>
</tr>
<tr>
<td><code>Encounter.reasonCode</code></td>
<td>Reason the encounter takes place, expressed as a code. For admissions, this can be used for a coded admission diagnosis.</td>
</tr>
<tr>
<td><code>Encounter.reasonReference</code></td>
<td>Reason the encounter takes place, expressed as a reference to a Condition, Procedure, Observation, or ImmunizationRecommendation.</td>
</tr>
</table>

---