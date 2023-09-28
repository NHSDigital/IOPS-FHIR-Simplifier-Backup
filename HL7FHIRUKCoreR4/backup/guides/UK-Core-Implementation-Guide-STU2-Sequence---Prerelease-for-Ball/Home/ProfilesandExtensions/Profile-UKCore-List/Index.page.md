---
topic: Profile-List-19037
---
# StructureDefinition-UKCore-List

<div id="newAsset"  markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 4. This is a new Profile added to UK Core and undergoing review in this STU2 ballot.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreList'
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
	name = 'UKCoreList'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-List, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

<b>Empty List</b> - This example shows the use of an empty List to indicate that there is no content. This is not supposed to represent actual system behaviour.
<br>{{pagelink:Example-UKCore-List-EmptyList}}
<br><br>
<b>Bundled Allergy List</b> - This example is an example FHIR Bundle that could be returned following a query for the allergies for a patient. Note: the use of List and Bundle is not mandated and is used to illustrate a possible use of the List Profile and is not expected system behaviour.<br>
{{pagelink:Example-UKCore-Bundle-BundledAllergyList}}
</div>
</nocheck>

## Example Usage Scenarios ##
The following are example usage scenarios for the UK Core List profile:

- A list of allergies for a Patient
- A list of current medication for a Patient
- Record or update a list of information for Patient

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
<td><code>List.status</code></td>
<td>Indicates the current state of this list.</td>
</tr>
<tr>
<td><code>List.code</code></td>
<td>This code defines the purpose of the list - why it was created.</td>
</tr>
<tr>
<td><code>List.subject</code></td>
<td>The common subject (or patient) of the resources that are in the list if there is one.</td>
</tr>
</table>

---