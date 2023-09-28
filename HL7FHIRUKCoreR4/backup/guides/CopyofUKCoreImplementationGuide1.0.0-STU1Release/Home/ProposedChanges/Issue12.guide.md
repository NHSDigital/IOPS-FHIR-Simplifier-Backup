## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>Three of the Sprint 4 UK Core profiles have elements that are currently bound to the UKCoreConditionCode ValueSet. However, this ValueSet is not composed of the same content as the three equivalent PRSB Core Information Standard data items. The profiles/element concerned are: Condition.code, Procedure.complication and Extension-UKCoreAnaestheticIssues.value[x].</td>
<td>The UK Core ValueSet bindings for these elements are changed where necessary to match the mappings provided in the PRSB Core Information Standard, which are currently being reviewed.</td>
</tr>

</table>

</br>

<b>Detail:</b>

<ul>
<li>Currently the PRSB Core Information Standard for Problem / Coded Value is the SNOMED Health issues simple reference set. It is proposed that the Content Logical Definition of the UKCoreConditionCode ValueSet will be changed to align.</li>
<li>For Complications related to Procedure, the PRSB Core Information Standard maps to the SNOMED <404684003 |Clinical finding (finding)| hierarchy. This is being reviewed by PRSB. If no change is made or the Core Information Standard mapping changes to something other that the SNOMED Health issues simple reference set, it is proposed that the UK Core binding for Procedure.complication will be to a new UK Core ValueSet which matches the mapping provided in the Core Information Standard. If the Core Information Standard changes to the SNOMED Health issues simple reference set then the binding can remain as it currently is.</li>
<li>For Anaesthetic Issues, the PRSB Core Information Standard doesn't currently specify a specific subset of SNOMED. This is also being reviewed by PRSB, and the UK Core binding will remain unchanged if the Core Information Standard maps to the SNOMED Health issues simple reference set, otherwise the binding will be to a new UK Core ValueSet which matches the mapping provided in the Core Information Standard. Review comments are also requested on the appropriateness of the Extension UK Core Anaesthetic Issues as it is currently defined: should a reference to another profile be used within the extension instead of an element to carry a CodeableConcept, and if so which profile or profiles should be considered for such a reference, for example?</li>
</ul>

