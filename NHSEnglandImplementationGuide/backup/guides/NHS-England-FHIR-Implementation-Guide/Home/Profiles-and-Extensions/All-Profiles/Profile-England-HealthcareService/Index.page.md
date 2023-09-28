---
topic: Profile-England-HealthcareService
---

## StructureDefinition-England-HealthcareService

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandHealthcareService'
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
	name = 'EnglandHealthcareService'
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
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-HealthcareService, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-HealthcareService, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
  {{tree:https://fhir.nhs.uk/StructureDefinition/England-HealthcareService, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
  {{table:https://fhir.nhs.uk/StructureDefinition/England-HealthcareService, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
  {{xml:https://fhir.nhs.uk/StructureDefinition/England-HealthcareService, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
  {{json:https://fhir.nhs.uk/StructureDefinition/England-HealthcareService, snapshot}}
</div>

<div id="Examples" class="tabcontent">
<h3>Examples</h3>
<b>Cancer Screening Centre</b> - An example to illustrate a cancer screening centre service within a HealthcareService resource.<br>
{{pagelink:Example-England-HealthcareService-CancerScreeningCentre}}
<br><br>

  <b>ERS Search Results</b> - An example to illustrate a ERS search results service within a HealthcareService resource.<br>
{{pagelink:Example-England-HealthcareService-ERSSearchResults}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##