---
topic: Profile-Organization
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization
---
# StructureDefinition-UKCore-Organization

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>General Practice</b> - Example to illustrate a General Practice organisation.
</br>{{pagelink:Example-UKCore-Organization-WhiteRoseMedicalCentre}}   <br><br>

<b>Hospital</b> - Example to illustrate a Hospital organisation.
</br>{{pagelink:Example-UKCore-Organization-LeedsTeachingHospital}}   <br><br>

<b>Main Location</b> - Example to illustrate the mainLocation extension.
</br>{{pagelink:Example-UKCore-Extension-MainLocation}}   <br><br>

<b>Organization Period</b> - Example to illustrate the core-defined organization-period extension.
</br>{{pagelink:Example-UKCore-Extension-OrganizationPeriod}}
</div>


<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Organization/~issues?level=File">Report Issue for UKCore-Organization</a>.
</div>
</nocheck>

### Example Usage Scenarios ###

- Query for organisation information using the query parameter identifier `Organization.identifier` for a known ODS code.
- Exchange organisation information within a FHIR document or message.

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
<td><code>Organization.identifier</code></td>
<td>Identifies this organization across multiple systems</td>
</tr>
<tr>
<td><code>Organization.identifier.system</code></td>
<td>a URL that describes a set values that are unique.</td>
</tr>
<tr>
<td><code>Organization.identifier.value</code></td>
<td>The value that is unique</td>
</tr>
<tr>
<td><code>Organization.active</code></td>
<td>Whether the organization's record is still in active use</td>
</tr>
<tr>
<td><code>Organization.name</code></td>
<td>A name associated with the organization.</td>
</tr>
<tr>
<td><code>Organization.telecom</code></td>
<td>A contact detail for the organization.</td>
</tr>
<tr>
<td><code>Organization.address</code></td>
<td>An address for the organization.</td>
</tr>
</table>

---