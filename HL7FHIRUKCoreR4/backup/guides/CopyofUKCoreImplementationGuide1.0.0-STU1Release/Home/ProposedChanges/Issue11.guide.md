## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>The UK Core currently does not align with the ValueSet specified in the PRSB Core Information Standard for Encounter Location Type (Encounter.location.physicalType profile element).</td>
<td>The binding for the Encounter.location.physicalType element, which is currently to a FHIR standard example ValueSet, will be changed to a new UK Core ValueSet in order to align with the PRSB Core Information Standard.</td>
</tr>

</table>

</br>

<b>Detail:</b>

<ul>
<li>The new UK Core ValueSet, proposed to have the name UKCoreLocationType, will be required to support concepts from a new CodeSystem copied from "NHS Data Dictionary Activity Location Type Code" (<a href="https://datadictionary.nhs.uk/data_elements/activity_location_type_code.html?hl=activity%2Clocation%2Ctype%2Ccode">https://datadictionary.nhs.uk/data_elements/activity_location_type_code.html?hl=activity%2Clocation%2Ctype%2Ccode</a>) and also an equivalent CodeSystem from NHS Wales with concepts copied from <a href="http://www.datadictionary.wales.nhs.uk/#!WordDocuments/locationtypecode.htm">http://www.datadictionary.wales.nhs.uk/#!WordDocuments/locationtypecode.htm</a>).</li>
<li>The ValueSet will be constructed according to the approach outlined in Proposal 3.</li>
<li>The binding strength will be specified as "Extensible".</li>
</ul>

