---
topic: Profile-Slot
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot
---
# StructureDefinition-UKCore-Slot

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreSlot'
select
	Canonical_URL: url,
  Status: status,
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
	name = 'UKCoreSlot'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Available Walk In Visit</b> - An example to illustrate a slot regarding a walk in visit.
  <br>
  {{pagelink:Example-UKCore-Slot-AvailableWalkInVisit}}
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
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Slot/~issues?level=File">Report Issue for UKCore-Practitioner</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Slot profile:
- Query for slot information from a given schedule
- Exchange slot information within a FHIR document or message.

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
<td><code>Slot.specialty</code></td>
<td>The specialty of a practitioner that would be required to perform the service requested in this appointment.</td>
</tr>
<td><code>Slot.appointmentType</code></td>
<td>The style of appointment or patient that may be booked in the slot.</td>
</tr>
<td><code>Slot.status</code></td>
<td>The status of the slot, e.g free, busy, etc.</td>
</tr>
<td><code>Slot.start</code></td>
<td>Date/Time that the slot is to begin.</td>
</tr>
<td><code>Slot.end</code></td>
<td>Date/Time that the slot is to conclude.</td>
</tr>
</table>

---