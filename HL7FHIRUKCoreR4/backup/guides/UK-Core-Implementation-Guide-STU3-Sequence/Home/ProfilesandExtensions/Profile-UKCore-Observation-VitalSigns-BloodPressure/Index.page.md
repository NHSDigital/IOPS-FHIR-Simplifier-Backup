---
topic: Profile-Observation-VitalSigns-BloodPressure
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BloodPressure
usage: http://hl7.org/fhir/StructureDefinition/Observation
issue: UKCore-Observation-VitalSigns-BloodPressure
---

# StructureDefinition-UKCore-Observation-VitalSigns-BloodPressure

<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 7. This is a new Profile added to UK Core and should undergo review during the Sprint 7 review window.

Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation-VitalSigns-BloodPressure/~issues?level=File">Report Issue for UKCore-Observation-VitalSigns-BloodPressure</a>.
</div>

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Blood Pressure</b> - An example to illustrate recording a high blood pressure.<br/>
{{pagelink:Example-UKCore-Observation-VitalSigns-BloodPressure}}<br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BloodPressure'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BloodPressure'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation-VitalSigns-BloodPressure'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Observation-VitalSigns-BloodPressure/~issues?level=File">Report Issue for UKCore-Observation-VitalSigns-BloodPressure</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Observation Vital Signs Blood Pressure profile:

- Query and retrieve a patient's blood pressure readings
- Record or update a patient's blood pressure readings

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

The UKCore-Observation-VitalSigns-BloodPressure profile further derives from {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} and this page only shows the differences between the two. Refer to {{pagelink:Profile-Observation,text:UKCore-Observation}} and {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} for more implementation guidance.

An instance of the UKCore-Observation-VitalSigns-BloodPressure resource SHALL have the `Observation.code` element populated, with a LOINC "magic code" and SNOMED CT concept as detailed below. In addition, the individual Systolic and Diastolic readings SHALL be populated in `Observation.component` as detailed below.

<div id="renderParent" title="Blood Pressure Observation structure">
{{render:BloodPressure}}
</div>

### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding {{pagelink:Profile-Observation,text:UKCore-Observation}} and {{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} tables, along with the following.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.device</code></td>
<td>A device SHOULD be present.</td>
</tr>
<tr>
<td><code>Observation.method</code></td>
<td>A measurement method SHOULD be present.</td>
</tr>
<tr>
<td><code>Observation.component.code.coding</code></td>
<td>A systolic blood pressure measurement SHALL be present, and that SHALL have a LOINC "magic code", in addition to the SNOMED CT concept for the systolic blood pressure observation.
<br>A diastolic blood pressure measurement SHOULD be present, and that SHALL have a LOINC "magic code", in addition to the SNOMED CT concept for the diastolic blood pressure observation.
</td>
</tr>
</table>

---

