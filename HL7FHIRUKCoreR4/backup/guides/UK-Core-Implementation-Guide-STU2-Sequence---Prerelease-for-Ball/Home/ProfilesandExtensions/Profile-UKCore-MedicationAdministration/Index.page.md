---
topic: Profile-MedicationAdministration-56616
---
# StructureDefinition-UKCore-MedicationAdministration

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMedicationAdministration'
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
	name = 'UKCoreMedicationAdministration'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, snapshot}}
</div>


<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationAdministration, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Timoptol Eye Drops</b> - An example to illustrate a medication administration of eye drops.<br>
 {{pagelink:Example-UKCore-MedicationAdministration-TimoptolEyeDrops}}
</div>
</nocheck>

### Example Usage Scenarios

The following are example usage scenarios for the UK Core Medication Administration profile:

-	To share inpatient or outpatient non-immunization administrations of medication between clinical systems. Example scenarios include inpatient patient transfer from ward-to-ward or hospital-to-hospital, where different clinical systems are in use. For immunisations use the {{pagelink:Profile-Immunization-16790}} resource.
-	To share patient self-administration of medication.
-	To share home-health reporting from medicines administration and monitoring devices.


---

## Profile Specific Implementation Guidance: ##

<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
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
