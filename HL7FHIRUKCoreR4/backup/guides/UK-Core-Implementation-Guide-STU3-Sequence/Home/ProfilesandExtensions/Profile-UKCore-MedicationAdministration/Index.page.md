---
topic: Profile-MedicationAdministration
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration
usage: http://hl7.org/fhir/StructureDefinition/MedicationAdministration
issue: UKCore-MedicationAdministration
---
# StructureDefinition-UKCore-MedicationAdministration

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Timoptol Eye Drops</b> - An example to illustrate a medication administration of eye drops.<br>
 {{pagelink:Example-UKCore-MedicationAdministration-TimoptolEyeDrops}}
</div>
</nocheck>

### Example Usage Scenarios

The following are example usage scenarios for the UK Core Medication Administration profile:

-	To share inpatient or outpatient non-immunization administrations of medication between clinical systems. Example scenarios include inpatient patient transfer from ward-to-ward or hospital-to-hospital, where different clinical systems are in use. For immunisations use the {{pagelink:Profile-Immunization}} resource.
-	To share patient self-administration of medication.
-	To share home-health reporting from medicines administration and monitoring devices.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##


<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>MedicationAdministration.identifier</code></td>
<td>Allow the resource to be referenced within/by other resources</td>
</tr>
<tr>
<td><code>MedicationAdministration.status</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>MedicationAdministration.medication[x]</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>MedicationAdministration.subject</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>MedicationAdministration.effective[x]</code></td>
<td>Mandatory element</td>
</tr>
<tr>
<td><code>MedicationAdministration.dosage</code></td>
<td>The dosage instruction for the administered medication</td>
</tr>
</table>

---
