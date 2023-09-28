---
topic: Profile-PractitionerRole
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole
---
# StructureDefinition-UKCore-PractitionerRole

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCorePractitionerRole'
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
	name = 'UKCorePractitionerRole'
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
<b>Patient's GP</b>- An example to illustrate the role of General Practitioner.
<br>
{{pagelink:Example-UKCore-PractitionerRole-GP}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core PractitionerRole profile:

- Query for a Practitioner role using the query parameter identifier `PractitionerRole.identifier` for a known SDS Role Id.
- Query for a Practitioner using query parameters such as specialty `PractitionerRole.specialty` for a known specialty.
- Exchange Practitioner role information within a FHIR document or message.

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
<td><code>PractitionerRole.active</code></td>
<td>Whether this practitioner role record is in active use</td>
</tr>
<tr>
<td><code>PractitionerRole.period</code></td>
<td>The period during which the practitioner is authorized to perform in these role(s)</td>
</tr>
<tr>
<td><code>PractitionerRole.practitioner</code></td>
<td>Practitioner that is able to provide the defined services for the organization</td>
</tr>
<tr>
<td><code>PractitionerRole.organization</code></td>
<td>Organization where the roles are available</td>
</tr>
<tr>
<td><code>PractitionerRole.specialty</code></td>
<td>Specific specialty of the practitioner</td>
</tr>
<tr>
<td><code>PractitionerRole.location</code></td>
<td>The location(s) at which this practitioner provides care</td>
</tr>
<tr>
<td><code>PractitionerRole.telecom</code></td>
<td>Contact details that are specific to the role/location/service</td>
</tr>
<tr>
<td><code>PractitionerRole.telecom.system</code></td>
<td>Telecommunications form for contact point</td>
</tr>
<tr>
<td><code>PractitionerRole.telecom.value</code></td>
<td>The actual contact point details</td>
</tr>
</table>

---