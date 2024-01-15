---
topic: Profile-Immunization
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization
---
# StructureDefinition-UKCore-Immunization

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Influenza virus vaccine</b> - An example to illustrate an Influenza virus vaccine.  <br>
{{pagelink: Example-UKCore-Immunization-InfluenzaVaccine}}
<br><br>
<b>Parent Present</b> - An example to illustrate the ParentPresent extension. <br>
{{pagelink: Example-UKCore-Extension-ParentPresent}}
<br><br>
<b>Vaccination Procedure</b> - An example to illustrate the VaccinationProcedure extension, with a vaccination procedure for an administered Influenza virus vaccine.  <br>
{{pagelink: Example-UKCore-Extension-VaccinationProcedure}}
<br><br>
<b>Vaccination Procedure Covid</b> - An example to illustrate the VaccinationProcedureCovid extension, with a vaccination procedure for the COVID-19 Vaccine Vaxzevria.  <br>
{{pagelink: Example-UKCore-Extension-VaccinationProcedure-Covid}}
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

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Immunization/~issues?level=File">Report Issue for UKCore-Immunization</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Immunization profile:

- Query and retrieve an individual’s immunisations (vaccinations)
- Record or update an individual’s immunisations (vaccinations).

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
<td><code>Immunization.status</code></td>
<td>Indicates the current status of the immunization event.</td>
</tr>
<tr>
<td><code>Immunization.vaccineCode</code></td>
<td>Vaccine that was administered or was to be administered.</td>
</tr>
<tr>
<td><code>Immunization.patient</code></td>
<td>The patient who either received or did not receive the immunization.</td>
</tr>
<tr>
<td><code>Immunization.occurrence[x]</code></td>
<td>When the vaccine administered or was to be administered.</td>
</tr>
<tr>
<td><code>Immunization.occurrenceDateTime</code></td>
<td>DateTime vaccine administered or was to be administered.</td>
</tr>
<tr>
<td><code>Immunization.manufacturer</code></td>
<td>Name of vaccine manufacturer.</td>
</tr>
<tr>
<td><code>Immunization.lotNumber</code></td>
<td>Lot number of the vaccine.</td>
</tr>
<tr>
<td><code>Immunization.doseQuantity</code></td>
<td>How much of the vaccine was administered</td>
</tr>
</table>

---
