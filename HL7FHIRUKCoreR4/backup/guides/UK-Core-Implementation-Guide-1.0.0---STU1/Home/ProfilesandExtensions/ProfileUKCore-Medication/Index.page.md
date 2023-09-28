---
topic: Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605
---
# StructureDefinition-UKCore-Medication

This UK Core profile is a restraint on the International FHIR resource <a href="https://hl7.org/fhir/R4/medication.html" target="_blank">Medication</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve medication information.

## Profile Purpose

This profile is primarily used for the identification and definition of a medication for the purposes of prescribing, dispensing, and administering a medication as well as for making statements about medication use.

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

<b>Timoptol Eye Drops</b> - An example to illustrate a representation of eye drops.  
{{pagelink:ExampleUKCore-Medication-TimoptolEyeDrops}}   <br><br>
<b>Timolol</b> - An example to illustrate the form element with a VTM.  
{{pagelink:Example-UKCore-Medication-TimololVTM}}   <br><br>
<b>COVID Vaccine</b> - An example to illustrate the batch element.  
{{pagelink:Example-UKCore-Medication-COVID-Vaccine}}   <br><br>
<b>Extension - Medication Trade Family</b> - An example to illustrate the Medication Trade Family.  
{{pagelink:Example-UKCore-Medication-Extension-MedicationTradeFamily}}   <br><br>
</div>

### Example Usage Scenarios

The UK Core Medication profile will likely not be used in isolation. It does not provide the context for the medication, e.g. the patient or medication related process. It will be typically used as a referenced resource within
- {{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}
- {{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}
- {{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}
- {{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}

---

## Profile Specific Implementation Guidance: ##

### Minimum Viable Content

A minimum viable content that all provider and consumer systems SHOULD support are the following elements.

<table id="assets">
<tr>
<th width="20%">Element</th>
<th width="80%">Reason</th>
</tr>
<tr>
<td><code>code</code></td>
<td>A dm+d code for the medication</td>
</tr>
</table>

---
