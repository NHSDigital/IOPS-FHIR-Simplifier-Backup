---
topic: Profile-England-Immunization
---

# StructureDefinition-England-Immunization

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandImmunization'
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
	name = 'EnglandImmunization'
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
{{tree:https://fhir.nhs.uk/StructureDefinition/England-Immunization, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-Immunization, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-Immunization, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/StructureDefinition/England-Immunization, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/StructureDefinition/England-Immunization, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/StructureDefinition/England-Immunization, snapshot}}
</div>

<div id="Examples" class="tabcontent">
<h3>Examples</h3>
<b>Patient Immunization Query</b> - An example to illustrate the patient immunization query contained in a Bundle resource
<br>{{pagelink:Example-England-Bundle-PatientImmunizationQuery}}
<br><br>
<b>Administration Of SARS-CoV-2 First Dose</b> - An example to illustrate the administration Of SARS-CoV-2 first dose
<br>{{pagelink:Example-England-Immunization-AdministrationOfSARSCoV2FirstDose}}
<br><br>
<b>SARS-CoV-2 Second Dose</b> - An example to illustrate the administration Of SARS-CoV-2 second dose<br>
{{pagelink:Example-England-Immunization-AdministrationOfSARSCoV2SecondDose}}
<br><br>
<b>SARS-CoV-2 Not Administered</b> - An example to illustrate the SARS-CoV-2 not administered<br>
{{pagelink:Example-England-Immunization-SARSCoV2NotAdministered}}
<br><br>
<b>Vaccination History</b> - An example to illustrate the patient vaccination history<br>
{{pagelink:Example-England-Bundle-VaccinationQuery-SearchInclude}}
<br><br>
<b>Vaccination Performer</b> - An example to illustrate the vaccination performer<br>
{{pagelink:Example-England-Immunization-VaccinationPerformer}}

</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##