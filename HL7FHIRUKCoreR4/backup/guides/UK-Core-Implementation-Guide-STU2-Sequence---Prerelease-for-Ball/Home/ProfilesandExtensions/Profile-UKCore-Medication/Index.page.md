---
topic: Profile-Medication-73860
---
# StructureDefinition-UKCore-Medication

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMedication'
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
	name = 'UKCoreMedication'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Medication, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Timoptol Eye Drops</b> - An example to illustrate a representation of eye drops.  <br>
{{pagelink:Example-UKCore-Medication-TimoptolEyeDrops}}   <br><br>
<b>Timolol</b> - An example to illustrate the form element with a VTM.  <br>
{{pagelink:Example-UKCore-Medication-TimololVTM}}   <br><br>
<b>COVID Vaccine</b> - An example to illustrate the batch element.  <br>
{{pagelink:Example-UKCore-Medication-COVID-Vaccine}}   <br><br>
<b>Extension - Medication Trade Family</b> - An example to illustrate the Medication Trade Family.  <br>
{{pagelink:Example-UKCore-Medication-Extension-MedicationTradeFamily}}
</div>
</nocheck>

### Example Usage Scenarios

The UK Core Medication profile will likely not be used in isolation. It does not provide the context for the medication, e.g. the patient or medication related process. It will be typically used as a referenced resource within
- {{pagelink:Profile-MedicationAdministration-56616}}
- {{pagelink:Profile-MedicationDispense-76932}}
- {{pagelink:Profile-MedicationRequest-20572}}
- {{pagelink:Profile-MedicationStatement-34649}}

---

## Profile Specific Implementation Guidance: ##

<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="20%">Element</th>
<th width="80%">Reason</th>
</tr>
<tr>
<td><code>Medication.code</code></td>
<td>Codes that identify this medication.</td>
</tr>
</table> 

---
