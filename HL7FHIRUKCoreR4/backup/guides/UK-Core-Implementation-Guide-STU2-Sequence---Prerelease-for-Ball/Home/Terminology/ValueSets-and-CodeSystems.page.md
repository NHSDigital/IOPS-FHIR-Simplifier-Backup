---
topic: Library-ValueSetsAndCodeSystems-38719
---
## Terminology

---

## ValueSets and CodeSystems

This is the list of ValueSets and CodeSystems defined for use within the UK Core. 

Other ValueSets are usable if the binding strength is defined as extensible. For more information see
[HL7 FHIR - Binding Strengths](http://hl7.org/fhir/R4/terminologies.html#strength).

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Important note regarding ValueSet expansions:</h4>
Within this release of the UK Core, ValueSet expansions have been incorporated into the ValueSets. For some ValueSets containing SNOMED CT or dm+d data in particular, the number of concepts were deemed too large to expand. It should also be remembered that the expansions of SNOMED CT data in particular represent the content available at the time the expansion was generated, but that this content can subsequently change. For an up to date and complete list of values, suppliers SHOULD consult the latest SNOMED CT terminology release.
</div>

<style>
 [class*=override] {
 	background-color:#f2f2f2;
	 }
</style>

<div class="tab">
<button class="tablinks active" onclick="openTab(event, 'Narrative')">Narrative</button>
<button class="tablinks" onclick="openTab(event, 'Alphabetical_VS')">Alphabetical (ValueSets)</button>
<button class="tablinks" onclick="openTab(event, 'Alphabetical_CS')">Alphabetical (CodeSystems)</button>
<button class="tablinks" onclick="openTab(event, 'Sprint_VS')">By Sprint (ValueSets)</button>
<button class="tablinks" onclick="openTab(event, 'Sprint_CS')">By Sprint (CodeSystems)</button>
<button class="tablinks" onclick="openTab(event, 'Resource')">By Resource</button>
</div>

<div id="Narrative" class="tabcontent"  style="display:block">
<h3>Narrative Listing</h3>
<table id="valuesetlist">
<tr>
<th width="50%">ValueSet</th>
<th width="5%">Status</th>
<th width="40%">Bound in Profile/Extension</th>
<th width="5%">C&TA Sprint</th>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-AddressKeyType}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-AddressKey}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-AddressKeyType}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-AdmissionMethod}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-AdmissionMethod}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-AdmissionMethodEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-AdmissionMethodWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>              
<td><h4>{{pagelink:ValueSet-UKCore-AllergyCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-AllergyIntolerance-30748}}</td>
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
<td>{{pagelink:Profile-AllergyIntolerance-30748}}</td>
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
<td>{{pagelink:Profile-AllergyIntolerance-30748}}</td>
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
<td><h4>{{pagelink:ValueSet-UKCore-AppointmentReasonCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Appointment-87479}}</td>
<td>5</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v2-0276</code></td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystem-UKCore-AppointmentReasonCode}}</td>
</tr>
<tr>
<td colspan="5"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-BiopsyState}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Specimen-37178}}</td>
<td>6</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v2-0493</code></td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystem-UKCore-BiopsyState}}</td>
</tr>
<tr>
<td colspan="5"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-BirthSex}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-BirthSex}}</td>
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
<td>
{{pagelink:Profile-MedicationAdministration-56616}}<br/>
{{pagelink:Profile-MedicationDispense-76932}}<br/>
{{pagelink:Profile-MedicationRequest-20572}}<br/>
{{pagelink:Profile-MedicationStatement-34649}}
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
<td><h4>{{pagelink:ValueSet-UKCore-CareSettingType}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-CareSettingType}}<br>
{{pagelink:Profile-Encounter-79976}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-CompositionCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Composition-31483}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-CompositionSectionCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Composition-31483}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem {{pagelink:CodeSystem-UKCore-RecordStandardHeadings}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ConditionCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Condition-78787}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/condition-category
</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem {{pagelink:CodeSystem-UKCore-ConditionCategory}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ConditionCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Condition-78787}}<br>
{{pagelink:Profile-Procedure-10775}}
</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ConditionEpisodicity}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-ConditionEpisode}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem {{pagelink:CodeSystem-UKCore-ConditionEpisodicity}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-DeathNotificationStatus}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-DeathNotificationStatus}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-DeathNotificationStatus}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-DeliveryChannel}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-DeliveryChannel}}</td>
<td>5</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-DeliveryChannel}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-DischargeDestination}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-DischargeDestinationEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-DischargeDestinationWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>


<tr>
<td><h4>{{pagelink:ValueSet-UKCore-DischargeMethod}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-DischargeMethod}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-DischargeMethodEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-DischargeMethodWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-DocumentType}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Composition-31483}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>


<tr>
<td><h4>{{pagelink:ValueSet-UKCore-EmergencyCareDischargeStatus}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-EmergencyCareDischargeStatus}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-EmergencyCareOutcomeOfAttendanceWales}}</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-EncounterLocationType}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-EncounterLocationTypeEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-EncounterLocationTypeWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-EncounterType}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>4</td>
</tr>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-EthnicCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-EthnicCategory}}</td>
<td>1</td>
</tr>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-EthnicCategoryEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-EthnicCategoryWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-FundingCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-Coverage}}</td>
<td>6</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem {{pagelink:CodeSystem-UKCore-FundingCategory}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-GenomeSequencingCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Specimen-37178}}</td>
<td>6</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-GenomeSequencingCategory}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ImmunizationAdministrationBodySite}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-16790}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ImmunizationExplanationReason}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-16790}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-LegalStatusClassification}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-LegalStatus}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-LegalStatusClassificationEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-LegalStatusClassificationWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-LegalStatusContext}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-LegalStatus}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-LegalStatusContext}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ListCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-List-19037}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ListEmptyReasonCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-List-19037}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-ListEmptyReasonCode}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/list-empty-reason</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ListWarningCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-ListWarningCode}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-ListWarningCode}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>


<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationAdministrationCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationAdministration-56616}}</td>
<td><div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i> (See footnote)</div></td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-MedicationAdministrationCategory}}</td>
</tr>
<tr>
<td colspan="4">Composed of <code>http://terminology.hl7.org/CodeSystem/medication-admin-category</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Medication-73860}}<br/>
{{pagelink:Profile-MedicationAdministration-56616}}<br/>
{{pagelink:Profile-MedicationDispense-76932}}<br/>
{{pagelink:Profile-MedicationRequest-20572}}<br/>
{{pagelink:Profile-MedicationStatement-34649}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk</code><br>
Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationDosageMethod}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationAdministration-56616}}<br/>
{{pagelink:Profile-MedicationDispense-76932}}<br/>
{{pagelink:Profile-MedicationRequest-20572}}<br/>
{{pagelink:Profile-MedicationStatement-34649}}</td>
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
<td>{{pagelink:Profile-Medication-73860}}</td>
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
<td colspan="4">Composed of CodeSystem {{pagelink:CodeSystem-UKCore-MedicationPrescribingOrganization}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationRequestCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationRequest-20572}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-MedicationRequestCategory}}</td>
</tr>
<tr>
<td colspan="4">Composed of <code>http://terminology.hl7.org/CodeSystem/medicationrequest-category</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationRequestCourseOfTherapy}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationRequest-20572}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-MedicationRequestCourseOfTherapy}}</td>
</tr>
<tr>
<td colspan="4">Composed of <code>http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-MedicationStatementCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-MedicationStatement-34649}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-MedicationStatementCategory}}</td>
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
<td>{{pagelink:Profile-MedicationDispense-76932}}</td>
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
<td>{{pagelink:Extension-UKCore-MedicationTradeFamily}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-NHSNumberUnavailableReason}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>6</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-NHSNumberUnavailableReason}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-NHSNumberVerificationStatus}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-NHSNumberVerificationStatus}}</td>
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
<td><h4>{{pagelink:ValueSet-UKCore-ObservationType}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Observation-67521}}</td>
<td>6</td>
</tr>
<tr >
<td colspan="4">Composed of <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-OrganizationType}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Organization-94604}}</td>
<td>6</td>
</tr>
<tr >
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/organization-type</code></td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-OrganizationTypeGenomics}}</td>
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
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-OtherContactSystem}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-OutcomeOfAttendance}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-OutcomeOfAttendanceEngland}}</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-OutcomeOfAttendanceWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineObservables}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Observation-Lab-67452}}</td>
<td><div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i><i class="fa fa-asterisk"></i> (See footnote)</div></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineProcedures}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Observation-Group-67431}}<br>
{{pagelink:Profile-ServiceRequest-Lab-37178}}</td>
<td><div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i><i class="fa fa-asterisk"></i> (See footnote)</div></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PersonMaritalStatusCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>1</td>
</tr>
<tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-MaritalStatus</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
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
<td>{{pagelink:Profile-FamilyMemberHistory-69978}}<br>
{{pagelink:Profile-Patient-88961}}<br>
{{pagelink:Profile-RelatedPerson-51006}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v2-0131</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-RoleCode</code></td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-AdditionalPersonRelationshipRole}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Appointment-87479}}<br>
{{pagelink:Profile-HealthcareService-13702}}<br>
{{pagelink:Profile-PractitionerRole-55046}}<br>
{{pagelink:Profile-Schedule-96669}}<br>
{{pagelink:Profile-Slot-83549}}
</td>
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
<td>{{pagelink:Extension-UKCore-ContactPreference}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-PreferredContactMethod}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-PreferredWrittenCommunicationFormat}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-ContactPreference}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-PreferredWrittenCommunicationFormat}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:Valueset-UKCore-ProcedureCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Procedure-10775}}<br>
{{pagelink:Profile-ServiceRequest-88746}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="4">Composed of <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ReasonImmunizationNotAdministered}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Immunization-16790}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>


<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ReportCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-DiagnosticReport-54417}}</td>
<td>6</td>
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
<td>{{pagelink:Extension-UKCore-ResidentialStatus}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-ResidentialStatus}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-SampleCategory}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-SampleCategory}}</td>
<td>6</td>
</tr>
<tr>
<td colspan="4">Composed of {{pagelink:CodeSystem-UKCore-SampleCategory}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-ServiceRequestReasonCode}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-PriorityReason}}<br>
{{pagelink:Profile-ServiceRequest-88746}}</td>
<td>5</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-SourceOfAdmission}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystem-UKCore-SourceOfAdmissionEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystem-UKCore-SourceOfAdmissionWales}}</td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>


<tr>
<td><h4>{{pagelink:ValueSet-UKCore-SourceOfServiceRequest}}</h4></td>
<td>active</td>
<td>{{pagelink:Extension-UKCore-SourceOfServiceRequest}}</td>
<td>5</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-SpecimenBodySite}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Specimen-37178}}</td>
<td>6</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-SpecimenType}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-Specimen-37178}}</td>
<td>6</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="4"  class="override"></td>
</tr>

<tr>
<td><h4>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</h4></td>
<td>active</td>
<td>{{pagelink:Profile-AllergyIntolerance-30748}}<br/>
{{pagelink:Profile-Immunization-16790}}<br/>
{{pagelink:Profile-MedicationAdministration-56616}}<br/>
{{pagelink:Profile-MedicationDispense-76932}}<br/>
{{pagelink:Profile-MedicationRequest-20572}}<br/>
{{pagelink:Profile-MedicationStatement-34649}}
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
<td>{{pagelink:Extension-UKCore-VaccinationProcedure}}</td>
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
<td>See guidance for {{pagelink:Extension-UKCore-VaccinationProcedure}} for usage</td>
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
<td>{{pagelink:Profile-Immunization-16790}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="4">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
</table>

</div>

<div id="Alphabetical_VS" class="tabcontent">
<h3>Alphabetical Listing (ValueSets)</h3>

<table>
<tbody>
<tr class="a-to-z"><td>
<p><b>A-D:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-AddressKeyType}}</li>
<li>{{pagelink:ValueSet-UKCore-AdmissionMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-AllergyCode}}</li>
<li>{{pagelink:ValueSet-UKCore-AllergyManifestation}}</li>
<li>{{pagelink:ValueSet-UKCore-AllergySubstance}}</li>
<li>{{pagelink:ValueSet-UKCore-AppointmentReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-BiopsyState}}</li>
<li>{{pagelink:ValueSet-UKCore-BirthSex}}</li>
<li>{{pagelink:ValueSet-UKCore-BodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-CareSettingType}}</li>
<li>{{pagelink:ValueSet-UKCore-CompositionCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-CompositionSectionCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ConditionCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-ConditionCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ConditionEpisodicity}}</li>
<li>{{pagelink:ValueSet-UKCore-DeathNotificationStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-DeliveryChannel}}</li>
<li>{{pagelink:ValueSet-UKCore-DischargeDestination}}</li>
<li>{{pagelink:ValueSet-UKCore-DischargeMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-DocumentType}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>E-L:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-EmergencyCareDischargeStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-EncounterLocationType}}</li>
<li>{{pagelink:ValueSet-UKCore-EncounterType}}</li>
<li>{{pagelink:ValueSet-UKCore-EthnicCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-FundingCategory}}<</li>
<li>{{pagelink:ValueSet-UKCore-GenomeSequencingCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-ImmunizationAdministrationBodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-ImmunizationExplanationReason}}</li>
<li>{{pagelink:ValueSet-UKCore-LegalStatusClassification}}</li>
<li>{{pagelink:ValueSet-UKCore-LegalStatusContext}}</li>
<li>{{pagelink:ValueSet-UKCore-ListCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ListEmptyReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ListWarningCode}}</li>
</ul>
</td></tr>
<tr class="a-to-z"><td>
<p><b>M-P:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-MedicationAdministrationCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationCode}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationDosageMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationForm}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationPrescribingOrganizationType}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationRequestCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationRequestCourseOfTherapy}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationStatementCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationSupplyType}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationTradeFamily}}</li>
<li>{{pagelink:ValueSet-UKCore-NHSNumberUnavailableReason}}</li>
<li>{{pagelink:ValueSet-UKCore-NHSNumberVerificationStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-ObservationType}}</li>
<li>{{pagelink:ValueSet-UKCore-OrganizationType}}</li>
<li>{{pagelink:ValueSet-UKCore-OtherContactSystem}}</li>
<li>{{pagelink:ValueSet-UKCore-OutcomeOfAttendance}}</li>
<li>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineObservables}}</li>
<li>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineProcedures}}</li>
<li>{{pagelink:ValueSet-UKCore-PersonMaritalStatusCode}}<</li>
<li>{{pagelink:ValueSet-UKCore-PersonRelationshipType}}</li>
<li>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</li>
<li>{{pagelink:ValueSet-UKCore-PreferredContactMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-PreferredWrittenCommunicationFormat}}</li>
<li>{{pagelink:Valueset-UKCore-ProcedureCode}}</li>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>Q-Z:</b></p> 
<ul>  
<li>{{pagelink:ValueSet-UKCore-ReasonImmunizationNotAdministered}}</li>
<li>{{pagelink:ValueSet-UKCore-ReportCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ResidentialStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-SampleCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-ServiceRequestReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-SourceOfAdmission}}</li>
<li>{{pagelink:ValueSet-UKCore-SourceOfServiceRequest}}</li>
<li>{{pagelink:ValueSet-UKCore-SpecimenBodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-SpecimenType}}</li>
<li>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccinationProcedure}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccinationProcedureSupplementary}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccineCode}}</li>
</ul>
</td></tr>

</tbody></table>
</div>

<div id="Alphabetical_CS" class="tabcontent">
<h3>Alphabetical Listing (CodeSystems)</h3>

<table>
<tbody>
<tr class="a-to-z"><td>
<p><b>A-D:</b></p>
<ul>
<li>{{pagelink:CodeSystem-UKCore-AdditionalPersonRelationshipRole}}</li>
<li>{{pagelink:CodeSystem-UKCore-AddressKeyType}}</li>
<li>{{pagelink:CodeSystem-UKCore-AdmissionMethodEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-AdmissionMethodWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-AppointmentReasonCode}}</li>
<li>{{pagelink:CodeSystem-UKCore-BiopsyState}}</li>
<li>{{pagelink:CodeSystem-UKCore-ConditionCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-ConditionEpisodicity}}</li>
<li>{{pagelink:CodeSystem-UKCore-DeathNotificationStatus}}</li>
<li>{{pagelink:CodeSystem-UKCore-DeliveryChannel}}</li>
<li>{{pagelink:CodeSystem-UKCore-DischargeDestinationEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-DischargeDestinationWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-DischargeMethodEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-DischargeMethodWales}}</li>
<li> </li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>E-L:</b></p>
<ul>
<li>{{pagelink:CodeSystem-UKCore-EmergencyCareOutcomeOfAttendanceWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-EncounterLocationTypeEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-EncounterLocationTypeWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-EthnicCategoryEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-EthnicCategoryWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-FundingCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-GenomeSequencingCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-LegalStatusClassificationEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-LegalStatusClassificationWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-LegalStatusContext}}</li>
<li>{{pagelink:CodeSystem-UKCore-ListEmptyReasonCode}}</li>
<li>{{pagelink:CodeSystem-UKCore-ListWarningCode}}</li>
</ul>
</td></tr>
<tr class="a-to-z"><td>
<p><b>M-P:</b></p>
<ul>
<li>{{pagelink:CodeSystem-UKCore-MedicationAdministrationCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationPrescribingOrganization}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationRequestCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationRequestCourseOfTherapy}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationStatementCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationSupplyType}}</li>
<li>{{pagelink:CodeSystem-UKCore-NHSNumberUnavailableReason}}</li>
<li>{{pagelink:CodeSystem-UKCore-NHSNumberVerificationStatusEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-NHSNumberVerificationStatusWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-OrganizationTypeGenomics}}</li>
<li>{{pagelink:CodeSystem-UKCore-OtherContactSystem}}</li>
<li>{{pagelink:CodeSystem-UKCore-OutcomeOfAttendanceEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-OutcomeOfAttendanceWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-PersonMaritalStatusEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-PersonMaritalStatusWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-PracticeSettingCode}}</li>
<li>{{pagelink:CodeSystem-UKCore-PreferredContactMethod}}</li>
<li>{{pagelink:CodeSystem-UKCore-PreferredWrittenCommunicationFormat}}</li>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>Q-Z:</b></p> 
<ul>  
<li>{{pagelink:CodeSystem-UKCore-RecordStandardHeadings}}</li>
<li>{{pagelink:CodeSystem-UKCore-ResidentialStatus}}</li>
<li>{{pagelink:CodeSystem-UKCore-SampleCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-SourceOfAdmissionEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-SourceOfAdmissionWales}}</li>
</ul>
</td></tr>

</tbody></table>
</div>

<div id="Sprint_VS" class="tabcontent">
<h3>By Sprint (ValueSets)</h3>

<p><b>C&TA Sprint 1:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-AddressKeyType}}</li>
<li>{{pagelink:ValueSet-UKCore-BirthSex}}</li>
<li>{{pagelink:ValueSet-UKCore-DeathNotificationStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-EthnicCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-NHSNumberVerificationStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-OtherContactSystem}}</li>
<li>{{pagelink:ValueSet-UKCore-PersonMaritalStatusCode}}</li>
<li>{{pagelink:ValueSet-UKCore-PersonRelationshipType}}</li>
<li>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</li>
<li>{{pagelink:ValueSet-UKCore-PreferredContactMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-PreferredWrittenCommunicationFormat}}</li>
<li>{{pagelink:ValueSet-UKCore-ResidentialStatus}}</li>
</ul>

<p><b>C&TA Sprint 2:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-AllergyCode}}</li>
<li>{{pagelink:ValueSet-UKCore-AllergyManifestation}}</li>
<li>{{pagelink:ValueSet-UKCore-AllergySubstance}}</li>
</ul>

<p><b>C&TA Sprint 3:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-BodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-ImmunizationAdministrationBodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-ImmunizationExplanationReason}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationCode}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationDosageMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationForm}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationPrescribingOrganizationType}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationRequestCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationRequestCourseOfTherapy}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationStatementCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationSupplyType}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationTradeFamily}}</li>
<li>{{pagelink:ValueSet-UKCore-ReasonImmunizationNotAdministered}}</li>
<li>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccinationProcedure}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccinationProcedureSupplementary}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccineCode}}</li>
</ul>

<p><b>C&TA Sprint 4:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-AdmissionMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-CareSettingType}}</li>
<li>{{pagelink:ValueSet-UKCore-CompositionCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-CompositionSectionCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ConditionCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-ConditionCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ConditionEpisodicity}}</li>
<li>{{pagelink:ValueSet-UKCore-DischargeDestination}}</li>
<li>{{pagelink:ValueSet-UKCore-DischargeMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-DocumentType}}</li>
<li>{{pagelink:ValueSet-UKCore-EmergencyCareDischargeStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-EncounterLocationType}}</li>
<li>{{pagelink:ValueSet-UKCore-EncounterType}}</li>
<li>{{pagelink:ValueSet-UKCore-LegalStatusClassification}}</li>
<li>{{pagelink:ValueSet-UKCore-LegalStatusContext}}</li>
<li>{{pagelink:ValueSet-UKCore-ListCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ListEmptyReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ListWarningCode}}</li>
<li>{{pagelink:ValueSet-UKCore-OutcomeOfAttendance}}</li>
<li>{{pagelink:Valueset-UKCore-ProcedureCode}}</li>
<li>{{pagelink:ValueSet-UKCore-SourceOfAdmission}}</li>
</ul>

<p><b>C&TA Sprint 5:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-AppointmentReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-DeliveryChannel}}</li>
<li>{{pagelink:ValueSet-UKCore-ServiceRequestReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-SourceOfServiceRequest}}</li>
</ul>

<p><b>C&TA Sprint 6:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-BiopsyState}}</li>
<li>{{pagelink:ValueSet-UKCore-FundingCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-GenomeSequencingCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-NHSNumberUnavailableReason}}</li>
<li>{{pagelink:ValueSet-UKCore-ObservationType}}</li>
<li>{{pagelink:ValueSet-UKCore-OrganizationType}}</li>
<li>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineObservables}}</li>
<li>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineProcedures}}</li>
<li>{{pagelink:ValueSet-UKCore-ReportCode}}</li>
<li>{{pagelink:ValueSet-UKCore-SampleCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-SpecimenBodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-SpecimenType}}</li>
</ul>

</div>


<div id="Sprint_CS" class="tabcontent">
<h3>By Sprint (CodeSystems)</h3>

<p><b>C&TA Sprint 1:</b></p>
<ul>
<li>{{pagelink:CodeSystem-UKCore-AdditionalPersonRelationshipRole}}</li>
<li>{{pagelink:CodeSystem-UKCore-AddressKeyType}}</li>
<li>{{pagelink:CodeSystem-UKCore-DeathNotificationStatus}}</li>
<li>{{pagelink:CodeSystem-UKCore-EthnicCategoryEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-EthnicCategoryWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-NHSNumberVerificationStatusEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-NHSNumberVerificationStatusWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-OtherContactSystem}}</li>
<li>{{pagelink:CodeSystem-UKCore-PersonMaritalStatusEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-PersonMaritalStatusWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-PracticeSettingCode}}</li>
<li>{{pagelink:CodeSystem-UKCore-PreferredContactMethod}}</li>
<li>{{pagelink:CodeSystem-UKCore-PreferredWrittenCommunicationFormat}}</li>
<li>{{pagelink:CodeSystem-UKCore-ResidentialStatus}}</li>
</ul>

<p><b>C&TA Sprint 3:</b></p>
<ul>
<li>{{pagelink:CodeSystem-UKCore-MedicationPrescribingOrganization}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationRequestCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationRequestCourseOfTherapy}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationStatementCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-MedicationSupplyType}}</li>
</ul>

<p><b>C&TA Sprint 4:</b></p>
<ul>

<li>{{pagelink:CodeSystem-UKCore-AdmissionMethodEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-AdmissionMethodWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-ConditionCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-ConditionEpisodicity}}</li>
<li>{{pagelink:CodeSystem-UKCore-DischargeDestinationEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-DischargeDestinationWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-DischargeMethodEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-DischargeMethodWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-EmergencyCareOutcomeOfAttendanceWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-EncounterLocationTypeEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-EncounterLocationTypeWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-LegalStatusClassificationEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-LegalStatusClassificationWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-LegalStatusContext}}</li>
<li>{{pagelink:CodeSystem-UKCore-ListEmptyReasonCode}}</li>
<li>{{pagelink:CodeSystem-UKCore-ListWarningCode}}</li>
<li>{{pagelink:CodeSystem-UKCore-OutcomeOfAttendanceEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-OutcomeOfAttendanceWales}}</li>
<li>{{pagelink:CodeSystem-UKCore-RecordStandardHeadings}}</li>
<li>{{pagelink:CodeSystem-UKCore-SourceOfAdmissionEngland}}</li>
<li>{{pagelink:CodeSystem-UKCore-SourceOfAdmissionWales}}</li>
</ul>

<p><b>C&TA Sprint 5:</b></p>
<ul>
<li>{{pagelink:CodeSystem-UKCore-AppointmentReasonCode}}</li>
<li>{{pagelink:CodeSystem-UKCore-DeliveryChannel}}</li>
</ul>

<p><b>C&TA Sprint 6:</b></p>
<ul>
<li>{{pagelink:CodeSystem-UKCore-BiopsyState}}</li>
<li>{{pagelink:CodeSystem-UKCore-FundingCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-GenomeSequencingCategory}}</li>
<li>{{pagelink:CodeSystem-UKCore-NHSNumberUnavailableReason}}</li>
<li>{{pagelink:CodeSystem-UKCore-OrganizationTypeGenomics}}</li>
<li>{{pagelink:CodeSystem-UKCore-SampleCategory}}</li>
</ul>
</div>

<div id="Resource" class="tabcontent">
<h3>By Resource (US Core style)</h3>

<p><b>AllergyIntolerance:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-AllergyCode}}</li>
<li>{{pagelink:ValueSet-UKCore-AllergyManifestation}}</li>
<li>{{pagelink:ValueSet-UKCore-AllergySubstance}}</li>
<li>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</li>
</ul>
<p><b>Appointment:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-AppointmentReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</li>
<li>{{pagelink:ValueSet-UKCore-DeliveryChannel}}</li>
</ul>
<p><b>Composition:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-CareSettingType}}</li>
<li>{{pagelink:ValueSet-UKCore-CompositionCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-CompositionSectionCode}}</li>
<li>{{pagelink:ValueSet-UKCore-DocumentType}}</li>
</ul>
<p><b>Condition:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-ConditionCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-ConditionCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ConditionEpisodicity}}</li>
</ul>
<p><b>DiagnosticReport:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-ReportCode}}</li>
</ul>
<p><b>Encounter:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-AdmissionMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-CareSettingType}}</li>
<li>{{pagelink:ValueSet-UKCore-DischargeDestination}}</li>
<li>{{pagelink:ValueSet-UKCore-DischargeMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-EmergencyCareDischargeStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-EncounterLocationType}}</li>
<li>{{pagelink:ValueSet-UKCore-EncounterType}}</li>
<li>{{pagelink:ValueSet-UKCore-LegalStatusClassification}}</li>
<li>{{pagelink:ValueSet-UKCore-LegalStatusContext}}</li>
<li>{{pagelink:ValueSet-UKCore-OutcomeOfAttendance}}</li>
<li>{{pagelink:ValueSet-UKCore-SourceOfAdmission}}</li>
</ul>
<p><b>HealthcareService:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</li>
</ul>
<p><b>Immunization:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-ImmunizationAdministrationBodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-ImmunizationExplanationReason}}</li>
<li>{{pagelink:ValueSet-UKCore-ReasonImmunizationNotAdministered}}</li>
<li>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccinationProcedure}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccinationProcedureSupplementary}}</li>
<li>{{pagelink:ValueSet-UKCore-VaccineCode}}</li>
</ul>
<p><b>List:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-CareSettingType}}</li>
<li>{{pagelink:ValueSet-UKCore-ListCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ListEmptyReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ListWarningCode}}</li>
</ul>
<p><b>Medication:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-MedicationCode}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationForm}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationTradeFamily}}</li>
</ul>
<p><b>MedicationAdministration:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-BodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationAdministrationCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationCode}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationDosageMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</li>
</ul>
<p><b>MedicationDispense:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-BodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationCode}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationDosageMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationSupplyType}}</li>
<li>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</li>
</ul>
<p><b>MedicationRequest:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-BodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationCode}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationDosageMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationRequestCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationRequestCourseOfTherapy}}</li>
<li>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</li>
</ul>
<p><b>MedicationStatement:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-BodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationCode}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationDosageMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationPrescribingOrganizationType}}</li>
<li>{{pagelink:ValueSet-UKCore-MedicationStatementCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-SubstanceOrProductAdministrationRoute}}</li>
</ul>
<p><b>Observation:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-ObservationType}}</li>
<li>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineObservables}}</li>
<li>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineProcedures}}</li>
</ul>
<p><b>Organization:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-OrganizationType}}</li>
</ul>
<p><b>Patient:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-BirthSex}}</li>
<li>{{pagelink:ValueSet-UKCore-DeathNotificationStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-EthnicCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-NHSNumberUnavailableReason}}</li>
<li>{{pagelink:ValueSet-UKCore-NHSNumberVerificationStatus}}</li>
<li>{{pagelink:ValueSet-UKCore-PersonMaritalStatusCode}}</li>
<li>{{pagelink:ValueSet-UKCore-PersonRelationshipType}}</li>
<li>{{pagelink:ValueSet-UKCore-PreferredContactMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-PreferredWrittenCommunicationFormat}}</li>
<li>{{pagelink:ValueSet-UKCore-ResidentialStatus}}</li>
</ul>
<p><b>PractitionerRole:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</li>
</ul>
<p><b>Procedure:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-ConditionCode}}</li>
<li>{{pagelink:Valueset-UKCore-ProcedureCode}}</li>
</ul>
<p><b>RelatedPerson:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-PersonRelationshipType}}</li>
<li>{{pagelink:ValueSet-UKCore-PreferredContactMethod}}</li>
<li>{{pagelink:ValueSet-UKCore-PreferredWrittenCommunicationFormat}}</li>
</ul>
<p><b>ServiceRequest:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-FundingCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-PathologyAndLaboratoryMedicineProcedures}}</li>
<li>{{pagelink:Valueset-UKCore-ProcedureCode}}</li>
<li>{{pagelink:ValueSet-UKCore-ServiceRequestReasonCode}}</li>
<li>{{pagelink:ValueSet-UKCore-SourceOfServiceRequest}}</li>
</ul>
<p><b>Schedule:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</li>
</ul>
<p><b>Slot:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-DeliveryChannel}}</li>
<li>{{pagelink:ValueSet-UKCore-PracticeSettingCode}}</li>
</ul>
<p><b>Specimen:</b></p>
<ul>
<li>{{pagelink:ValueSet-UKCore-BiopsyState}}</li>
<li>{{pagelink:ValueSet-UKCore-GenomeSequencingCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-SampleCategory}}</li>
<li>{{pagelink:ValueSet-UKCore-SpecimenBodySite}}</li>
<li>{{pagelink:ValueSet-UKCore-SpecimenType}}</li>
</ul>
</div>
<br>
<div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i> <code>UKCore-MedicationAdministrationCategory</code> was added after specific review and feedback from the Digital and Interoperable Medicines Programme. It was not added under a Clinical & Technical Assurance sprint
</div>
<br>
<div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i> <i class="fa fa-asterisk"></i> <code>UKCore-UnifiedTestList</code> added in C&TA Sprint 6 was replaced by the <code>UKCore-PathologyAndLaboratoryMedicineObservables</code> and <code>UKCore-PathologyAndLaboratoryMedicineProcedures</code> ValueSets during the STU2 Ballot reconciliation due to a change by the SNOMED CT UK Clinical Edition.
</div>

---
