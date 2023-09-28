---
topic: Profile-Questionnaire
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire
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
<b>Inpatient Survey</b> - An example to illustrate a questionnaire regarding an in-patient survey.
<br>{{pagelink:Example-UKCore-Questionnaire-InpatientSurvey}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Questionnaire profile:
- Query for details of a questionnaire
- Exchange questionnaire information within a FHIR document or message.

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
