---
topic: Profile-MedicationDispense
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense
usage: http://hl7.org/fhir/StructureDefinition/MedicationDispense
issue: UKCore-MedicationDispense
---
# StructureDefinition-UKCore-MedicationDispense

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

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

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

<h3> Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
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
<td><code>MedicationDispense.dosageInstruction.text</code></td>
<td>Free text dosage instructions.</td>
</tr>
<tr>
<td><code>MedicationDispense.dosageInstruction.timing</code></td>
<td>When medication should be administered.</td>
</tr>
<tr>
<td><code>MedicationDispense.dosageInstruction.doseAndRate</code></td>
<td>Dosage instructions for the medication.</td>
</tr>
<tr>
<td><code>MedicationDispense.dosageInstruction.doseAndRate.dose[x]</code></td>
<td>Quantity of medication administered.</td>
</tr>
<tr>
<td><code>MedicationDispense.dosageInstruction.doseAndRate.rate[x]</code></td>
<td>Rate at which the medication is to be administered.</td>
</tr>
</table>


---