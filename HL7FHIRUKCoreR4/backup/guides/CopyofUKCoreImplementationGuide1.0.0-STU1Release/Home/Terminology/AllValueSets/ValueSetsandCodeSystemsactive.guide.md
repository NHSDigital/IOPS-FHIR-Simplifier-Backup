## ValueSets and Code Systems (active)

This is the list of ValueSets and CodeSystems defined for use within the UK Core. 

Other ValueSets are useable if the binding strength is defined as extensible. For more information see
<a href="http://hl7.org/fhir/terminologies.html#strength" target="_blank">HL7 FHIR - Binding Strengths</a>.

The UK Core ValueSets have been assigned a maturity level similar to the maturity levels described in the FHIR standard. This is intended to indicate how stable the ValueSet is deemed to be, this is in addition to the publication status of the ValueSet <a href="http://hl7.org/fhir/valueset-publication-status.html" target="_blank">HL7 FHIR statuses</a> of draft, active, retired and unknown.
<br/>
<br/>
<table id="assets">
<tr>
<th width="10%">Maturity level</th>
<th width="90%">Definition</th>
</tr>
<tr>
<td>0</td>
<td>The ValueSet has been published on the current build. This ValueSet has had no formal review and therefore may have quality issues. It is published only to allow the review process to start</td>
</tr>
<tr>
<td>1</td>
<td>The ValueSet produces no warnings during the build process and has had a formal internal review by the UK Core development team</td>
</tr>
<tr>
<td>2</td>
<td>The ValueSet has been released for review to the UK FHIR community, any feedback received has been addressed as far as possible</td>
</tr>
<tr>
<td>3</td>
<td>The ValueSet has been presented for inclusion in the Technical and Clinical Assurance process</td>
</tr>
<tr>
<td>4</td> 
<td>The ValueSet has completed the Technical and Clinical Assurance process and the status has been changed to active</td>
</tr>
<tr>
<td>5</td>
<td>The ValueSet has been presented for inclusion in the HL7 UK Ballot Process</td>
</tr>
<tr> 
<td>6</td> 
<td>The ValueSet has completed the HL7 UK Ballot process and is now deemed to be Normative</td>
</tr>
</table>
<br/>
<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note:</b></br>The ValueSets and CodeSystems listed below have been defined for use in the UK Core. These ValueSets and CodeSystems have either been assured or currently in the process of being assured.<br/>

For the current list of ValueSets or CodeSysytems under development refer to the <a href="https://simplifier.net/guide/ukcoreimplementationguideassetsindevelopment?version=current" target="blank">HL7 FHIR® UK Core Profile Implementation Guide R4 (Draft) ValueSets and Code Systems.</a>
<p>Where more than one CodeSystem is listed the associated ValueSet should be expanded to give the full list of codes</p> 
</div>
<br/>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note regarding dm+d within certain UK Core ValueSets:</b></br>For ValueSets which include the use of the dm+d CodeSystem, within this release of the UK Core it has not been possible to document in the content logical definitions the constraints to specific dm+d concept classes that are referred to within the respective ValueSet descriptions. Once work is completed within NHS Digital to put dm+d into a terminology server – anticipated to be before the end of 2021 - the mechanism with which to formally describe the applicable dm+d concept class constraints in these ValueSets can be incorporated into a later release of the UK Core.
<br/>
<br/>
In the interim, the content logical definitions for these ValueSets simply include a reference to a URL for the whole of dm+d, whilst the descriptions textually provide the constraints on the applicable dm+d concept classes that are relevant to the ValueSet.
<br/>
<br/>
The ValueSets affected by this issue are:
<li>UKCoreAllergyCode</li>
<li>UKCoreAllergySubstance</li>
<li>UKCoreMedicationCode</li>
<li>UKCoreVaccineCode</li>
<br/>
If you need further information about this please contact the Interoperable Medicines Standards programme via the Contact Us page.
<br/>
<br/>
</div>
<br/>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note regarding ValueSet expansions:</b></br>Within this release of the UK Core, ValueSet expansions have been incorporated into the ValueSets. For some very large ValueSets containing SNOMED data in particular, whilst the expansion may state the true number of concepts that were in the ValueSet at the time the expansion was created, the accompanying table will be limited to no more than 600 of the applicable concepts. It should also be remembered that the expansions of SNOMED data in particular represent the content available at the time the expansion was generated, but that this content can subsequently change. For an up to date and complete list of values, suppliers should consult the latest SNOMED terminology release.
<br/>
</div>
<br/>
<table id="assets">
<!--Important note the shading in table is controlled in the CSS update CSS if adding or removing rows-->
<tr>
<th width="45%">ValueSet</th>
<th width="5%">Status</th>
<th width="5%">Maturity</th>
<th width="40%">Bound in Profile/Extension</th>
<th width="5%">C&TA Sprint</th>
</tr>

<tr>
<td>{{pagelink:ValueSetUKCoreAddressKeyType-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-AddressKey-Index-110}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-AddressKeyType-Index-110}}</td>
</tr>
<tr>              
<td>{{pagelink:ValueSetUKCoreAllergyCode-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreAllergyManifestation-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreAllergySubstance-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>

<tr>
<td>{{pagelink:ValueSetUKCoreBirthSex-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-BirthSex-Index-110}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>	http://terminology.hl7.org/CodeSystem/v3-AdministrativeGender</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreBodySite-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreDeathNotificationStatus-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-DeathNotificationStatus-Index-110}}</td>
<td>1<br/</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-DeathNotificationStatus-Index-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreEthnicCategory-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-EthnicCategory-Index-110}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EthnicCategoryEngland-110}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EthnicCategoryScotland-110}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EthnicCategoryWales-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreHumanLanguage-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCoreHumanLanguage-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreImmunizationAdministrationBodySite-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreImmunizationExplanationReason-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationCode-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}<br/>
{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationDosageMethod-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationForm-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationPrecondition-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationPrescribingOrganization-110}}</td>
<td>active</td>
<td>4</td>
<td>
{{pagelink:ExtensionUKCore-MedicationPrescribingOrganization}}<br/>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem {{pagelink:CodeSystemUKCore-MedicationPrescribingOrganization-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationRequestCategory-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MedicationRequestCategory-110}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/medicationrequest-category</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationStatementCategory-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MedicationStatementCategory-110}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/medication-statement-category</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationRequestCourseOfTherapy-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MedicationRequestCouseOfTherapy-110}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationSupplyType-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MedicationSupplyType-Index-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreMedicationTradeFamily-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-MedicationTradeFamily-110}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreNHSNumberVerificationStatus-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-NHSNumberVerificationStatus-Index-110}}</td>
<td>1<br</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-NHSNumberVerificationStatus-Index-110}}</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreOtherContactSystem-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>ContactPoint.system</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-OtherContactSystem-Index-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCorePersonMaritalStatusCode-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-PersonMaritalStatus-110}}</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-MaritalStatus</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCorePersonRelationshipType}}</td>
<td>active</td>
<td>4</td>
</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem 	<code>http://terminology.hl7.org/CodeSystem/v2-0131</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-RoleCode</code></td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-AdditionalPersonRelationshipRole-Index-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCorePractitionerRoleCode-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/practitioner-role</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCorePreferredContactMethod-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-PreferredContactMethod-Index-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCorePreferredWrittenCommunicationFormat-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-PreferredWrittenCommunicationFormat-Index-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreReasonImmunizationNotAdministered-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreResidentialStatus-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-ResidentialStatus-Index-110}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-ResidentialStatus-Index-110}}</td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreSubstanceOrProductAdministrationRoute-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}<br/>
{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}<br/>
{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>

<tr>
<td>{{pagelink:ValueSetUKCoreVaccinationProcedure-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-VaccinationProcedure-Index-110}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreVaccinationProcedureSupplementary-110}}</td>
<td>active</td>
<td>4</td>
<td>See guidance for {{pagelink:ExtensionUKCore-VaccinationProcedure-Index-110}} for usage</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td>{{pagelink:ValueSetUKCoreVaccineCode-Index-110}}</td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>

<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
</table>


---




























