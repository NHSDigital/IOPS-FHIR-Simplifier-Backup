---
topic: Profile-Flag
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Flag
usage: http://hl7.org/fhir/StructureDefinition/Flag
issue: UKCore-Flag
---
# StructureDefinition-UKCore-Flag

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Food Allergy</b> - An example to illustrate a flag regarding a food allergy.
<br>{{pagelink:Example-UKCore-Flag-FoodAllergy}}
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Flag profile:
- Query for flag information for a given Patient
- Exchange flag information within a FHIR document or message.

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
<td><code>Flag.status</code></td>
<td>Supports basic workflow.</td>
</tr>
<tr>
<td><code>Flag.code</code></td>
<td>The coded value or textual component of the flag to display to the user.</td>
</tr>
<tr>
<td><code>Flag.subject</code></td>
<td>The patient, location, group, organization, or practitioner etc. this is about record this flag is associated with.</td>
</tr>
</table>
</div>

---