---
topic: Profile-Schedule
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Schedule
---
# StructureDefinition-UKCore-Schedule

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Immunization</b> - An example to illustrate a schedule regarding an immunization.
<br>
{{pagelink:Example-UKCore-Schedule-Immunization}}
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
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Schedule'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Schedule'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Schedule'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Schedule/~issues?level=File">Report Issue for UKCore-Schedule</a>.
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Schedule profile:
- Query for details of a schedule
- Exchange schedule information within a FHIR document or message.

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
<td><code>Schedule.active</code></td>
<td>Whether this schedule is in active use.</td>
</tr>
<tr>
<td><code>Schedule.specialty</code></td>
<td>Type of specialty needed.</td>
</tr>
<tr>
<td><code>Schedule.actor</code></td>
<td>Resource(s) that availability information is being provided for.</td>
</tr>
<tr>
<td><code>Schedule.planningHorizon</code></td>
<td>Period of time covered by schedule.</td>
</tr>
</table>

---
