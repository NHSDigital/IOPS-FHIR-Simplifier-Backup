---
topic: Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0
---
# StructureDefinition-UKCore-MedicationRequest

This UK Core profile is a restraint on the International FHIR resource  <a href="https://hl7.org/fhir/R4/medicationrequest.html" target="_blank">MedicationRequest</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve prescription information.

## Profile Purpose

An order or request for both supply of the medication and the instructions for administration of the medication to an individual. This profile covers inpatient medication orders as well as community orders (whether filled by the prescriber or by a pharmacy). It also includes orders for over-the-counter medications (e.g. Aspirin), total parenteral nutrition and diet/ vitamin supplements. It MAY be used to support the order of medication-related devices. It is not intended for use in prescribing particular diets, or for ordering non-medication-related items (eyeglasses, supplies, etc).

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Eye drops</b> - An example to illustrate a request for eye drops. 
</br>
{{pagelink:ExampleUKCore-MedicationRequest-EyeDrops}}  <br><br>

<b>Extension - RepeatInformation</b> - An example to illustrate the RepeatInformation extension. 
</br>
{{pagelink:ExampleUKCore-MedicationRequest-Extension-RepeatInformation}}  <br><br>
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationRequest profile:

- Query for a patient's specific requested medication
- Record or update a requested medication.

---

## Profile Specific Implementation Guidance: ##

### Minimum Viable Content

A minimum viable content that all provider and consumer systems SHOULD support are the following elements.

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
<td><code>intent</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>category</code></td>
<td>Provides the business context for the relevant dispensing processes</td>
</tr>
<tr>
<td><code>medication[x]</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>subject</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>authoredOn</code></td>
<td>To timestamp the event</td>
</tr>
<tr>
<td><code>requester</code></td>
<td>Who is requesting the medication</td>
</tr>
<tr>
<td><code>dosageInstruction</code></td>
<td>Dosage instructions for the medication</td>
</tr>
<tr>
<td><code>dispenseRequest</code></td>
<td>Specific dispensing quantity instructions</td>
</tr>
<tr>
<td><code>substitution</code></td>
<td>Mandatory element</td>
</tr>
</table>

---
