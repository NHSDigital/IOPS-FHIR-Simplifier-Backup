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
<b>24 hour monitoring</b> - An example to illustrate recording the average blood pressure over 24 hours.<br/>
{{pagelink:Example-UKCore-Observation-24HourBloodPressure}}<br><br>
  <b>Awareness of diagnosis</b> - An example to illustrate the observation of the awareness of a diagnosis.<br/>
{{pagelink:Example-UKCore-Observation-AwarenessOfDiagnosis}}<br><br>
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
<b>Breathing Normally</b> - An example to illustrate a patient breathing room air.<br/>
{{pagelink:Example-UKCore-Observation-BreathingNormally}}<br><br>
  <b>Drug Use</b> - An example to illustrate the observation of patient drug use.<br/>
{{pagelink:Example-UKCore-Observation-DrugUse}}<br><br>
<b>Fasting Test</b> - An example to illustrate recording the blood glucose level following a period of fasting.<br/>
{{pagelink:Example-UKCore-Observation-FastingTest}}<br><br>
<b>Finger Joint Inflammation</b> - An example to illustrate the observation of an inflammed finger joint.<br/>
{{pagelink:Example-UKCore-Observation-FingerJointInflamed}}<br><br>
<b>Full Blood count</b> - An example to illustrate a full blood count using multiple lab observation references.<br/>
{{pagelink:Example-UKCore-Observation-Group-FullBloodCount}}
<b>Head Circumference</b> - An example to illustrate a vital signs head circumference reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-HeadCircumference}}<br><br>
<b>Heart Rate</b> - An example to illustrate a vital signs heart rate reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-HeartRate}}<br><br>
<b>Heavy Drinker</b> - An example to illustrate the alcohol consumption of a heavy drinker.<br/>
{{pagelink:Example-UKCore-Observation-HeavyDrinker}}<br><br>
<b>NEWS2 Bundle</b> - An example to illustrate a full bundle of National Early Warning Score (NEWS) 2 observations, sub scores, and total score.<br/>
{{pagelink:Example-UKCore-Bundle-NEWS2Observations}}<br><br>
<b>NPEWS Total</b> - An example to illustrate a National Paediatric Early Warning System (NPEWS) total score.<br/>
{{pagelink:Example-UKCore-Observation-NPEWSTotal}}<br><br>
<b>Oxygen Saturation</b> - An example to illustrate a vital signs oxygen saturation reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-OxygenSaturation}}<br><br>
<b>Pipe Smoker</b> - An example to illustrate recording a patient who smokes a pipe.<br/>
{{pagelink:Example-UKCore-Observation-PipeSmoker}}<br><br>
<b>Red cell count</b> - An example to illustrate the observation of a red cell count for a blood specimen.<br/>
{{pagelink:Example-UKCore-Observation-Lab-RedCellCount}}<br><br>
<b>Respiratory Rate</b> - An example to illustrate a vital signs respiration rate reading.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-RespiratoryRate}}<br><br>
<b>Responds to Voice</b> - An example to illustrate recording a patients level of consiousness.<br/>
{{pagelink:Example-UKCore-Observation-PatientConsciousness}}<br><br>
  <b>Triggered By Drug Use</b> - An example to illustrate the pre-adopted R5 element via an extension, which is used to indicate a triggering observation.<br>
  {{pagelink:Example-UKCore-Extension-TriggeredBy}}<br><br>
<b>Using Oxygen Therapy</b> - An example to illustrate a patient on supplemental oxygen.<br/>
{{pagelink:Example-UKCore-Observation-OxygenTherapy}}<br><br>
<b>White cell count</b> - An example to illustrate the observation of a white cell count for a blood specimen.<br/>
{{pagelink:Example-UKCore-Observation-Lab-WhiteCellCount}}<br><br>

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

<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.status</code></td>
<td>The status of the result value.</td>
</tr>
<tr>
<td><code>Observation.category</code></td>
<td>A code that classifies the general type of observation being made.</td>
</tr>
<tr>
<td><code>Observation.code</code></td>
<td>Type of observation (code / type)</td>
</tr>
<tr>
<td><code>Observation.subject</code></td>
<td>Who and/or what the observation is about</td>
</tr>
<tr>
<td><code>Observation.effective[x]</code></td>
<td>Clinically relevant time/time-period for observation</td>
</tr>
<tr>
<td><code>Observation.performer</code></td>
<td>Who is responsible for the observation</td>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>Actual result.</td>
</tr>
</table>

---
