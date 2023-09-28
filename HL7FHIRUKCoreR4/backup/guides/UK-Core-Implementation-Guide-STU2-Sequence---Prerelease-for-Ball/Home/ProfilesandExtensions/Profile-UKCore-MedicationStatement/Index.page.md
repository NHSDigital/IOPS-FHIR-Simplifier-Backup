---
topic: Profile-MedicationStatement-34649
---
# StructureDefinition-UKCore-MedicationStatement

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMedicationStatement'
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
	name = 'UKCoreMedicationStatement'
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
<br>{{pagelink:Example-UKCore-MedicationStatement-Amoxicillin}}
<br><br>
<b>Extension - LastIssueDate</b> - An example to illustrate the LastIssueDate extension.
<br>{{pagelink:Example-UKCore-MedicationStatement-Extension-LastIssueDate}}
<br><br>
<b>Extension - PrescribingOrg</b> - An example to illustrate the PrescribingOrg extension.
<br>{{pagelink:Example-UKCore-MedicationStatement-Extension-PrescribingOrg}}
<br><br>
<b>Extension - PharmacistVerifiedIndicator</b> - An example to illustrate the PharmacistVerifiedIndicator extension. 
<br>{{pagelink:Example-UKCore-MedicationStatement-Extension-PharmacistVerifiedIndicator}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationStatement profile:

- Query and retrieve a patient's current medication
- Record or update a patient's current medication.

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
<td><code>MedicationStatement.identifier</code></td>
<td>Allow the resource to be referenced within/by other resources.</td>
</tr>
<tr>
<td><code>MedicationStatement.basedOn</code></td>
<td>To reference to a <code>MedicationRequest</code> resource, where applicable.</td>
</tr>
<tr>
<td><code>MedicationStatement.status</code></td>
<td>A code representing the patient or other source's judgement about the state of the medication used that this statement is about.</td>
</tr>
<tr class="balloted">
<td><code>MedicationStatement.category</code></td>
<td>Indicates where the medication is expected to be consumed or administered.
</td>
</tr>
<tr>
<td><code>MedicationStatement.medication[x]</code></td>
<td>Identifies the medication being administered. </td>
</tr>
<tr>
<td><code>MedicationStatement.subject</code></td>
<td>Who is/was taking the medication.</td>
</tr>
<tr>
<td><code>MedicationStatement.effective[x]</code></td>
<td>To timestamp the statement</td>
</tr>
<tr>
<td><code>MedicationStatement.dateAsserted</code></td>
<td>To timestamp the statement assertion</td>
</tr>
<tr>
<td><code>MedicationStatement.informationSource</code></td>
<td>To reference other resources, where applicable</td>
</tr>
<tr>
<td><code>MedicationStatement.derivedFrom</code></td>
<td>To reference other resources, where applicable</td>
</tr>
<tr>
<td><code>MedicationStatement.dosage</code></td>
<td>For the dosage for the statement</td>
</tr>
</table>

---