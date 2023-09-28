---
topic: Profile-Observation-VitalSigns
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns
---

# StructureDefinition-UKCore-Observation-VitalSigns

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreObservationVitalSigns'
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
	name = 'UKCoreObservationVitalSigns'
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
<b>Blood Pressure</b> - An example to illustrate a vital signs blood pressure reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BloodPressure}}<br><br>
<b>BMI</b> - An example to illustrate a vital signs body mass index reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BMI}}<br><br>
<b>Body Height</b> - An example to illustrate a vital signs body height reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BodyHeight}}<br><br>
<b>Body Temperature</b> - An example to illustrate a vital signs body temperature reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BodyTemperature}}<br><br>
<b>Body Weight</b> - An example to illustrate a vital signs body weight reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BodyWeight}}<br><br>
<b>Head Circumference</b> - An example to illustrate a vital signs head circumference reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-HeadCircumference}}<br><br>
<b>Heart Rate</b> - An example to illustrate a vital signs heart rate reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-HeartRate}}<br><br>
<b>Oxygen Saturation</b> - An example to illustrate a vital signs oxygen saturation reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-OxygenSaturation}}<br><br>
<b>Respiratory Rate</b> - An example to illustrate a vital signs respiration rate reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-RespiratoryRate}}<br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###

The following are example usage scenarios for the UK Core Observation Vital Signs profile:

- Query and retrieve a patient's vital signs
- Record or update a patient's vitals signs

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

This is a derived profile of {{pagelink:Profile-Observation,text:UKCore-Observation}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.

This guidance is also designed to align with [https://hl7.org/fhir/R4/observation-vitalsigns.html](HL7 Observation Vital Signs guidance) where possible.

### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding UKCore-Observation table, along with the following.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.status</code></td>
<td>A status of <code>final</code> SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.category</code></td>
<td>A category of <code>vital-signs</code> SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.code.coding</code></td>
<td>A LOINC "magic code" SHALL be present, in addition to the SNOMED CT concept for the observation type.</td>
</tr>
<tr>
<td><code>Observation.subject</code></td>
<td>A UKCore-Patient SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.effective[x]</code></td>
<td>An effective time or date SHALL be present.</td>
</tr>
<tr>
<td><code>Observation.component.code.coding</code></td>
<td>If a component is present, a LOINC "magic code" SHALL be present, in addition to the SNOMED CT concept for the observation type.</td>
</tr>
</table>

---

