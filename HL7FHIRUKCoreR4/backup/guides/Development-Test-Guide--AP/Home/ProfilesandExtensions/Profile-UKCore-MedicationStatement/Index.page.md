---
topic: Profile-MedicationStatement
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement
---
# StructureDefinition-UKCore-MedicationStatement

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMedicationStatement'
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
	name = 'UKCoreMedicationStatement'
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
<b>Amoxicillin</b> - An example to illustrate a medication statement of Amoxicillin.
<br>{{pagelink:Example-UKCore-MedicationStatement-Amoxicillin}}
<br><br>
<b>Extension - LastIssueDate</b> - An example to illustrate the LastIssueDate extension.
<br>{{pagelink:Example-UKCore-MedicationStatement-Extension-LastIssueDate}}
<br><br>
<b>Extension - PrescribingOrg</b> - An example to illustrate the PrescribingOrg extension.
<br>{{pagelink:Example-UKCore-MedicationStatement-Extension-PrescribingOrg}}
<br><br>
<b>Extension - PharmacistVerifiedIndicator</b> - An example to illustrate the PharmacistVerifiedIndicator extension. 
<br>{{pagelink:Example-UKCore-MedicationStatement-Extension-PharmacistVerifiedIndicator}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationStatement profile:

- Query and retrieve a patient's current medication
- Record or update a patient's current medication.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##
