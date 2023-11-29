---
topic: Profile-Task
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task
---
# StructureDefinition-UKCore-Task


<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreTask'
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
	name = 'UKCoreTask'
select
	Profile_Purpose: purpose
```

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-Task/~issues?level=File">Report Issue for UKCore-Task</a>.
</div>
<nocheck>


<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Colonoscopy</b> - An example to illustrate a task regarding a colonoscopy.
  <br>
  {{pagelink:Example-UKCore-Task-Colonoscopy}}
  <br><br>
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Task profile:
- Query for task information
- Exchange task information within a FHIR document or message.

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
<td><code>Task.status</code></td>
<td>The current status of the task.</td>
</tr>
<tr>
<td><code>Task.intent</code></td>
<td>Indicates the "level" of actionability associated with the task.</td>
</tr>
<tr>
<td><code>Task.code</code></td>
<td>A name or code (or both) briefly describing what the task involves.</td>
</tr>
<tr>
<td><code>Task.focus</code></td>
<td>The request being actioned or the resource being manipulated by this task.</td>
</tr>
<tr>
<td><code>Task.for</code></td>
<td>Beneficiary of the task.</td>
</tr>
<tr>
<td><code>Task.authoredOn</code></td>
<td>Task creation date.</td>
</tr>
<tr>
<td><code>Task.requester</code></td>
<td>Who is asking for task to be done.</td>
</tr>
<tr>
<td><code>Task.owner</code></td>
<td>Responsible individual.</td>
</tr>
<tr>
<td><code>Task.reasonCode</code></td>
<td>Why task is needed.</td>
</tr>
<tr>
<td><code>Task.restriction</code></td>
<td>Constraints on fulfilment tasks.</td>
</tr>
<tr>
<td><code>Task.restriction.period</code></td>
<td>Over what time-period is fulfilment sought.
</td>
</tr>
<tr>
<td><code>Task.input</code></td>
<td>Information used to perform task.</td>
</tr>
</table>

<hr class="thickline">
