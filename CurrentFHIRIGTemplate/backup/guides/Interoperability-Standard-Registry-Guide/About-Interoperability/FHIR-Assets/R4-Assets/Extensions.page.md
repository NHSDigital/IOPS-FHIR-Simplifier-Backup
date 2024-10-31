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

    
## Extensions

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/Extension-England-FlagNotes">Extension-England-FlagNotes</a>
  0.1.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Extension-ExtCodeableReference">England-Extension-ExtCodeableReference</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/Extension-England-LocationExtension">Extension-England-LocationExtension</a>
  1.0.0
  2024-06-19
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/Extension-England-TypedPeriod">Extension-England-TypedPeriod</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/Extension-England-TypedDateTime">Extension-England-TypedDateTime</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/Extension-England-OrganisationRole">Extension-England-OrganisationRole</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/Extension-England-FlagRemovalReason">Extension-England-FlagRemovalReason</a>
  1.0.0
  2023-11-09
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-BookingOrganization">Extension-UKCore-BookingOrganization</a>
  1.3.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-OtherContactSystem">Extension-UKCore-OtherContactSystem</a>
  3.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ProblemSignificance">Extension-UKCore-ProblemSignificance</a>
  1.1.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ActualProblem">Extension-UKCore-ActualProblem</a>
  1.3.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ResidentialStatus">Extension-UKCore-ResidentialStatus</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-PharmacistVerifiedIndicator">Extension-UKCore-PharmacistVerifiedIndicator</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-CareSettingType">Extension-UKCore-CareSettingType</a>
  2.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-Evidence">Extension-UKCore-Evidence</a>
  2.2.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-BodySiteReference">Extension-UKCore-BodySiteReference</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-DiagnosticReportSupportingInfo">Extension-UKCore-DiagnosticReportSupportingInfo</a>
  1.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-BirthSex">Extension-UKCore-BirthSex</a>
  2.1.0
  2024-06-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-CuffSize">Extension-UKCore-CuffSize</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-AllergyIntoleranceEnd">Extension-UKCore-AllergyIntoleranceEnd</a>
  2.3.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-AdditionalContact">Extension-UKCore-AdditionalContact</a>
  1.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-LegalStatus">Extension-UKCore-LegalStatus</a>
  1.2.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ListWarningCode">Extension-UKCore-ListWarningCode</a>
  3.1.0
  2024-06-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ParentPresent">Extension-UKCore-ParentPresent</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-SourceOfServiceRequest">Extension-UKCore-SourceOfServiceRequest</a>
  1.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-Recorder">Extension-UKCore-Recorder</a>
  1.1.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationChangeSummary">Extension-UKCore-MedicationChangeSummary</a>
  2.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ConditionBodyStructure">Extension-UKCore-ConditionBodyStructure</a>
  0.0.1
  2024-06-07
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-EthnicCategory">Extension-UKCore-EthnicCategory</a>
  2.3.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-DiagnosticReportNote">Extension-UKCore-DiagnosticReportNote</a>
  1.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationPrescribingOrganization">Extension-UKCore-MedicationPrescribingOrganization</a>
  1.0.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-DiagnosticReportComposition">Extension-UKCore-DiagnosticReportComposition</a>
  1.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ContactRank">Extension-UKCore-ContactRank</a>
  2.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-PreferredDispenserOrganization">Extension-UKCore-PreferredDispenserOrganization</a>
  2.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-EmergencyCareDischargeStatus">Extension-UKCore-EmergencyCareDischargeStatus</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-AddressKey">Extension-UKCore-AddressKey</a>
  3.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationDosageLastChanged">Extension-UKCore-MedicationDosageLastChanged</a>
  2.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-TreatmentCategory">Extension-UKCore-TreatmentCategory</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationPrescribingOrganizationType">Extension-UKCore-MedicationPrescribingOrganizationType</a>
  1.1.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-OutcomeOfAttendance">Extension-UKCore-OutcomeOfAttendance</a>
  2.2.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-CodingSCTDescDisplay">Extension-UKCore-CodingSCTDescDisplay</a>
  1.2.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicalApplianceSupplier">Extension-UKCore-MedicalApplianceSupplier</a>
  2.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-DischargeMethod">Extension-UKCore-DischargeMethod</a>
  2.2.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-Coverage">Extension-UKCore-Coverage</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-DeviceReference">Extension-UKCore-DeviceReference</a>
  1.1.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-TypedPeriod">Extension-UKCore-TypedPeriod</a>
  1.0.0
  2023-10-13
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-NominatedPharmacy">Extension-UKCore-NominatedPharmacy</a>
  2.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ConditionEpisode">Extension-UKCore-ConditionEpisode</a>
  3.1.0
  2024-06-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-DiagnosticReportMediaLink">Extension-UKCore-DiagnosticReportMediaLink</a>
  0.0.1
  2024-06-07
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-SampleCategory">Extension-UKCore-SampleCategory</a>
  1.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationQuantityText">Extension-UKCore-MedicationQuantityText</a>
  2.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-VaccinationProcedure">Extension-UKCore-VaccinationProcedure</a>
  2.2.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-SpecimenCollectionCollector">Extension-UKCore-SpecimenCollectionCollector</a>
  1.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-AdmissionMethod">Extension-UKCore-AdmissionMethod</a>
  2.3.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ContactPreference">Extension-UKCore-ContactPreference</a>
  2.3.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ObservationBodyStructure">Extension-UKCore-ObservationBodyStructure</a>
  1.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ServiceRequestMethod">Extension-UKCore-ServiceRequestMethod</a>
  1.0.0
  2022-05-20
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-AssociatedEncounter">Extension-UKCore-AssociatedEncounter</a>
  1.1.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-NHSNumberVerificationStatus">Extension-UKCore-NHSNumberVerificationStatus</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ClinicalSetting">Extension-UKCore-ClinicalSetting</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ReligiousAffiliation">Extension-UKCore-ReligiousAffiliation</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-CopyCorrespondenceIndicator">Extension-UKCore-CopyCorrespondenceIndicator</a>
  2.2.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-TypedDateTime">Extension-UKCore-TypedDateTime</a>
  2.2.0
  2023-10-13
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-PriorityReason">Extension-UKCore-PriorityReason</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-SpecimenContainerDevice">Extension-UKCore-SpecimenContainerDevice</a>
  0.0.1
  2023-12-05
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationPrescribingAgency">Extension-UKCore-MedicationPrescribingAgency</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-PatientFetalStatus">Extension-UKCore-PatientFetalStatus</a>
  0.0.1
  2024-07-23
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-EffectivePeriod">Extension-UKCore-EffectivePeriod</a>
  2.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-NHSNumberUnavailableReason">Extension-UKCore-NHSNumberUnavailableReason</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-RelatedProblemHeader">Extension-UKCore-RelatedProblemHeader</a>
  1.3.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-OverseasVisitorChargingCategory">Extension-UKCore-OverseasVisitorChargingCategory</a>
  1.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-RecordingSetting">Extension-UKCore-RecordingSetting</a>
  1.1.0
  2024-06-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-ObservationTriggeredBy">Extension-UKCore-ObservationTriggeredBy</a>
  1.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MessageHeaderInstruction">Extension-UKCore-MessageHeaderInstruction</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-EncounterTransport">Extension-UKCore-EncounterTransport</a>
  2.1.0
  2022-12-16
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-NHSCommunication">Extension-UKCore-NHSCommunication</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-DeathNotificationStatus">Extension-UKCore-DeathNotificationStatus</a>
  2.2.0
  2023-12-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-RelatedClinicalContent">Extension-UKCore-RelatedClinicalContent</a>
  1.3.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationStatementLastIssueDate">Extension-UKCore-MedicationStatementLastIssueDate</a>
  2.1.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MainLocation">Extension-UKCore-MainLocation</a>
  2.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-PrescriptionType">Extension-UKCore-PrescriptionType</a>
  2.1.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-CodingSCTDescId">Extension-UKCore-CodingSCTDescId</a>
  2.2.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-AnaestheticIssues">Extension-UKCore-AnaestheticIssues</a>
  2.3.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-FamilyMemberHistoryParticipant">Extension-UKCore-FamilyMemberHistoryParticipant</a>
  1.1.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-DeliveryChannel">Extension-UKCore-DeliveryChannel</a>
  2.1.0
  2024-06-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationTradeFamily">Extension-UKCore-MedicationTradeFamily</a>
  1.1.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-SpecimenContainerLocation">Extension-UKCore-SpecimenContainerLocation</a>
  0.0.1
  2023-12-05
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/Extension-UKCore-MedicationRepeatInformation">Extension-UKCore-MedicationRepeatInformation</a>
  2.3.0
  2023-12-07
  <span class="status active">active</span>
</li>

</ul></div><br><br>

---


