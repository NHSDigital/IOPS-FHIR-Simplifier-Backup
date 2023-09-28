---
topic: Profile-Task-90615
---
# StructureDefinition-UKCore-Task

<div  id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 5. This is a new Profile added to UK Core and undergoing review in this STU2 ballot.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreTask'
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
	name = 'UKCoreTask'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Colonoscopy</b> - An example to illustrate a task regarding a colonoscopy.
  <br>
  {{pagelink:Example-UKCore-Task-Colonoscopy}}
  <br><br>
</div>
<nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Task profile:
- Query for task information
- Exchange task information within a FHIR document or message.

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

---
