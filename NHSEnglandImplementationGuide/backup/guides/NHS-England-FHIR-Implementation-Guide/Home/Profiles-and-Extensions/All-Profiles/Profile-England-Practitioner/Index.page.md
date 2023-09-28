---
topic: Profile-England-Practitioner
---

## StructureDefinition-England-Practitioner

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandPractitioner'
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
	name = 'EnglandPractitioner'
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
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-Practitioner, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-Practitioner, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-Practitioner, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
  {{table:https://fhir.nhs.uk/StructureDefinition/England-Practitioner, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
  {{xml:https://fhir.nhs.uk/StructureDefinition/England-Practitioner, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
  {{json:https://fhir.nhs.uk/StructureDefinition/England-Practitioner, snapshot}}
</div>

<div id="Examples" class="tabcontent">
<h3>Examples</h3>
<b>Basic Practitioner</b> - An example to illustrate the basic practitioner<br>
{{pagelink:Example-England-Practitioner-BasicPractitioner}}
<br><br>
<b>Consultant</b> - An example to illustrate the practitioner who is a consultant<br>
{{pagelink:Example-England-Practitioner-Consultant}}
<br><br>
<b>General Practitioner</b> - An example to illustrate the  a practitioner who is the patient's GP<br>
{{pagelink:Example-England-Practitioner-GP}}
<br><br>
<b> Practitioner As Nurse</b> - An example to illustrate the practitioner who is a nurse<br>
{{pagelink:Example-England-Practitioner-Nurse}}
<br><br>
<b>Validate Practitioner</b> - An example to illustrate to validate practitioner<br>
{{pagelink:Example-England-Practitioner-Validation}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##

