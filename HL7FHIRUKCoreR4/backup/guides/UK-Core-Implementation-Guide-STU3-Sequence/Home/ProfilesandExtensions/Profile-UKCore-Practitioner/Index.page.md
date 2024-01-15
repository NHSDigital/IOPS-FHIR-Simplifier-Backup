---
topic: Profile-Practitioner
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner
---
# StructureDefinition-UKCore-Practitioner

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>General Practitioner</b> - An example to illustrate a practitioner who is the Patient's GP. 
<br>
{{pagelink:Example-UKCore-Practitioner-DoctorPaulRastall}}
<br><br>
<b>Consultant</b> - An example to illustrate a practitioner who is a Consultant. 
<br>
{{pagelink:Example-UKCore-Practitioner-ConsultantSandraGose}}
<br><br>
<b>Pharmacist</b> - An example to illustrate a practitioner who is a Pharmacist.
<br>
{{pagelink:Example-UKCore-Practitioner-PharmacistJimmyChuck}}
<br><br>
Note: the practitioner's role information is carried in the {{pagelink:Profile-PractitionerRole}}   <br><br>
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Practitioner/~issues?level=File">Report Issue for UKCore-Practitioner</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Practitioner profile:

- Query for practitioner information using the query parameter identifier (`Practitioner.identifier`) for a known SDS User Identifier.
- Exchange practitioner information within a FHIR document or message.

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
<td><code>Practitioner.identifier</code></td>
<td>An identifier that applies to this person in this role.
</td>
</tr>
<tr>
<td><code>Practitioner.identifier.system</code></td>
<td>The namespace for the identifier value</td>
</tr>
<tr>
<td><code>Practitioner.identifier.value</code></td>
<td>The value that is unique</td>
</tr>
<tr>
<td><code>Practitioner.name</code></td>
<td>The name(s) associated with the practitioner</td>
</tr>
<tr>
<td><code>Practitioner.name.family</code></td>
<td>Family name (often called 'Surname')</td>
</tr>
<tr>
<td><code>Practitioner.telecom</code></td>
<td>A contact detail for the practitioner (that apply to all roles)</td>
</tr>
<tr>
<td><code>Practitioner.telecom.system</code></td>
<td>Telecommunications form for contact point</td>
</tr>
<tr>
<td><code>Practitioner.telecom.value</code></td>
<td>The actual contact point details</td>
</tr>
</table>

---