---
topic: Profile-RelatedPerson
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson
usage: http://hl7.org/fhir/StructureDefinition/RelatedPerson
issue: UKCore-RelatedPerson
---
# StructureDefinition-UKCore-RelatedPerson

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}} 
<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Related Person</b> - An example to illustrate a person who is related to the patient.
  <br>
{{pagelink:Example-UKCore-RelatedPerson-JoySmith}}
<br><br>
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
