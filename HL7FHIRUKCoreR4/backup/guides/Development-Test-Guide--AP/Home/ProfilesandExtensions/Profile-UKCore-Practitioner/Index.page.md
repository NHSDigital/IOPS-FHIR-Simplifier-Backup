---
topic: Profile-Practitioner
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner
---
# StructureDefinition-UKCore-Practitioner

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCorePractitioner'
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
	name = 'UKCorePractitioner'
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
<b>General Practitioner</b> - An example to illustrate a practitioner who is the Patient's GP. 
<br>
{{pagelink:Example-UKCore-Practitioner-DoctorPaulRastall}}
<br><br>
<b>Consultant</b> - An example to illustrate a practitioner who is a Consultant. 
<br>
{{pagelink:Example-UKCore-Practitioner-ConsultantSandraGose}}
<br><br>
<b>Pharmacist</b> - An example to illustrate a practitioner who is a Pharmacist.
<br>
{{pagelink:Example-UKCore-Practitioner-PharmacistJimmyChuck}}
<br><br>
Note: the practitioner's role information is carried in the {{pagelink:Profile-PractitionerRole}}   <br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Practitioner profile:

- Query for practitioner information using the query parameter identifier (`Practitioner.identifier`) for a known SDS User Identifier.
- Exchange practitioner information within a FHIR document or message.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##
