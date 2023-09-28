---
topic: Profile-RelatedPerson-51006
---
# StructureDefinition-UKCore-RelatedPerson

<div  id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 5. This is a new Profile added to UK Core and undergoing review in this STU2 ballot.
</div>

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Related Person</b> - An example to illustrate a person who is related to the patient.
  <br>
{{pagelink:Example-UKCore-RelatedPerson}}
<br><br>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core RelatedPerson profile:
- Query for related person information for a given Patient
- Exchange related person information within a FHIR document or message.

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
