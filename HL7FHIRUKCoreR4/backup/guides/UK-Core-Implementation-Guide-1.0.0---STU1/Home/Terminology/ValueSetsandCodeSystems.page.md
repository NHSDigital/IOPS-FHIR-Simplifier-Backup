---
topic: Library-ValueSetsAndCodeSystems-7b04b3ad-26b2-4281-b1a3-8edbbe398915
---
## ValueSets and Code Systems

This is the list of ValueSets and CodeSystems defined for use within the UK Core. 

Other ValueSets are usable if the binding strength is defined as extensible. For more information see
<a href="http://hl7.org/fhir/R4/terminologies.html#strength" target="_blank">HL7 FHIR - Binding Strengths</a>.

<br/>
<br/>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note regarding ValueSet expansions:</b></br>Within this release of the UK Core, ValueSet expansions have been incorporated into the ValueSets. For some ValueSets containing SNOMED CT or dm+d data in particular, the number of concepts were deemed too large to expand. It should also be remembered that the expansions of SNOMED CT data in particular represent the content available at the time the expansion was generated, but that this content can subsequently change. For an up to date and complete list of values, suppliers SHOULD consult the latest SNOMED CT terminology release.
<br/>
</div>

<style>
 [class*=override] {
 	background-color:#f2f2f2;
	 }
 
</style>

<table id="valuesetlist">
<tr>
<th width="45%">ValueSet</th>
<th width="5%">Status</th>
<th width="40%">Bound in Profile/Extension</th>
<th width="5%">C&TA Sprint</th>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-AddressKeyType}}</h4></td>
<td>active</td>
<td>{{pagelink:ExtensionUKCore-AddressKey}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-AddressKeyType}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>              
<td><h4>{{pagelink:ValueSet-UKCore-AllergyCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-AllergyManifestation}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-AllergySubstance}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-BirthSex}}</h4></td>
<td>active</td>
<td>{{pagelink:ExtensionUKCore-BirthSex}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-AdministrativeGender</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-BodySite}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-DeathNotificationStatus}}</h4></td>
<td>active</td>
<td>{{pagelink:ExtensionUKCore-DeathNotificationStatus}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-DeathNotificationStatus}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-EthnicCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:ExtensionUKCore-EthnicCategory}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-EthnicCategoryEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-EthnicCategoryWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-HumanLanguage}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-HumanLanguage}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ImmunizationAdministrationBodySite}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ImmunizationExplanationReason}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}<br/>
{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationDosageMethod}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationForm}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationPrecondition}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationPrescribingOrganizationType}}</h4></td>
<td>active</td>
<td>
{{pagelink:Extension-UKCore-MedicationPrescribingOrganizationType}}
</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem {{pagelink:CodeSystemUKCore-MedicationPrescribingOrganization}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationRequestCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-MedicationRequestCategory}}</td>
</tr>
<tr>
<td colspan="4">Composed of <code>http://terminology.hl7.org/CodeSystem/medicationrequest-category</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationRequestCourseOfTherapy}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-MedicationRequestCourseOfTherapy}}</td>
</tr>
<tr>
<td colspan="4">Composed of <code>http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy</code></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationStatementCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-MedicationStatementCategory}}</td>
</tr>
<tr>
<td colspan="4">Composed of <code>http://terminology.hl7.org/CodeSystem/medication-statement-category</code></td>
</tr>

<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationSupplyType}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-MedicationSupplyType}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationTradeFamily}}</h4></td>
<td>active</td>
<td>{{pagelink:ExtensionUKCore-MedicationTradeFamily}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-NHSNumberVerificationStatus}}</h4></td>
<td>active</td>
<td>{{pagelink:ExtensionUKCore-NHSNumberVerificationStatus}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-NHSNumberVerificationStatusEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-NHSNumberVerificationStatusWales}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-OtherContactSystem}}</h4></td>
<td>active</td>
<td>ContactPoint.system</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-OtherContactSystem}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PersonMaritalStatusCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-PersonMaritalStatusEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-PersonMaritalStatusWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PersonRelationshipType}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem 	<code>http://terminology.hl7.org/CodeSystem/v2-0131</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-RoleCode</code></td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-AdditionalPersonRelationshipRole}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-PracticeSettingCode}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PreferredContactMethod}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-PreferredContactMethod}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PreferredWrittenCommunicationFormat}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-PreferredWrittenCommunicationFormat}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ReasonImmunizationNotAdministered}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ResidentialStatus}}</h4></td>
<td>active</td>
<td>{{pagelink:ExtensionUKCore-ResidentialStatus}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystemUKCore-ResidentialStatus}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}<br/>
{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}<br/>
{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}
</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-VaccinationProcedure}}</h4></td>
<td>active</td>
<td>{{pagelink:ExtensionUKCore-VaccinationProcedure}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-VaccinationProcedureSupplementary}}</h4></td>
<td>active</td>
<td>See guidance for {{pagelink:ExtensionUKCore-VaccinationProcedure}} for usage</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSet-UKCore-VaccineCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
</table>


---
