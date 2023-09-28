---
topic: Profile-England-Patient
---

# StructureDefinition-England-Patient

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandPatient'
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
	name = 'EnglandPatient'
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
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-Patient, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-Patient, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-Patient, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
  {{table:https://fhir.nhs.uk/StructureDefinition/England-Patient, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
  {{xml:https://fhir.nhs.uk/StructureDefinition/England-Patient, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
  {{json:https://fhir.nhs.uk/StructureDefinition/England-Patient, snapshot}}
</div>

<div id="Examples" class="tabcontent">
<h3>Examples</h3>
<b>FredricaSmith</b> - An example to illustrate a patient called FredricaSmith<br>
{{pagelink:Example-England-Patient-FredricaSmith}}
<br><br>
<b>JackDawkins</b> - An example to illustrate a patient called JackDawkins<br>
{{pagelink:Example-England-Patient-JackDawkins}}
<br><br>
<b>Patient</b> - An example to illustrate a patient<br>
{{pagelink:Example-England-Patient-PDS}}
<br><br>
<b>RichardSmith</b> - An example to illustrate a patient called RichardSmith<br>
{{pagelink:Example-England-Patient-RichardSmith}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##

