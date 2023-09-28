---
topic: Profile-Immunization
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization
---
# StructureDefinition-UKCore-Immunization

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreImmunization'
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
	name = 'UKCoreImmunization'
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

<b>Influenza virus vaccine</b> - An example to illustrate an Influenza virus vaccine.  <br>
{{pagelink: Example-UKCore-Immunization-InfluenzaVaccine}}
<br><br>
<b>Extension - ParentPresent</b> - An example to illustrate the ParentPresent extension. <br>
{{pagelink: Example-UKCore-Immunization-Extension-ParentPresent}}
<br><br>
<b>Extension - VaccinationProcedure</b> - An example to illustrate the VaccinationProcedure extension, with a vaccination procedure for an administered Influenza virus vaccine.  <br>
{{pagelink: Example-UKCore-Immunization-Extension-VaccinationProcedure}}
<br><br>
<b>Extension - VaccinationProcedureCovid</b> - An example to illustrate the VaccinationProcedureCovid extension, with a vaccination procedure for the COVID-19 Vaccine Vaxzevria.  <br>
{{pagelink: Example-UKCore-Immunization-Extension-VaccinationProcedure-Covid}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Immunization profile:

- Query and retrieve an individual’s immunisations (vaccinations)
- Record or update an individual’s immunisations (vaccinations).

<hr class="thickline">

## Profile Specific Implementation Guidance: ##
