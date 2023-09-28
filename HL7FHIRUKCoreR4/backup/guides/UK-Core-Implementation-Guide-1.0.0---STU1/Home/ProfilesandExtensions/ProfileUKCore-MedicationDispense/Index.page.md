---
topic: Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9
---
# StructureDefinition-UKCore-MedicationDispense

This UK Core profile is a restraint on the International FHIR resource <a href="https://hl7.org/fhir/R4/medicationdispense.html" target="_blank">MedicationDispense</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve dispensed medication information.

## Profile Purpose
This profile covers the supply of medications to an individual. Examples include dispensing and pick-up from an outpatient or community pharmacy, dispensing patient-specific medications from inpatient pharmacy to ward, as well as issuing a single dose from ward stock to an individual for consumption. The medication dispense is the result of a pharmacy system responding to a medication order.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Eye drops</b> - An example to illustrate a dispense eye drops.  </br>
{{pagelink:ExampleUKCore-MedicationDispense-EyeDrops}}   <br><br>
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationDispense profile:

- Query for a patient's specific dispensed medication
- Record or update a dispensed medication.

---

## Profile Specific Implementation Guidance: ##

### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHOULD support are the following elements.

<table id="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>identifier</code></td>
<td>Allow the resource to be referenced within/by other resources</td>
</tr>
<tr>
<td><code>status</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>statusReason</code></td>
<td>To expand on the intent of the <code>status</code></td>
</tr>
<tr>
<td><code>medication[x]</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>subject</code></td>
<td>Identify the patient</td>
</tr>
<tr>
<td><code>performer</code></td>
<td>Who or what performed the dispensing event</td>
</tr>
<tr>
<td><code>authorizingPrescription</code></td>
<td>Link to a prescription, when available</td>
</tr>
<tr>
<td><code>quantity</code></td>
<td>Quantity of medication dispensed</td>
</tr>
<tr>
<td><code>whenPrepared</code></td>
<td>Timestamp the event</td>
</tr>
<tr>
<td><code>dosageInstruction</code></td>
<td>Dosage instruction for the dispensed medication</td>
</tr>
</table>

---
