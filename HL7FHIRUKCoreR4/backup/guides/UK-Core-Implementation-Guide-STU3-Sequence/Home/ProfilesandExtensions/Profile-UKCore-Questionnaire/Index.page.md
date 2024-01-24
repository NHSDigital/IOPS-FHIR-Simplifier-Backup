---
topic: Profile-Questionnaire
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Questionnaire
usage: http://hl7.org/fhir/StructureDefinition/Questionnaire
issue: UKCore-Questionnaire
---
# StructureDefinition-UKCore-Questionnaire

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>End of Life Survey</b> - An example to illustrate a questionnaire regarding an end of life plan survey.
<br>{{pagelink:Example-UKCore-Questionnaire-EOLPlan}}
  <br><br>
<b>Fitness For Work Survey</b> - An example to illustrate a questionnaire regarding a fitness for work survey.
<br>{{pagelink:Example-UKCore-Questionnaire-FitnessForWork}}
  <br><br>
<b>Inpatient Survey</b> - An example to illustrate a questionnaire regarding an in-patient survey.
<br>{{pagelink:Example-UKCore-Questionnaire-InpatientSurvey}}
</div>
</nocheck>

<div id="ProfileGuidance">

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
</div>

---
