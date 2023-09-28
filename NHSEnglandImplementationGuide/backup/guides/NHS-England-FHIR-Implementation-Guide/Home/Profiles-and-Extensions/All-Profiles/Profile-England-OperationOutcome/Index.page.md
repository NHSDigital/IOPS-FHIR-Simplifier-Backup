---
topic: Profile-England-OperationOutcome
---

# StructureDefinition-England-OperationOutcome

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandOperationOutcome'
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
	name = 'EnglandOperationOutcome'
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
{{tree:https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/StructureDefinition/England-OperationOutcome, snapshot}}
</div>

<div id="Examples" class="tabcontent">
<h3>Examples</h3>
<b>Patient First Name Validation</b> - An example to validate patient first name<br>
{{pagelink:Example-England-OperationOutcome-PatientFirstNameValidation}}
<br><br>
<b>Patient Details Validation</b> - An example to validate patient details<br>
{{pagelink:Example-England-OperationOutcome-PatientDetailsValidation}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##