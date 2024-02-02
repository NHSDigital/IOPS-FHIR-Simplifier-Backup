---
topic: Profile-Task
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task
usage: http://hl7.org/fhir/StructureDefinition/Task
issue: UKCore-Task
---
# StructureDefinition-UKCore-Task

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Colonoscopy</b> - An example to illustrate a task regarding a colonoscopy.
  <br>
  {{pagelink:Example-UKCore-Task-Colonoscopy}}
  <br><br>
</div>
</nocheck>

<div id="ProfileGuidance">

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
</div>

---
