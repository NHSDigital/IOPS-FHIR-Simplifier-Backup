---
topic: Profile-Immunization-16790
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
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Influenza virus vaccine</b> - An example to illustrate an Influenza virus vaccine.  <br>
{{pagelink: Example-UKCore-Immunization}}
<br><br>
<b>Extension - ParentPresent</b> - An example to illustrate the ParentPresent extension. <br>
{{pagelink: Example-UKCore-Immunization-Extension-ParentPresent}}
<br><br>
<b>Extension - VaccinationProcedure</b> - An example to illustrate the VaccinationProcedure extension, with a vaccination procedure for an administered Influenza virus vaccine.  <br>
{{pagelink: Example-UKCore-Immunization-Extension-VaccinationProcedure}}
<br><br>
<b>Extension - VaccinationProcedureCovid</b> - An example to illustrate the VaccinationProcedureCovid extension, with a vaccination procedure for the COVID-19 Vaccine Vaxzevria.  <br>
{{pagelink: Example-UKCore-Immunization-Extension-VaccinationProcedureCovid}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Immunization profile:

- Query and retrieve an individual’s immunisations (vaccinations)
- Record or update an individual’s immunisations (vaccinations).

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
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
