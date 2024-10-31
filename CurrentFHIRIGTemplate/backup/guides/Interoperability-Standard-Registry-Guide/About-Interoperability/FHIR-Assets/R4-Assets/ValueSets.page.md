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

    
## ValueSets

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-BodyStructure">England-BodyStructure</a>
  0.0.2
  2024-06-18
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/ValueSet-England-ChildProtectionPlan">England-ChildProtectionPlan</a>
  1.0.0
  2023-11-09
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-FlagCategoryPatient">England-FlagCategoryPatient</a>
  0.1.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-FlagCategoryProgramme">England-FlagCategoryProgramme</a>
  0.3.7
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-FlagCodeProgramme">England-FlagCodeProgramme</a>
  0.3.7
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-FlagCodeRA">England-FlagCodeRA</a>
  0.1.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-FlagConditionCategory">England-FlagConditionCategory</a>
  0.3.7
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-FlagConditionCode">England-FlagConditionCode</a>
  0.3.7
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-FlagProvenanceRole">England-FlagProvenanceRole</a>
  0.3.8
  2024-06-25
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/ValueSet-England-FlagRemovalReason">England-FlagRemovalReason</a>
  1.0.0
  2023-11-09
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-JobRoleCode">England-JobRoleCode</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-MCEDSignalResult">England-MCEDSignalResult</a>
  0.0.1
  2024-02-27
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/ValueSet-England-OrganisationRole">England-OrganisationRole</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-PDSRelationshipType">England-PDSRelationshipType</a>
  0.0.1
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/ValueSet-England-PeriodType">England-PeriodType</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/ValueSet-England-TaskCode">England-TaskCode</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/ValueSet-England-TypedDateTime">England-TypedDateTime</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ACVPU">UKCore-ACVPU</a>
  2.1.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-AddressKeyType">UKCore-AddressKeyType</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-AdmissionMethod">UKCore-AdmissionMethod</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-AlcoholConsumption">UKCore-AlcoholConsumption</a>
  0.0.1
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-AllergyCode">UKCore-AllergyCode</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-AllergyExposureRoute">UKCore-AllergyExposureRoute</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-AllergyManifestation">UKCore-AllergyManifestation</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-AllergySubstance">UKCore-AllergySubstance</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-AppointmentReasonCode">UKCore-AppointmentReasonCode</a>
  1.0.0
  2022-05-20
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BMI">UKCore-BMI</a>
  1.0.1
  2024-02-27
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BiopsyState">UKCore-BiopsyState</a>
  2.1.0
  2023-10-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BirthSex">UKCore-BirthSex</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodGlucose">UKCore-BloodGlucose</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure">UKCore-BloodPressure</a>
  1.0.1
  2024-02-27
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure-Average">UKCore-BloodPressure-Average</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure-AverageDiastolic">UKCore-BloodPressure-AverageDiastolic</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure-AverageSystolic">UKCore-BloodPressure-AverageSystolic</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure-CuffSize">UKCore-BloodPressure-CuffSize</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure-DeviceType">UKCore-BloodPressure-DeviceType</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure-Diastolic">UKCore-BloodPressure-Diastolic</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure-MeasurementMethod">UKCore-BloodPressure-MeasurementMethod</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BloodPressure-Systolic">UKCore-BloodPressure-Systolic</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BodyHeightMeasurements">UKCore-BodyHeightMeasurements</a>
  1.0.1
  2024-02-27
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BodyPosition">UKCore-BodyPosition</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BodySite">UKCore-BodySite</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BodyTemperature">UKCore-BodyTemperature</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-BodyWeightMeasurements">UKCore-BodyWeightMeasurements</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-CareSettingType">UKCore-CareSettingType</a>
  3.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-CompositionCategory">UKCore-CompositionCategory</a>
  1.0.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-CompositionSectionCode">UKCore-CompositionSectionCode</a>
  2.2.0
  2023-08-03
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ConditionCategory">UKCore-ConditionCategory</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ConditionCode">UKCore-ConditionCode</a>
  2.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ConditionEpisode">UKCore-ConditionEpisode</a>
  2.1.0
  2022-12-16
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ConditionEpisodicity">UKCore-ConditionEpisodicity</a>
  2.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ConditionRelationship">UKCore-ConditionRelationship</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ConsentException">UKCore-ConsentException</a>
  0.0.1
  2024-07-11
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-DateTimeType">UKCore-DateTimeType</a>
  2.1.0
  2023-10-13
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-DeathNotificationStatus">UKCore-DeathNotificationStatus</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-DeliveryChannel">UKCore-DeliveryChannel</a>
  1.1.0
  2022-05-20
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-DeviceType">UKCore-DeviceType</a>
  1.1.0
  2022-01-22
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-DischargeDestination">UKCore-DischargeDestination</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-DischargeMethod">UKCore-DischargeMethod</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-DocumentType">UKCore-DocumentType</a>
  2.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-EarlyWarningSubScore">UKCore-EarlyWarningSubScore</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-EarlyWarningTotalScore">UKCore-EarlyWarningTotalScore</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-EmergencyCareDischargeStatus">UKCore-EmergencyCareDischargeStatus</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-EncounterLocationType">UKCore-EncounterLocationType</a>
  1.0.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-EncounterType">UKCore-EncounterType</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-EthnicCategory">UKCore-EthnicCategory</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-FindingCode">UKCore-FindingCode</a>
  2.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-FundingCategory">UKCore-FundingCategory</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-GenomeSequencingCategory">UKCore-GenomeSequencingCategory</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-HeadCircumferenceMeasurements">UKCore-HeadCircumferenceMeasurements</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-HeartRate">UKCore-HeartRate</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-HumanLanguage">UKCore-HumanLanguage</a>
  2.2.0
  2023-12-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ImmunizationAdministrationBodySite">UKCore-ImmunizationAdministrationBodySite</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ImmunizationExplanationReason">UKCore-ImmunizationExplanationReason</a>
  2.3.0
  2023-02-14
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-InspiredOxygen">UKCore-InspiredOxygen</a>
  2.1.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-LanguageAbilityMode">UKCore-LanguageAbilityMode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-LanguageAbilityProficiency">UKCore-LanguageAbilityProficiency</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-LegalStatusClassification">UKCore-LegalStatusClassification</a>
  1.0.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-LegalStatusContext">UKCore-LegalStatusContext</a>
  1.0.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ListCode">UKCore-ListCode</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ListEmptyReasonCode">UKCore-ListEmptyReasonCode</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ListWarningCode">UKCore-ListWarningCode</a>
  2.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationAdministrationCategory">UKCore-MedicationAdministrationCategory</a>
  1.0.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationChangeStatus">UKCore-MedicationChangeStatus</a>
  1.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationCode">UKCore-MedicationCode</a>
  2.3.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationDosageMethod">UKCore-MedicationDosageMethod</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationDosageRoute">UKCore-MedicationDosageRoute</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationForm">UKCore-MedicationForm</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationPrecondition">UKCore-MedicationPrecondition</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationPrescribingAgency">UKCore-MedicationPrescribingAgency</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationPrescribingOrganization">UKCore-MedicationPrescribingOrganization</a>
  1.1.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationPrescribingOrganizationType">UKCore-MedicationPrescribingOrganizationType</a>
  1.0.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationRequestCategory">UKCore-MedicationRequestCategory</a>
  1.1.2
  2024-07-23
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationRequestCourseOfTherapy">UKCore-MedicationRequestCourseOfTherapy</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationStatementCategory">UKCore-MedicationStatementCategory</a>
  1.1.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationSupplyType">UKCore-MedicationSupplyType</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MedicationTradeFamily">UKCore-MedicationTradeFamily</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MessageEvent">UKCore-MessageEvent</a>
  2.2.0
  2024-02-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-MessageHeaderInstruction">UKCore-MessageHeaderInstruction</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-NHSNumberUnavailableReason">UKCore-NHSNumberUnavailableReason</a>
  1.1.0
  2024-06-14
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-NHSNumberVerificationStatus">UKCore-NHSNumberVerificationStatus</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ObservationMethod">UKCore-ObservationMethod</a>
  2.0.0
  2023-11-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ObservationType">UKCore-ObservationType</a>
  2.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ObservationVitalSignsType">UKCore-ObservationVitalSignsType</a>
  1.1.0
  2024-02-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ObservationVitalSignsValue">UKCore-ObservationVitalSignsValue</a>
  1.0.0
  2023-11-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-OperationOutcomeIssueDetails">UKCore-OperationOutcomeIssueDetails</a>
  1.1.0
  2024-02-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-OrganizationType">UKCore-OrganizationType</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-OtherContactSystem">UKCore-OtherContactSystem</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-OutcomeOfAttendance">UKCore-OutcomeOfAttendance</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-OverseasVisitorChargingCategory">UKCore-OverseasVisitorChargingCategory</a>
  1.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-OxygenSaturation">UKCore-OxygenSaturation</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PathologyAndLaboratoryMedicineObservables">UKCore-PathologyAndLaboratoryMedicineObservables</a>
  1.0.0
  2023-11-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PathologyAndLaboratoryMedicineProcedures">UKCore-PathologyAndLaboratoryMedicineProcedures</a>
  1.0.0
  2023-11-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PeriodType">UKCore-PeriodType</a>
  1.0.0
  2023-10-13
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PersonMaritalStatusCode">UKCore-PersonMaritalStatusCode</a>
  2.3.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PersonRelationshipType">UKCore-PersonRelationshipType</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PersonStatedGenderCode">UKCore-PersonStatedGenderCode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PracticeSettingCode">UKCore-PracticeSettingCode</a>
  1.0.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PractitionerRoleCode">UKCore-PractitionerRoleCode</a>
  1.0.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PreferredContactMethod">UKCore-PreferredContactMethod</a>
  2.2.0
  2023-10-09
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PreferredWrittenCommunicationFormat">UKCore-PreferredWrittenCommunicationFormat</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-PrescriptionType">UKCore-PrescriptionType</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ProblemSignificance">UKCore-ProblemSignificance</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ProcedureCode">UKCore-ProcedureCode</a>
  2.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-QuestionnaireQuestionCodes">UKCore-QuestionnaireQuestionCodes</a>
  1.0.0
  2024-02-12
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ReasonImmunizationNotAdministered">UKCore-ReasonImmunizationNotAdministered</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-RecordingSetting">UKCore-RecordingSetting</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ReligiousAffiliation">UKCore-ReligiousAffiliation</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ReportCode">UKCore-ReportCode</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ReportCodeSnCT">UKCore-ReportCodeSnCT</a>
  2.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ResidentialStatus">UKCore-ResidentialStatus</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-RespirationRate">UKCore-RespirationRate</a>
  1.1.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-SDSJobRoleName">UKCore-SDSJobRoleName</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-SampleCategory">UKCore-SampleCategory</a>
  2.1.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-SampleState">UKCore-SampleState</a>
  1.0.0
  2024-10-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ServiceRequestMethod">UKCore-ServiceRequestMethod</a>
  1.0.0
  2022-05-20
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-ServiceRequestReasonCode">UKCore-ServiceRequestReasonCode</a>
  1.1.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-SourceOfAdmission">UKCore-SourceOfAdmission</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-SourceOfServiceRequest">UKCore-SourceOfServiceRequest</a>
  1.2.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-SpecimenBodySite">UKCore-SpecimenBodySite</a>
  2.1.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-SpecimenType">UKCore-SpecimenType</a>
  2.2.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-SubstanceOrProductAdministrationRoute">UKCore-SubstanceOrProductAdministrationRoute</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-TobaccoConsumption">UKCore-TobaccoConsumption</a>
  0.0.1
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-TreatmentCategory">UKCore-TreatmentCategory</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-UnifiedTestList">UKCore-UnifiedTestList</a>
  1.0.0
  2023-11-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-VaccinationProcedure">UKCore-VaccinationProcedure</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-VaccinationProcedureSupplementary">UKCore-VaccinationProcedureSupplementary</a>
  2.1.1
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-VaccineCode">UKCore-VaccineCode</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-VitalSignsObservationType">UKCore-VitalSignsObservationType</a>
  2.0.1
  2022-12-16
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/ValueSet-UKCore-VitalSignsObservationValue">UKCore-VitalSignsObservationValue</a>
  2.0.0
  2022-12-16
  <span class="status retired">retired</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/ValueSet-nhsdigital-message-events">nhsdigital-message-events</a>
  1.0.12
  <span class="status draft">draft</span>
</li>

</ul></div><br><br>

---


