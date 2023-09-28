## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>The UK Core currently does not support a data item present in the PRSB Core Information Standard: Legal Status on Admission.</td>
<td>During Sprint 4 Clinical and Technical Assurance calls, it was agreed that the UK Core should also support this data item. It was also agreed that the UK Core should support a Legal Status on Discharge, using the same set of concepts as for Legal Status on Admission.</td>
</tr>

</table>

</br>


<b>Detail:</b>

<ul>
<li>A new extension will be created to support the exchange of a legal status on admission and also a legal status on discharge. The extension will include a type element to indicate whether the use of the extension relates to admission or discharge (this will require a new CodeSystem and ValueSet).</li>
<li>A new ValueSet will be created to support concepts from a new CodeSystem copied from "NHS Data Dictionary Mental health act legal status classification code" (<a href="https://datadictionary.nhs.uk/data_elements/mental_health_act_legal_status_classification_code__on_admission_.html?hl=mental%2Chealth%2Cact%2Clegal%2Cstatus%2Cclassification%2Ccode">https://datadictionary.nhs.uk/data_elements/mental_health_act_legal_status_classification_code__on_admission_.html?hl=mental%2Chealth%2Cact%2Clegal%2Cstatus%2Cclassification%2Ccode</a>) and also an equivalent CodeSystem from NHS Wales with concepts copied from <a href="http://www.datadictionary.wales.nhs.uk/#!WordDocuments/legalstatus.htm">http://www.datadictionary.wales.nhs.uk/#!WordDocuments/legalstatus.htm</a>.</li>
<li>The new ValueSet will be constructed according to the approach outlined in Proposal 3.</li>
</ul>

<b>Profile affected:</b>

<ul>
<li>Encounter</li>
</ul>
