## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>Some Sprint 4 ValueSets contain only a single CodeSystem based on England specific Data Dictionary concepts.</td>
<td>Additional CodeSystems supporting concepts from other UK countries will be incorporated into such ValueSets.</td>
</tr>

</table>

</br>


<b>Detail:</b>

<ul>

<li>Where a ValueSet currently refers to a CodeSystem that is a copy of a set of concepts from the (England) NHS Data Dictionary, the ValueSet will be extended to accommodate additional CodeSystems of equivalent concepts copied from Data Dictionaries from other parts of the UK where requirements can be confirmed by appropriate stakeholders during the course of the development work for Sprint 4. Where requirements cannot be confirmed at this time, it is accepted that the ValueSet can be extended at a later date to support requirements of other UK countries as they become known and available.</li>

<li>Because it is likely that this approach would lead to the same concept being present more than once amongst the CodeSystems that the ValueSet is comprised of, the binding strength for these ValueSets will be set to "Preferred", as the use of "Extensible" is complicated by the presence of such duplicates.</li>

<li>Where currently the CodeSystem name is of the form "NHSDataModelAndDictionary…" this will be changed to begin "UKCore...", as with other UK Core CodeSystems, to reflect the fact that these CodeSystems are not NHS Data Dictionary owned CodeSystems, although they will reflect the content of the NHS Data Dictionary CodeSystem (both codes and descriptions) at the time of creation of the UK Core CodeSystem.</li>

<li>It is accepted that the equivalent Data Dictionary sets of concepts from which the UK Core CodeSystems are composed represent a copy of the concepts available at time of development within Sprint 4, and that these Data Dictionary sets of concepts may change over time to a schedule that is different from UK Core change cycles. It is accepted that the UK Core CodeSystems do not need to dynamically represent to same content as the Data Dictionary equivalents, as such dynamic change could cause problems for implementers.</li>

</ul>

This proposal applies to:


<b>Profile/Element Encounter.hospitalization.admitSource</b>

<ul>
<li>ValueSet UKCoreSourceOfAdmission to be composed of:
<ul>
<li>CodeSystem NHSDataModelandDictionarySourceOfAdmission renamed to UKCoreEnglandSourceOfAdmission and content aligned to latest version of the NHS Data Dictionary content (sourced from <a href="https://datadictionary.nhs.uk/data_elements/source_of_admission_code__hospital_provider_spell_.html">https://datadictionary.nhs.uk/data_elements/source_of_admission_code__hospital_provider_spell_.html</a>)</li>
<li>CodeSystem UKCoreWalesSourceOfAdmission added with content aligned to the latest version of the NHS Wales Data Dictionary content (sourced from <a href="http://www.datadictionary.wales.nhs.uk/#!WordDocuments/sourceofadmission.htm">http://www.datadictionary.wales.nhs.uk/#!WordDocuments/sourceofadmission.htm</a>)</li>
</ul>
</li>
</ul>

<b>Profile/Element Encounter.hospitalization.dischargedisposition</b>

<ul>
<li>ValueSet UKCoreDischargeDestination to be composed of:
<ul>
<li>CodeSystem NHSDataModelandDictionaryDischargeDestination renamed to UKCoreEnglandDischargeDestination and content aligned to latest version of the NHS Data Dictionary content (sourced from <a href="https://datadictionary.nhs.uk/data_elements/discharge_destination_code__hospital_provider_spell_.html">https://datadictionary.nhs.uk/data_elements/discharge_destination_code__hospital_provider_spell_.html</a>)</li>
<li>CodeSystem UKCoreWalesDischargeDestination added with content aligned to the latest version of the NHS Wales Data Dictionary content (sourced from <a href="http://www.datadictionary.wales.nhs.uk/#!WordDocuments/dischargedestination.htm">http://www.datadictionary.wales.nhs.uk/#!WordDocuments/dischargedestination.htm</a>)</li>
</ul>
</li>
</ul>

<b>Extension UK Core Admission Method</b>

<ul>
<li>ValueSet UKCoreAdmissionMethod to be composed of:
<ul>
<li>CodeSystem NHSDataModelandDictionaryAdmissionMethod renamed to UKCoreEnglandAdmissionMethod and content aligned to latest version of the NHS Data Dictionary content (sourced from <a href="https://datadictionary.nhs.uk/data_elements/admission_method_code__hospital_provider_spell_.html">https://datadictionary.nhs.uk/data_elements/admission_method_code__hospital_provider_spell_.html</a>)</li>
<li>CodeSystem UKCoreWalesAdmissionMethod added with content aligned to the latest version of the NHS Wales Data Dictionary content (sourced from <a href="http://www.datadictionary.wales.nhs.uk/#!WordDocuments/admissionmethod.htm">http://www.datadictionary.wales.nhs.uk/#!WordDocuments/admissionmethod.htm</a>)</li>
</ul>
</li>
</ul>

<b>Extension UK Core Discharge Method</b>

<ul>
<li>ValueSet UKCoreDischargeMethod to be composed of:
<ul>
<li>CodeSystem NHSDataModelandDictionaryDischargeMethod renamed to UKCoreEnglandDischargeMethod and content aligned to latest version of the NHS Data Dictionary content (sourced from <a href="https://datadictionary.nhs.uk/data_elements/discharge_method_code__hospital_provider_spell_.html">https://datadictionary.nhs.uk/data_elements/discharge_method_code__hospital_provider_spell_.html</a>)</li>
<li>CodeSystem UKCoreWalesDischargeMethod added with content aligned to the latest version of the NHS Wales Data Dictionary content (sourced from <a href="http://www.datadictionary.wales.nhs.uk/#!WordDocuments/dischargemethod.htm">http://www.datadictionary.wales.nhs.uk/#!WordDocuments/dischargemethod.htm</a>)</li>
</ul>
</li>
</ul>

<b>Extension UK Core Outcome Of Attendance</b>

<ul>
<li>ValueSet UKCoreOutcomeOfAttendance to be composed of:
<ul>
<li>CodeSystem NHSDataModelandDictionaryOutcomeofAttendance renamed to UKCoreEnglandOutcomeOfAttendance and content aligned to latest version of the NHS Data Dictionary content (sourced from <a href="https://datadictionary.nhs.uk/data_elements/outcome_of_attendance_code.html">https://datadictionary.nhs.uk/data_elements/outcome_of_attendance_code.html</a>)</li>
<li>CodeSystem UKCoreWalesOutcomeOfAttendance added with content aligned to the latest version of the NHS Wales Data Dictionary content (sourced from <a href="http://www.datadictionary.wales.nhs.uk/#!WordDocuments/outcomeofattendance.htm">http://www.datadictionary.wales.nhs.uk/#!WordDocuments/outcomeofattendance.htm</a>)</li>
</ul>
</li>
</ul>
