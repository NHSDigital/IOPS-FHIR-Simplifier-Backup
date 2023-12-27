---
topic: Profile-QuestionnaireResponse
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse
---
# StructureDefinition-UKCore-QuestionnaireResponse

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreQuestionnaireResponse'
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
	name = 'UKCoreQuestionnaireResponse'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
  <button class="tablinks" onclick="openTab(event, 'Detailed View')">Detailed View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree, buttons}}
</div>

<div id="Detailed View" class="tabcontent">
  <h3>Detailed Descriptions</h3>
{{dict}}
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
  <b>Baby Patient Survey</b> - An example to illustrate a questionnaire response regarding a baby patient survey.
  <br>{{pagelink:Example-UKCore-QuestionnaireResponse-BabyPatientSurvey}}
  <br><br>
  <b>End of Life Survey</b> - An example to illustrate a questionnaire response regarding an end of life plan survey.
  <br>{{pagelink:Example-UKCore-QuestionnaireResponse-EOLPlan}}
  <br><br>
  <b>Fitness For Work Survey</b> - An example to illustrate a questionnaire response regarding a fitness for work survey.
  <br>{{pagelink:Example-UKCore-QuestionnaireResponse-FitnessForWork}}
  <br><br>
  <b>Inpatient Survey Response</b> - An example to illustrate a questionnaire response regarding an in-patient survey.
  <br>{{pagelink:Example-UKCore-QuestionnaireResponse-InpatientSurvey}}
</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse'
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
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse'
```
</span>
</div>

<div id="Feedback" class="tabcontent">
  <h3>Feedback</h3>
Click here to <a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-QuestionnaireResponse/~issues?level=File">Report Issue for UKCore-QuestionnaireResponse</a>.
</div>
</nocheck>

### Example Usage Scenarios ###

The following are example usage scenarios for the UK Core QuestionnaireResponse profile:
- Query for details of a questionnaire response
- Exchange questionnaire response information within a FHIR document or message.

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
<td><code>QuestionnaireResponse.identifier</code></td>
<td>Unique id for this set of answers.</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.questionnaire</code></td>
<td>The Questionnaire that defines and organizes the questions for which answers are being provided.
</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.status</code></td>
<td>The position of the questionnaire response within its overall lifecycle.
</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.subject</code></td>
<td>The subject of the questions.</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.subject.display</code></td>
<td>Plain text narrative that identifies the resource in addition to the resource reference.
</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.authored</code></td>
<td>Date the answers were gathered.</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.author</code></td>
<td>Person who received and recorded the answers.</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.item</code></td>
<td>A group or question item from the original questionnaire for which answers are provided.
</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.item.linkId</code></td>
<td>Pointer to specific item from Questionnaire.</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.item.answer</code></td>
<td>The response(s) to the question.</td>
</tr>
</table>

<hr class="thickline">
