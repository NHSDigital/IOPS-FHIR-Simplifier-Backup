## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>For both Questionnaire.code and Questionnaire.item.code there is an example binding to a FHIR standard ValueSet with a definition of the whole of LOINC. LOINC is generally not used in the UK.
</td>
<td>Create a UKCore-SNOMEDCT ValueSet consisting of the whole of SNOMED CT.

Change the binding of Questionnaire.code to the new UKCore-SNOMEDCT ValueSet. This reflects a more preferred default CodeSystem for the UK Core than LOINC but may require further discussion in the future.

For the Questionnaire.item.code element, SNOMED CT is not a suitable default CodeSystem. In the absence of any specific CodeSystem requirements at this level, the proposal is to remove the current FHIR standard binding and leave this element unbound.<br/><br/>Update 12/05/2022:<br/>- The ValueSet used for binding to the Questionnaire.code element has been called UKCore-QuestionnaireQuestionCodes.<br/>- No change to the binding of the Questionnaire.item.code element has been made as it has not been possible to revert to unbound where a binding has already been specified in the FHIR standard profile. 
</td>
</tr>

</table>