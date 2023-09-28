## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>No UK Core specific ValueSet is present in the UK Core to support three of the concepts that were available in the Care Connect ValueSet for the Condition.category element.</td>
<td>During Sprint 4 Clinical and Technical Assurance calls, it was agreed that the UK Core should also support those three concepts that were previously available in the Care Connect version (Presenting Complaint | Co-morbidity | Issue).</td>
</tr>

</table>

</br>

<b>Detail:</b>

<ul>
<li>A new UK Core CodeSystem will be created to support the three additional concepts.</li>
<li>A new UK Core ValueSet will be created, composed of the condition-category CodeSystem used by the FHIR standard ValueSet for the Condition.category element (with concepts: Problem List Item | Encounter Diagnosis) and the newly created UK Core CodeSystem.</li>
<li>The binding strength will be specified as "Extensible".</li>
</ul>
