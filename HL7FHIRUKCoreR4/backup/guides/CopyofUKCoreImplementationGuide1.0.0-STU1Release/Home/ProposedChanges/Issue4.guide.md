## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>The use of slicing for elements where a UK Core ValueSet is specified with just SNOMED content is still present in some Sprint 4 profiles. Such slicing was removed from profiles covered by Sprints 1 to 3, as the slicing was only used to structurally allow for the inclusion of the Extension UKCoreCodingSCTDescId and a decision was made to use guidance to describe when and how to use that extension instead.</td>
<td>Where a SNOMED slice has been specified, the slice will be removed and any UK Core binding that had been applied to that slice will be moved to the element which has been sliced.</td>
</tr>

</table>

</br>


<b>This proposal applies to the following profiles/elements:</b>

<ul>
<li>Condition.code</li>
<li>Condition.bodySite</li>
<li>Encounter.type</li>
<li>Encounter.hospitalization.reAdmission</li>
<li>Procedure.code</li>
<li>Procedure.bodySite</li>
<li>Procedure.complication</li>
</ul>
