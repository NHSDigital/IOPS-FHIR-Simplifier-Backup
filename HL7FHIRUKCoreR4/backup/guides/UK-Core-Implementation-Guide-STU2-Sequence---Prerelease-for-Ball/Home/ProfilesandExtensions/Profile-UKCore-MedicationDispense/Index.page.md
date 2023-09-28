---
topic: Profile-MedicationDispense-76932
---
# StructureDefinition-UKCore-MedicationDispense

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMedicationDispense'
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
	name = 'UKCoreMedicationDispense'
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
{{pagelink:Example-UKCore-MedicationDispense-EyeDrops}} 
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationDispense profile:

- Query for a patient's specific dispensed medication
- Record or update a dispensed medication.

---

## Profile Specific Implementation Guidance: ##

<h3> Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>MedicationDispense.identifier</code></td>
<td>Allow the resource to be referenced within/by other resources.</td>
</tr>
<tr>
<td><code>MedicationDispense.status</code></td>
<td>Mandatory element.</td>
</tr>
<tr>
<td><code>MedicationDispense.medication[x]</code></td>
<td>What medication was supplied.</td>
</tr>
<tr>
<td><code>MedicationDispense.subject</code></td>
<td>Identify the patient.</td>
</tr>
<tr>
<td><code>MedicationDispense.performer</code></td>
<td>Who or what performed the dispensing event.</td>
</tr>
<tr>
<td><code>MedicationDispense.performer.actor</code></td>
<td>Individual who was performing.</td><!--added-->
</tr>
<tr>
<td><code>MedicationDispense.authorizingPrescription</code></td>
<td>Link to a prescription, when available.</td>
</tr>
<tr>
<td><code>MedicationDispense.quantity</code></td>
<td>Quantity of medication dispensed.</td>
</tr>
<tr>
<td><code>MedicationDispense.whenPrepared</code></td>
<td>Timestamp the event.</td>
</tr>
<tr>
<td><code>MedicationDispense.dosageInstruction</code></td>
<td>Dosage instruction for the dispensed medication.</td>
</tr>
<!-- added all below-->
<tr>
<td class="balloted"><code>MedicationDispense.dosageInstruction.text</code></td>
<td class="balloted">Free text dosage instructions.</td>
</tr>
<tr>
<td class="balloted"><code>MedicationDispense.dosageInstruction.timing</code></td>
<td class="balloted">When medication should be administered.</td>
</tr>
<tr>
<td class="balloted"><code>MedicationDispense.dosageInstruction.doseAndRate</code></td>
<td class="balloted">Dosage instructions for the medication.</td>
</tr>
<tr>
<td class="balloted"><code>MedicationDispense.dosageInstruction.doseAndRate.dose[x]</code></td>
<td class="balloted">Quantity of medication administered.</td>
</tr>
<tr>
<td class="balloted"><code>MedicationDispense.dosageInstruction.doseAndRate.rate[x]</code></td>
<td class="balloted">Rate at which the medication is to be administered.</td>
</tr>
</table>


---