---
topic: Profile-QuestionnaireResponse
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-QuestionnaireResponse
usage: http://hl7.org/fhir/StructureDefinition/QuestionnaireResponse
issue: UKCore-QuestionnaireResponse
---
# StructureDefinition-UKCore-QuestionnaireResponse

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

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
</nocheck>


<div id="ProfileGuidance">

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
</div>

---
