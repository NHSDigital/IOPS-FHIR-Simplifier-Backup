---
topic: Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159
---
# StructureDefinition-UKCore-Immunization

This UK Core profile is a restraint on the International FHIR resource <a href="https://hl7.org/fhir/R4/immunization.html" target="_blank">Immunization</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve an individual’s immunisation information. 

## Profile Purpose

This profile is intended to cover the recording of current and historical administration of vaccines to individuals across all healthcare disciplines in all care settings and all regions. This profile does not support the administration of non-vaccine agents, even those that may have or claim to have immunological effects. While the terms "immunisation" and "vaccination" are not clinically identical, for the purposes of the FHIR profile, the terms are used synonymously. 

<div class="tab">
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

<b>Influenza virus vaccine</b> - An example to illustrate an Influenza virus vaccine.  
{{pagelink: ExampleUKCore-Immunization}}
<br><br>
<b>Extension - ParentPresent</b> - An example to illustrate the ParentPresent extension.  
{{pagelink: ExampleUKCore-Immunization-Extension-ParentPresent}}
<br><br>
<b>Extension - VaccinationProcedure</b> - An example to illustrate the VaccinationProcedure extension, whth a vaccination procedure for an adminstered Influenza virus vaccine.  
{{pagelink: ExampleUKCore-Immunization-Extension-VaccinationProcedure}}
<br><br>
<b>Extension - VaccinationProcedureCovid</b> - An example to illustrate the VaccinationProcedureCovid extension, whth a vaccination procedure for the COVID-19 Vaccine Vaxzevria.  
{{pagelink: ExampleUKCore-Immunization-Extension-VaccinationProcedureCovid}}   <br><br>
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Immunization profile:

- Query and retrieve an individual’s immunisations (vaccinations)
- Record or update an individual’s immunisations (vaccinations).

---

## Profile Specific Implementation Guidance: ##
