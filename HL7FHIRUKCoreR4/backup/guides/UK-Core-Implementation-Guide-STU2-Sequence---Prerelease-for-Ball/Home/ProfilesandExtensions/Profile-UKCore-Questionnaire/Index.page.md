---
topic: Profile-Questionnaire-47615
---
# StructureDefinition-UKCore-Questionnaire

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreQuestionnaire'
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
	name = 'UKCoreQuestionnaire'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Inpatient Survey</b> - An example to illustrate a questionnaire regarding an in-patient survey.
<br>{{pagelink:Example-UKCore-Questionnaire-InpatientSurvey}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Questionnaire profile:
- Query for details of a questionnaire
- Exchange questionnaire information within a FHIR document or message.

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
<td><code>Questionnaire.url</code></td>
<td>Canonical identifier for this questionnaire, represented as a URI (globally unique).</td>
</tr>
<tr>
<td><code>Questionnaire.title</code></td>
<td>Name for this questionnaire (human friendly).</td>
</tr>
<tr>
<td><code>Questionnaire.status</code></td>
<td>The status of this questionnaire. Enables tracking the life-cycle of the content.
</td>
</tr>
<tr>
<td><code>Questionnaire.subjectType</code></td>
<td>Resource that can be subject of QuestionnaireResponse.</td>
</tr>
<tr>
<td><code>Questionnaire.item</code></td>
<td>Questions and sections within the Questionnaire.</td>
</tr>
<tr>
<td><code>Questionnaire.item.linkId</code></td>
<td>Unique id for item in questionnaire.</td>
</tr>
<tr>
<td><code>Questionnaire.item.text</code></td>
<td>The text of a question.</td>
</tr>
<tr>
<td><code>Questionnaire.item.type</code></td>
<td>Defines the format in which the user is to be prompted for the answer.</td>
</tr>
</table>

---
