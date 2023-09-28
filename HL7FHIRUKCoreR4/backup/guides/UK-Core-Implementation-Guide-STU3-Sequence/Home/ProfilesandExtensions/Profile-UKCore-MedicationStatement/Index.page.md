---
topic: Profile-MedicationStatement
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement
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
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Amoxicillin</b> - An example to illustrate a medication statement of Amoxicillin.
<br>{{pagelink:Example-UKCore-MedicationStatement-Amoxicillin}}
<br><br>
<b>Last Issue Date</b> - An example to illustrate the LastIssueDate extension.
<br>{{pagelink:Example-UKCore-Extension-LastIssueDate}}
<br><br>
<b>Medication Prescribing Organization Type</b> - An example to illustrate the MedicationPrescribingOrganizationType extension.
<br>{{pagelink:Example-UKCore-Extension-MedicationPrescribingOrganizationType}}
<br><br>
<b>Pharmacist Verified Indicator</b> - An example to illustrate the PharmacistVerifiedIndicator extension. 
<br>{{pagelink:Example-UKCore-Extension-PharmacistVerifiedIndicator}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement'
  and status = 'active'
```
</span>
<br><br>
  This Profile is referenced in the following Extensions: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement'
```
</span>
<br><br>
  This Profile is referenced in the following Profiles: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type !='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core MedicationStatement profile:

- Query and retrieve a patient's current medication
- Record or update a patient's current medication.

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
<tr>
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