---
topic: Profile-RelatedPerson
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson
---
# StructureDefinition-UKCore-RelatedPerson

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreRelatedPerson'
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
	name = 'UKCoreRelatedPerson'
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
  <b>Related Person</b> - An example to illustrate a person who is related to the patient.
  <br>
{{pagelink:Example-UKCore-RelatedPerson-JoySmith}}
<br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core RelatedPerson profile:
- Query for related person information for a given Patient
- Exchange related person information within a FHIR document or message.

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
<td><code>RelatedPerson.active</code></td>
<td>Whether this related person's record is in active use.</td>
</tr>
<tr>
<td><code>RelatedPerson.patient</code></td>
<td>The patient this person is related to.</td>
</tr>
<tr>
<td><code>RelatedPerson.relationship</code></td>
<td>The nature of the relationship.</td>
</tr>
<tr>
<td><code>RelatedPerson.name</code></td>
<td>A name associated with the person.</td>
</tr>
<tr>
<td><code>RelatedPerson.telecom</code></td>
<td>A contact detail for the person.</td>
</tr>
<tr>
<td><code>RelatedPerson.address</code></td>
<td>Address where the related person can be contacted or visited.</td>
</tr>
<tr>
<td><code>RelatedPerson.address.line</code></td>
<td>Street name, number, direction & P.O. Box etc.</td>
</tr>
<tr>
<td><code>RelatedPerson.address.city</code></td>
<td>Name of city, town etc.</td>
</tr>
<tr>
<td><code>RelatedPerson.address.postalCode</code></td>
<td>Postal code for area.</td>
</tr>
</table>

---
