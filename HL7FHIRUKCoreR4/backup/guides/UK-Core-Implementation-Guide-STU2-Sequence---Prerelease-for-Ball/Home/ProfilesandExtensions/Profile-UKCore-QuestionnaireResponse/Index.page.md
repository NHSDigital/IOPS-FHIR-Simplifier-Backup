---
topic: Profile-QuestionnaireResponse-37290
---
## StructureDefinition-UKCore-QuestionnaireResponse

<div  id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 5. This is a new Profile added to UK Core and undergoing review in this STU2 ballot.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreQuestionnaireResponse'
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
	name = 'UKCoreQuestionnaireResponse'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Baby Patient Survey</b> - An example to illustrate a questionnaire response regarding a baby patient survey.
  <br>
  {{pagelink:Example-UKCore-QuestionnaireResponse-BabyPatientSurvey}}
  <br><br>
  <b>Inpatient Survey Response</b> - An example to illustrate a questionnaire response regarding an in-patient survey.
  <br>
  {{pagelink:Example-UKCore-QuestionnaireResponse-InpatientSurvey}}
</div>
</nocheck>

### Example Usage Scenarios ###

The following are example usage scenarios for the UK Core QuestionnaireResponse profile:
- Query for details of a questionnaire response
- Exchange questionnaire response information within a FHIR document or message.

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
<td><code>QuestionnaireResponse.identifier</code></td>
<td>Unique id for this set of answers.</td>
</tr>
<tr>
<td><code>QuestionnaireResponse.questionnaire</code></td>
<td>The Questionnaire that defines and organises the questions for which answers are being provided.
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

---
