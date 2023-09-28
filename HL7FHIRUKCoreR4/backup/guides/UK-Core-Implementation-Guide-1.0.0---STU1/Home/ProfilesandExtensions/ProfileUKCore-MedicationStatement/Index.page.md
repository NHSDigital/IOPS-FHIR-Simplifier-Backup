---
topic: Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf
---
# StructureDefinition-UKCore-MedicationStatement

This UK Core profile is a restraint on the International FHIR resource <a href="https://hl7.org/fhir/R4/medicationstatement.html" target="_blank">MedicationStatement</a>, and defines the constraints, extensions, and minimal set of data to query and retrieve medication statement information.

## Profile Purpose

This profile allows exchange of a record of a medication that is being consumed by a patient. A MedicationStatement may indicate that the individual may be taking the medication now or has taken the medication in the past or will be taking the medication in the future. The source of this information can be the individual, significant other (such as a family member or spouse), or a clinician.

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>XML View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Amoxicillin</b> - An example to illustrate a medication statement of Amoxicillin.
</br>
{{pagelink:ExampleUKCore-MedicationStatement-Amoxicillin}}  <br><br>

<b>Extension - LastIssueDate</b> - An example to illustrate the LastIssueDate extension.
</br>
{{pagelink:ExampleUKCore-MedicationStatement-Extension-LastIssueDate}}  <br><br>

<b>Extension - PrescribingOrg</b> - An example to illustrate the PrescribingOrg extension.
</br>
{{pagelink:ExampleUKCore-MedicationStatement-Extension-PrescribingOrg}}  <br><br>

<b>Extension - PharmacistVerifiedIndicator</b> - An example to illustrate the PharmacistVerifiedIndicator extension. 
</br>
{{pagelink:Example-UKCore-MedicationStatement-Extension-PharmacistVerifiedIndicator}}  <br><br>
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationStatement profile:

- Query and retrieve a patient's current medication
- Record or update a patient's current medication.

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
<td><code>basedOn</code></td>
<td>To reference to a <code>MedicationRequest</code> resource, where applicable</td>
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
<td>Mandatory element</td>
</tr>
<tr>
<td><code>effective[x]</code></td>
<td>To timestamp the statement</td>
</tr>
<tr>
<td><code>dateAsserted</code></td>
<td>To timestamp the statement assertion</td>
</tr>
<tr>
<td><code>informationSource</code></td>
<td>To reference other resources, where applicable</td>
</tr>
<tr>
<td><code>derivedFrom</code></td>
<td>To reference other resources, where applicable</td>
</tr>
<tr>
<td><code>dosage</code></td>
<td>For the dosage for the statement</td>
</tr>
</table>

---
