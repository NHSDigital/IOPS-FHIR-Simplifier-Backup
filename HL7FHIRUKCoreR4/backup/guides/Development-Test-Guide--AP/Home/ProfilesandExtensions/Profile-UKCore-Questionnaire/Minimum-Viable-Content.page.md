## Minimum Viable Content

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
