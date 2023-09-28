---
topic: Profile-Observation
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation
---

# StructureDefinition-UKCore-Observation

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreObservation'
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
	name = 'UKCoreObservation'
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
  <b>Awareness of diagnosis</b> - An example to illustrate the observation of the awareness of a diagnosis.<br/>
{{pagelink:Example-UKCore-Observation-AwarenessOfDiagnosis}}<br><br>
  <b>Drug Use</b> - An example to illustrate the observation of patient drug use.<br/>
{{pagelink:Example-UKCore-Observation-DrugUse}}<br><br>
  <b>Triggered By Drug Use</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to indicate a triggering observation.<br>
  {{pagelink:Example-UKCore-Observation-Extension-TriggeredBy}}<br><br>
<br><br>
<b>Finger Joint Inflammation</b> - An example to illustrate the observation of an inflammed finger joint.<br/>
{{pagelink:Example-UKCore-Observation-FingerJointInflamed}}
</div>


<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation profile:

- Query and retrieve a patient's observations
- Record or update a patient's observations

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

