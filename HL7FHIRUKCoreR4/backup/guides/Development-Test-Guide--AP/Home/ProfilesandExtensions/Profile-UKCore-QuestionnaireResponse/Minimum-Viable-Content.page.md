## Minimum Viable Content

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

---
