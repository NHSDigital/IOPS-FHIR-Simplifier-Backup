## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>The use of the "Extensible" binding strength on ValueSets specifying only the use of SNOMED potentially places a burden on many implementations to provide a mapping to a CodeSystem (SNOMED) that either is not used natively or in which legacy data was not recorded, if the FHIR standard requirements relating to the use of a ValueSet with an "Extensible" binding strength are to be adhered to.</td>
<td>The use of the "Extensible" binding strength on ValueSets specifying only the use of SNOMED needs to be reviewed. This also needs to be applied to ValueSets from Sprints 1 to 3. Where the use of "Extensible" is not deemed to be appropriate, the use of "Preferred" will be proposed.</td>
</tr>

</table>

</br>


<b>Detail:</b>

It is the following FHIR standard requirement which potentially places a burden on implementations where SNOMED coding is not currently used or mapped to:

<ul>
<li>"If there is at least one applicable concept in the extensibly-bound value set with a meaning which includes but is more general than the meaning that is intended to be represented by the element in the resource instance, then the code that is used in the instance SHALL be taken from the value set and should be the closest available match for the intended element instance meaning (i.e. neither more general or more specific). However, a more specific code that more completely represents the intended meaning may also be included in the instance as an additional Coding if the data type is CodeableConcept, but it cannot be used instead of the code from the value set. This helps ensure that systems know which codes they should expect to receive and build logic for and it facilitates interoperability."</li>
</ul>

For the purposes of this proposal, the approach to determining whether the use of the "Extensible" binding strength is appropriate or not is based on the number of SNOMED concepts specified within the ValueSet. If the number of concepts is less than 100 then it is proposed to retain the "Extensible" binding strength. Otherwise the suggestion is to change the binding strength to "Preferred". Views are sought on whether this is an appropriate criterium and whether alternative criteria should be considered.

Based on the above, the following proposals are made:

That the binding strength for bindings to the following Sprint 4 ValueSets be changed from "Extensible" to "Preferred":

<ul>
<li>UKCoreBodySite</li>
<li>UKCoreConditionCode</li>
<li>UKCoreDocumentType</li>
<li>UKCoreEncounterType</li>
<li>UKCoreProcedureCode</li>
</ul>

That the binding strength for bindings to the following Sprint 4 ValueSets need not be changed from "Extensible":

<ul>
<li>UKCoreCareSettingType</li>
<li>UKCoreEmergencyCareDischargeStatus</li>
<li>UKCoreListCode</li>
</ul>

That the binding strength for bindings to the following Sprint 1-3 ValueSets be changed from "Extensible" to "Preferred":

<ul>
<li>UKCoreAllergyCode</li>
<li>UKCoreAllergyManifestation</li>
<li>UKCoreAllergySubstance</li>
<li>UKCoreBodySite</li>
<li>UKCoreImmunizationExplanationReason</li>
<li>UKCoreMedicationForm</li>
<li>UKCoreMedicationPrecondition</li>
<li>UKCoreMedicationTradeFamily</li>
<li>UKCoreVaccinationProcedure</li>
</ul>

That the binding strength for bindings to the following Sprints 1-3 ValueSets need not be changed from "Extensible":

<ul>
<li>UKCoreImmunizationAdministrationBodySite</li>
<li>UKCoreMedicationDosageMethod</li>
<li>UKCoreReasonImmunizationNotAdministered</li>
<li>UKCoreSubstanceOrProductAdministrationRoute</li>
</ul>
