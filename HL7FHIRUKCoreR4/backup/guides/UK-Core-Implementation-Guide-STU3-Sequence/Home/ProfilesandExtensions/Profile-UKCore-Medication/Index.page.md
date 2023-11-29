---
topic: Profile-Medication
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication
---
# StructureDefinition-UKCore-Medication

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMedication'
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
	name = 'UKCoreMedication'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>COVID Vaccine</b> - An example to illustrate the batch element.  <br>
{{pagelink:Example-UKCore-Medication-COVID-Vaccine}}   <br><br>
<b>Medication Trade Family</b> - An example to illustrate the Medication Trade Family.  <br>
{{pagelink:Example-UKCore-Extension-MedicationTradeFamily}} <br><br>
<b>Timolol</b> - An example to illustrate the form element with a VTM.  <br>
{{pagelink:Example-UKCore-Medication-TimololVTM}}   <br><br>
<b>Timoptol Eye Drops</b> - An example to illustrate a representation of eye drops.  <br>
{{pagelink:Example-UKCore-Medication-TimoptolEyeDrops}}   <br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Medication/~issues?level=File">Report Issue for UKCore-Medication</a>.
</div>
</nocheck>

### Example Usage Scenarios

The UK Core Medication profile will likely not be used in isolation. It does not provide the context for the medication, e.g. the patient or medication related process. It will be typically used as a referenced resource within
- {{pagelink:Profile-MedicationAdministration}}
- {{pagelink:Profile-MedicationDispense}}
- {{pagelink:Profile-MedicationRequest}}
- {{pagelink:Profile-MedicationStatement}}

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
<td><code>Medication.code</code></td>
<td>Codes that identify this medication.</td>
</tr>
</table> 

---
