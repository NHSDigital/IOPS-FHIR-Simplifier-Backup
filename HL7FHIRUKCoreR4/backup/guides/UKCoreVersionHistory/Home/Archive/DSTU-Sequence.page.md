## {{page-title}}

This archive contains older versions of UK Core which were developed as part of the intial decovery known as DSTU Sequence. These were developed in another Simplifer organisation project, are deprecated and are no longer available. Some further information is available below.

## DSTU Sequence

<table id="assets">
<tr>
<th width="5%">Date</th>	
<th width="10%">IG Version</th>
<th width="5%">FHIR Version</th>	
<th Width="50%">Description</th>	
</tr>
<tr>
<th colspan="4">DSTU Sequence (Historical) Note: These Implementation Guides are archived and not publicly available.</th>
<tr>
<td>Pre-release</td>
<td>DSTU(pre-release)</td>
<td>4.0.1</td>
<td>Pre-migration to HL7 account development versions.</td>
</tr>
<table/>

## Additional Release Notes for Medication 

These changes were agreed during the external consultation call on 25th June 2021 9:30-11:30.

## Overview of changes

<table id="assets">
<tr>
<th width="5%">Number</th>
<th width="40%">Issue</th>
<th width="40%">Change</th>
</tr>
<tr>
<td>1</td>

<td>The UKCoreMedicationCode ValueSet needs to refer to dm+d sets of codes instead of SNOMED reference sets.</td>
<td>The description and composition of the ValueSet will be changed.</td>
</tr>
<tr>
<td>2</td>

<td>Within the Medication profiles, the binding for the dosage.site or dosageInstruction.site element needs to be changed to a value set referring to the anatomical or acquired body structure SNOMED hierarchy, to align with the Core Information Standard.</td>
<td>The existing UK Core Body Site value set will be added into the UK Core DSTU as this already refers to the appropriate SNOMED hierarchy, and the dosage.site or dosageInstruction.site element in affected profiles will be bound to this value set. The Dose Syntax IG will also be aligned with this change. The description and composition of the value set will be modified to align with equivalent changes made to these fields in other value sets in the UK Core.</td>
</tr>
<tr>
<td>3</td>

<td>Within the Medication profiles, the binding for the dosage.method element needs to be changed to a value set referring to the SNOMED ePrescribing Method reference set, to align with the Dose Syntax IG.</td>
<td>A new UK Core Value Set will be created and the dosage.method element in affected profiles will be bound to this new value set. The Core Information Standard will also be aligned with this change.</td>
</tr>
<tr>
<td>4</td>

<td>Within the Medication profiles, the binding for the dosage.asNeeded element needs to be changed to a value set referring to the SNOMED Health issues reference set instead of the current Clinical Finding SNOMED hierarchy.</td>
<td>A new UK Core Value Set will be created and the dosage.asNeeded element in affected profiles will be bound to this new value set. The Dose Syntax IG will also be aligned with this change, as will the Core Information Standard.</td>
</tr>
<tr>
<td>5</td>

<td>The UKCoreVaccineCode value set needs to refer to dm+d sets of codes instead of SNOMED reference sets.</td>
<td>The description and composition of the UKCoreVaccineCode value set will be changed to refer to the appropriate dm+d concept classes.</td>
</tr>
<tr>
<td>6</td>

<td>Within the Immunization profile, the binding for the site element needs to be changed to a value set referring to a SNOMED Vaccine body site of administration reference set instead of the current HL7 example CodesForImmunizationSiteOfAdministration binding, to align with the Core Information Standard.</td>
<td>A new UK Core Value Set will be created and the site element in the affected profile will be bound to this new value set.</td>
</tr>
<tr>
<td>7</td>

<td>The UKCoreVaccinationProcedureCode value set needs review as some of the hierarchies are out of date and it does not align with the Core Information Standard.</td>
<td>The Vaccination Procedure value set will be amended to be composed of concepts from the following three SNOMED herarchies (including the hierarchy concepts themselves):
<li>'Active or passive immunisation'</li>
<li>'Seasonal influenza vaccination given by midwife'</li>
<li>'Vaccination given'</li>
The Core Information Standard will also be amended to align with this.
</td>
</tr>
<tr>
<td>8</td>

<td>The UKCoreImmunizationExplanationReason value set needs to refer to a SNOMED Healthcare matters reference set instead of the current set of 12 specific SNOMED concepts.</td>
<td>The description and composition of the UKCoreImmunizationExplanationReason value set will be changed to refer to the appropriate SNOMED reference set.</td>
</tr>
<tr>
<td>9</td>

<td>Within the Medication profile, the cardinality of the code element is optional, meaning a Medication resource can validly have no identification of an actual medication. There is no recognised use case within the UK Core when either a coded or a free text medication cannot be provided.</td>
<td>The cardinality of the code element within the Medication profile will be changed to 1..1.</td>
</tr>
<tr>
<td>10</td>

<td>Currently two separate value sets are used to refer to the same SNOMED reference set, to carry the exposure route of an allergy and the dosage route of a medication or immunisation.</td>
<td>A single more generic value set will be created to replace the existing UKCoreAllergyExposureRoute and UKCoreMedicationDosageRoute value sets, and existing bindings to these two value sets within Allergy, Medication and Immunization profiles will be replaced with bindings to the new value set.</td>
</tr>
<tr>
<td>11</td>

<td>The bindings for the medication[x] element within Medication profiles (which would be used by the medicationCodeableConcept element) need to change from the HL7 example value set to a UK Core Value Set, to mirror the binding for referenced Medication resources.</td>
<td>The bindings for the medication[x] element will be changed to the UKCoreMedicationCode value set within the affected profiles.</td>
</tr>
<tr>
<td>12</td>

<td>Although not specifically discussed during Sprint 3 calls, a request has been made to further update the UKCoreAllergyCode value set to also support the use of dm+d codes in addition to existing SNOMED and nullFlavor codes.</td>
<td>The value set composition will be expanded to allow the use of dm+d codes in addition to existing code systems.</td>
</tr>
<tr>
<td>13</td>

<td>Although not specifically discussed during Sprint 3 calls, it has become evident that some of the UK Core value set descriptions, particularly ones referring to SNOMED data, don't provide a natural language description of the value set.</td>
<td>All Sprints 1 to 3 value set descriptions are reviewed and modified according to a slightly revised set of conventions and to replace SNOMED ECL type descriptions with appropriate descriptive text.</td>
</tr>
<tr>
<td>14</td>

<td>Within the MedicationRequest profile, the value set binding for the courseOfTherapyType element needs to change to a value set which encompasses the 'acute' and 'continuous' concepts from the HL7 standard medicationrequest-course-of-therapy code system and also includes a 'continuous repeating dispensing' concept.</td>
<td>A new UK Core code system will be created which contains the 'continuous repeating dispensing' concept. A new UK Core value set will be created which includes the 'acute' and 'continuous' concepts from the HL7 standard code system and also includes the 'continuous repeating dispensing' concept from the new UK Core code system. The MedicationRequest.courseOfTherapyType element will be bound to this new value set with an 'extensible' binding strength.</br></br>These changes will allow the UKCore-PrescriptionType extension and the UKCorePrescriptionType value set used by that extension to be removed from the UK Core, as courseOfTherapy now covers the business requirement that originally led to their creation in STU3.</td>
</tr>
<tr>
<td>15</td>

<td>The MedicationRepeatInformation extension no longer needs to include a numberOfRepeatPrescriptionsAllowed element as the MedicationRequest profile in FHIR R4 now includes a dispenseRequest.numberOfRepeatsAllowed element.</td>
<td>The numberOfRepeatPrescriptionsAllowed element will be removed from the MedicationRepeatInformation extension.</td>
</tr>
<tr>
<td>16</td>

<td>Within the MedicationRequest profile, it is unclear how the doNotPerform element should be used.</td>
<td>Unless the Sprint 3 review turns up a strong use case for its use, guidance will be added into the MedicationRequest profile not to use the MedicationRequest.doNotPerform element.</td>
</tr>
<tr>
<td>17</td>

<td>Within the MedicationRequest profile, the value set binding for the category element needs to change to a UK Core value set which encompasses all the values within the HL7 standard medicationrequest-category code system and also includes a 'leave' concept.</td>
<td>A new UK Core code system will be created which contains the 'leave' concept. A new UK Core value set will be created which includes all concepts from the HL7 standard code system and also includes the 'leave' concept from the new UK Core code system. The MedicationRequest.category element will be bound to this new value set with an 'extensible' binding strength.</td>
</tr>
<tr>
<td>18</td>

<td>It is not currently possible to specify a Trade Family or Brand for a medication.</td>
<td>A Medication Trade Family extension will be added into the UK Core associated with the Medication profile. A Medication Trade Family value set will also be added to the UK Core and a binding to this value set created within the extension.</td>
</tr>
<tr>
<td>19</td>

<td>Within the MedicationRequest profile, according to the FHIR specification the default position for the substitution element is that if nothing is specified, then substitution may be done. This is the opposite position to how substitution is regarded within the UK.</td>
<td>The cardinality of the MedicationRequest.substitution element will be changed from 0..1 to 1..1. A default value for substitution.allowedBoolean will be specified as 'false' to reflect the UK default position of no substitution. Where a substitution is required to be specified, either the substitution.allowedBoolean would need to be set to 'true' or the substitution.allowedCodeableConcept will be used instead of substitution.allowedBoolean to specify the type of substitution required.</td>
</tr>
<tr>
<td>20</td>

<td>There are a number of use cases for recording within a Medication Statement that the Medication has been verified by a pharmacist. Currently there is no element to record this.</td>
<td>A new extension will be created for the MedicationStatement profile to indicate whether the medication has been verified by a pharmacist, using a Boolean value.</td>
</tr>
<tr>
<td>21</td>

<td>Within the Immunization profile, a constraint needs to be specified to indicate that if an immunisation has not been given then a reason for this must be provided.</td>
<td>A constraint will be added into the Immunization profile, i.e. if the immunization was not given then Immunization.status value MUST = 'not-done', and the Immunization.statusReason MUST be populated.</td>
</tr>
</table>