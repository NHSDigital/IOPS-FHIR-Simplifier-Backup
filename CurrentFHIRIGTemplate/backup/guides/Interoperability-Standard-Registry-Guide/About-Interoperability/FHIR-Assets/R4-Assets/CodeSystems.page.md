<label>
    <input type="checkbox" id="ukcore-checkbox" checked>
    Show UKCore Items
    </label>
    <br>
    <label>
    <input type="checkbox" id="nhsengland-checkbox" checked>
    Show NHSEngland Items
    </label>

    
<script>
    const ukcoreCheckbox = document.getElementById('ukcore-checkbox');
    const nhsenglandCheckbox = document.getElementById('nhsengland-checkbox');

    ukcoreCheckbox.addEventListener('change', function() {
        const ukcoreItems = document.querySelectorAll('.ukcore');
        ukcoreItems.forEach(item => {
        if (ukcoreCheckbox.checked) {
            item.classList.remove('hidden');
        } else {
            item.classList.add('hidden');
        }
        });
    });

    nhsenglandCheckbox.addEventListener('change', function() {
        const nhsenglandItems = document.querySelectorAll('.nhsengland');
        nhsenglandItems.forEach(item => {
        if (nhsenglandCheckbox.checked) {
            item.classList.remove('hidden');
        } else {
            item.classList.add('hidden');
        }
        });
    });
    </script>

    
## CodeSystems

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/CodeSystem-England-ConditionCategoryRA">England-ConditionCategoryRA</a>
  0.4.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/CodeSystem-England-ConditionCodeRA">England-ConditionCodeRA</a>
  0.4.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-FGMRemovalReason">England-FGMRemovalReason</a>
  1.0.0
  2023-11-09
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/CodeSystem-England-FlagCategoryPatient">England-FlagCategoryPatient</a>
  0.4.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/CodeSystem-England-FlagCategoryRA">England-FlagCategoryRA</a>
  0.4.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-HTTPErrorCodes">England-HTTPErrorCodes</a>
  1.0.0
  2024-06-13
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/CodeSystem-England-JobRoleCode">England-JobRoleCode</a>
  0.0.1
  2024-10-26
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-MessageEventsBARS">England-MessageEventsBARS</a>
  1.0.0
  2024-06-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-MessageReasonBARS">England-MessageReasonBARS</a>
  1.0.0
  2024-06-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-ODSDateTime">England-ODSDateTime</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-ODSOrganisationRole">England-ODSOrganisationRole</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-ODSRecordClass">England-ODSRecordClass</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-ODSRecordUseType">England-ODSRecordUseType</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-ODSRelationship">England-ODSRelationship</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-PFSPrescriptionOrderingParameter">England-PFSPrescriptionOrderingParameter</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-PeriodType">England-PeriodType</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/CodeSystem-England-SDSJobRoleName">England-SDSJobRoleName</a>
  0.0.1
  2024-09-17
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-NHSDataModelAndDictionary-AdmissionMethod">NHSDataModelAndDictionary-AdmissionMethod</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-NHSDataModelAndDictionary-DischargeDestination">NHSDataModelAndDictionary-DischargeDestination</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-NHSDataModelAndDictionary-DischargeMethod">NHSDataModelAndDictionary-DischargeMethod</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-NHSDataModelAndDictionary-OutcomeOfAttendance">NHSDataModelAndDictionary-OutcomeOfAttendance</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-NHSDataModelAndDictionary-PersonMaritalStatusCode">NHSDataModelAndDictionary-PersonMaritalStatusCode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-NHSDataModelAndDictionary-PersonStatedGenderCode">NHSDataModelAndDictionary-PersonStatedGenderCode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-NHSDataModelAndDictionary-SourceOfAdmission">NHSDataModelAndDictionary-SourceOfAdmission</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-AdditionalPersonRelationshipRole">UKCore-AdditionalPersonRelationshipRole</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-AddressKeyType">UKCore-AddressKeyType</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-AdmissionMethodEngland">UKCore-AdmissionMethodEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-AdmissionMethodWales">UKCore-AdmissionMethodWales</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-AppointmentReasonCode">UKCore-AppointmentReasonCode</a>
  1.0.0
  2022-05-20
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-BiopsyState">UKCore-BiopsyState</a>
  1.0.0
  2023-10-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ConditionCategory">UKCore-ConditionCategory</a>
  1.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ConditionEpisodicity">UKCore-ConditionEpisodicity</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ConditionRelationship">UKCore-ConditionRelationship</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ConsentUpdateMode">UKCore-ConsentUpdateMode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-DateTimeType">UKCore-DateTimeType</a>
  2.1.0
  2023-10-13
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-DeathNotificationStatus">UKCore-DeathNotificationStatus</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-DeliveryChannel">UKCore-DeliveryChannel</a>
  1.1.0
  2022-05-20
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-DischargeDestinationEngland">UKCore-DischargeDestinationEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-DischargeDestinationWales">UKCore-DischargeDestinationWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-DischargeMethodEngland">UKCore-DischargeMethodEngland</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-DischargeMethodWales">UKCore-DischargeMethodWales</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-EPSIssueCode">UKCore-EPSIssueCode</a>
  1.1.0
  2023-02-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-EmergencyCareOutcomeOfAttendanceWales">UKCore-EmergencyCareOutcomeOfAttendanceWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-EncounterLocationTypeEngland">UKCore-EncounterLocationTypeEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-EncounterLocationTypeWales">UKCore-EncounterLocationTypeWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-EthnicCategory">UKCore-EthnicCategory</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-EthnicCategoryEngland">UKCore-EthnicCategoryEngland</a>
  1.1.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-EthnicCategoryScotland">UKCore-EthnicCategoryScotland</a>
  1.1.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-EthnicCategoryWales">UKCore-EthnicCategoryWales</a>
  1.1.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-FundingCategory">UKCore-FundingCategory</a>
  2.0.0
  2024-06-14
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-GenomeSequencingCategory">UKCore-GenomeSequencingCategory</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-HumanLanguage">UKCore-HumanLanguage</a>
  2.1.0
  2023-12-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ITKResponseCode">UKCore-ITKResponseCode</a>
  1.0.0
  2023-02-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-LanguageAbilityMode">UKCore-LanguageAbilityMode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-LanguageAbilityProficiency">UKCore-LanguageAbilityProficiency</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-LegalStatusClassificationEngland">UKCore-LegalStatusClassificationEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-LegalStatusClassificationWales">UKCore-LegalStatusClassificationWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-LegalStatusContext">UKCore-LegalStatusContext</a>
  1.0.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ListEmptyReasonCode">UKCore-ListEmptyReasonCode</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ListWarningCode">UKCore-ListWarningCode</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationAdministrationCategory">UKCore-MedicationAdministrationCategory</a>
  1.0.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationChangeStatus">UKCore-MedicationChangeStatus</a>
  1.0.1
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationPrescribingAgency">UKCore-MedicationPrescribingAgency</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationPrescribingOrganization">UKCore-MedicationPrescribingOrganization</a>
  1.0.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationPrescribingOrganizationType">UKCore-MedicationPrescribingOrganizationType</a>
  1.0.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationRequestCategory">UKCore-MedicationRequestCategory</a>
  1.1.1
  2023-10-06
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationRequestCourseOfTherapy">UKCore-MedicationRequestCourseOfTherapy</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationStatementCategory">UKCore-MedicationStatementCategory</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MedicationSupplyType">UKCore-MedicationSupplyType</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MessageEvent">UKCore-MessageEvent</a>
  2.1.0
  2022-12-16
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-MessageHeaderInstruction">UKCore-MessageHeaderInstruction</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-NHSNumberUnavailableReason">UKCore-NHSNumberUnavailableReason</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-NHSNumberVerificationStatus">UKCore-NHSNumberVerificationStatus</a>
  2.1.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-NHSNumberVerificationStatusEngland">UKCore-NHSNumberVerificationStatusEngland</a>
  1.1.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-NHSNumberVerificationStatusWales">UKCore-NHSNumberVerificationStatusWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-OrganizationTypeGenomics">UKCore-OrganizationTypeGenomics</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-OtherContactSystem">UKCore-OtherContactSystem</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-OutcomeOfAttendanceEngland">UKCore-OutcomeOfAttendanceEngland</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-OutcomeOfAttendanceWales">UKCore-OutcomeOfAttendanceWales</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-OverseasVisitorChargingCategory">UKCore-OverseasVisitorChargingCategory</a>
  1.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PeriodType">UKCore-PeriodType</a>
  1.0.0
  2023-10-13
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PersonMaritalStatus">UKCore-PersonMaritalStatus</a>
  1.0.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PersonMaritalStatusEngland">UKCore-PersonMaritalStatusEngland</a>
  1.1.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PersonMaritalStatusScotland">UKCore-PersonMaritalStatusScotland</a>
  1.0.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PersonMaritalStatusWales">UKCore-PersonMaritalStatusWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PracticeSettingCode">UKCore-PracticeSettingCode</a>
  1.0.1
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PracticeSettingCodeEngland">UKCore-PracticeSettingCodeEngland</a>
  1.0.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PracticeSettingCodeScotland">UKCore-PracticeSettingCodeScotland</a>
  1.0.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PracticeSettingCodeWales">UKCore-PracticeSettingCodeWales</a>
  1.0.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PreferredContactMethod">UKCore-PreferredContactMethod</a>
  2.2.0
  2023-10-09
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PreferredWrittenCommunicationFormat">UKCore-PreferredWrittenCommunicationFormat</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PrescriptionType">UKCore-PrescriptionType</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-PrimarySampleState">UKCore-PrimarySampleState</a>
  1.0.0
  2024-10-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ProblemSignificance">UKCore-ProblemSignificance</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-RecordStandardHeadings">UKCore-RecordStandardHeadings</a>
  2.2.0
  2022-08-03
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-RecordingSetting">UKCore-RecordingSetting</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ResidentialStatus">UKCore-ResidentialStatus</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-SDSJobRoleName">UKCore-SDSJobRoleName</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-SampleCategory">UKCore-SampleCategory</a>
  2.0.0
  2024-08-05
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-ServiceRequestMethod">UKCore-ServiceRequestMethod</a>
  1.0.0
  2022-05-20
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-SourceOfAdmissionEngland">UKCore-SourceOfAdmissionEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-SourceOfAdmissionWales">UKCore-SourceOfAdmissionWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-SpineErrorOrWarningCode">UKCore-SpineErrorOrWarningCode</a>
  1.0.0
  2023-02-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-TreatmentCategory">UKCore-TreatmentCategory</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/CodeSystem-UKCore-WithheldIdentityReason">UKCore-WithheldIdentityReason</a>
  0.0.1
  2024-06-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-message-events">message-events</a>
  1.0.19
  2022-03-25
  <span class="status draft">draft</span>
</li>

</ul></div><br><br>

---


