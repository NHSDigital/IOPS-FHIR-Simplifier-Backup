## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>The UK Core currently does not align with the ValueSet specified in the PRSB Core Information Standard for Encounter Service (Encounter.serviceType profile element).</td>
<td>The binding for the Encounter.serviceType profile element, which is currently to a FHIR standard example ValueSet, will be changed to the UKCoreCareSettingType ValueSet</td>
</tr>

</table>

</br>

<b>Detail:</b>

<ul>
<li>The UKCoreCareSettingType ValueSet is composed of the SNOMED Services Simple Reference Set, which aligns with the PRSB Core Information Standard.</li>
<li>The binding strength will be specified as "Preferred" to align with the approach in Proposal 5.</li>
</ul>

