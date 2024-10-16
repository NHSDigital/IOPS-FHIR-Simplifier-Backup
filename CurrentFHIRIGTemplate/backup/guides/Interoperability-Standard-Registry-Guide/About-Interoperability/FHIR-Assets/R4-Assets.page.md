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


## Profiles

<div class="status-container">
<ul>

### AllergyIntolerance

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-AllergyIntolerance">UKCore-AllergyIntolerance</a>
  2.5.0
  2024-07-11
  <span class="status active">active</span>
</li>

### Appointment

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Appointment">UKCore-Appointment</a>
  1.3.0
  2023-12-12
  <span class="status active">active</span>
</li>

### AuditEvent

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-AuditEvent">UKCore-AuditEvent</a>
  1.2.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### BodyStructure

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-BodyStructure">UKCore-BodyStructure</a>
  0.0.1
  2024-08-12
  <span class="status draft">draft</span>
</li>

### Bundle

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Bundle">UKCore-Bundle</a>
  2.2.0
  2023-12-16
  <span class="status draft">draft</span>
</li>

### CarePlan

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-CarePlan">UKCore-CarePlan</a>
  2.2.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### CareTeam

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-CareTeam">UKCore-CareTeam</a>
  2.1.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### Communication

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Communication">UKCore-Communication</a>
  2.1.0
  2023-12-12
  <span class="status draft">draft</span>
</li>

### Composition

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Composition">UKCore-Composition</a>
  2.4.0
  2023-12-12
  <span class="status active">active</span>
</li>

### Condition

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Condition">UKCore-Condition</a>
  2.6.0
  2024-06-07
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Condition-Flag">England-Condition-Flag</a>
  0.2.0
  2024-06-18
  <span class="status draft">draft</span>
</li>

### Consent

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Consent">UKCore-Consent</a>
  2.4.0
  2023-12-16
  <span class="status draft">draft</span>
</li>

### Device

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Device">UKCore-Device</a>
  1.2.0
  2023-12-12
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Device-BloodPressure">UKCore-Device-BloodPressure</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

### DiagnosticReport

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-DiagnosticReport">UKCore-DiagnosticReport</a>
  2.5.0
  2024-06-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-DiagnosticReport-Lab">UKCore-DiagnosticReport-Lab</a>
  2.0.1
  2024-07-23
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-DiagnosticReport-MCED">England-DiagnosticReport-MCED</a>
  0.0.1
  2024-03-19
  <span class="status draft">draft</span>
</li>

### DocumentReference

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-DocumentReference">UKCore-DocumentReference</a>
  2.2.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### Encounter

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Encounter">UKCore-Encounter</a>
  2.5.0
  2023-12-12
  <span class="status active">active</span>
</li>

### EpisodeOfCare

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-EpisodeOfCare">UKCore-EpisodeOfCare</a>
  2.2.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### FamilyMemberHistory

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-FamilyMemberHistory">UKCore-FamilyMemberHistory</a>
  1.2.0
  2024-07-11
  <span class="status active">active</span>
</li>

### Flag

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Flag">UKCore-Flag</a>
  1.2.0
  2023-12-12
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Flag-PatientFlag">England-Flag-PatientFlag</a>
  0.3.0
  2024-09-27
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Flag-PatientFlag-Adjustment">England-Flag-PatientFlag-Adjustment</a>
  0.2.0
  2024-09-27
  <span class="status draft">draft</span>
</li>

### HealthcareService

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-HealthcareService">UKCore-HealthcareService</a>
  1.3.0
  2024-07-11
  <span class="status active">active</span>
</li>

### ImagingStudy

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-ImagingStudy">UKCore-ImagingStudy</a>
  1.1.0
  2023-12-12
  <span class="status draft">draft</span>
</li>

### Immunization

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Immunization">UKCore-Immunization</a>
  2.4.0
  2023-12-12
  <span class="status active">active</span>
</li>

### List

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-List">UKCore-List</a>
  2.4.0
  2023-12-12
  <span class="status active">active</span>
</li>

### Location

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Location">UKCore-Location</a>
  2.3.0
  2023-12-12
  <span class="status active">active</span>
</li>

### Medication

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Medication">UKCore-Medication</a>
  2.3.0
  2023-12-12
  <span class="status active">active</span>
</li>

### MedicationAdministration

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-MedicationAdministration">UKCore-MedicationAdministration</a>
  2.3.0
  2024-07-11
  <span class="status active">active</span>
</li>

### MedicationDispense

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-MedicationDispense">UKCore-MedicationDispense</a>
  2.4.0
  2024-07-11
  <span class="status active">active</span>
</li>

### MedicationRequest

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-MedicationRequest">UKCore-MedicationRequest</a>
  2.5.0
  2024-07-11
  <span class="status active">active</span>
</li>

### MedicationStatement

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-MedicationStatement">UKCore-MedicationStatement</a>
  2.5.0
  2024-07-11
  <span class="status active">active</span>
</li>

### MessageHeader

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-MessageHeader">UKCore-MessageHeader</a>
  2.4.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### Observation

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation">UKCore-Observation</a>
  2.5.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-ACVPU">UKCore-Observation-ACVPU</a>
  1.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-AlcoholConsumption">UKCore-Observation-AlcoholConsumption</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-AverageBloodPressure">UKCore-Observation-AverageBloodPressure</a>
  1.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-BloodGlucose">UKCore-Observation-BloodGlucose</a>
  1.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-EarlyWarningTotalScore">UKCore-Observation-EarlyWarningTotalScore</a>
  1.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-Group-Lab">UKCore-Observation-Group-Lab</a>
  2.0.1
  2024-07-23
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-InspiredOxygen">UKCore-Observation-InspiredOxygen</a>
  1.0.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-Lab">UKCore-Observation-Lab</a>
  2.0.1
  2024-07-23
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-TobaccoConsumption">UKCore-Observation-TobaccoConsumption</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns">UKCore-Observation-VitalSigns</a>
  1.1.1
  2024-07-23
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-BMI">UKCore-Observation-VitalSigns-BMI</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-BloodPressure">UKCore-Observation-VitalSigns-BloodPressure</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-BodyHeight">UKCore-Observation-VitalSigns-BodyHeight</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-BodyTemperature">UKCore-Observation-VitalSigns-BodyTemperature</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-BodyWeight">UKCore-Observation-VitalSigns-BodyWeight</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-HeadCircumference">UKCore-Observation-VitalSigns-HeadCircumference</a>
  1.0.0
  2023-09-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-HeartRate">UKCore-Observation-VitalSigns-HeartRate</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-OxygenSaturation">UKCore-Observation-VitalSigns-OxygenSaturation</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Observation-VitalSigns-RespirationRate">UKCore-Observation-VitalSigns-RespirationRate</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Observation-MCED">England-Observation-MCED</a>
  0.0.1
  2024-03-22
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Observation-MCED-Result">England-Observation-MCED-Result</a>
  0.0.1
  2024-03-19
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Observation-MCED-Screening">England-Observation-MCED-Screening</a>
  0.0.1
  2024-03-19
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Observation-MCED-Site">England-Observation-MCED-Site</a>
  0.0.2
  2024-03-21
  <span class="status draft">draft</span>
</li>

### OperationOutcome

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-OperationOutcome">UKCore-OperationOutcome</a>
  1.3.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### Organization

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Organization">UKCore-Organization</a>
  2.5.1
  2024-07-23
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Organization-MCED">England-Organization-MCED</a>
  0.0.1
  2024-03-19
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Organization-ODS">England-Organization-ODS</a>
  0.0.1
  2024-01-11
  <span class="status draft">draft</span>
</li>

### OrganizationAffiliation

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-OrganizationAffiliation">UKCore-OrganizationAffiliation</a>
  0.0.1
  2024-07-11
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-OrganizationAffiliation-ODS">England-OrganizationAffiliation-ODS</a>
  0.0.2
  2024-06-18
  <span class="status draft">draft</span>
</li>

### Patient

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Patient">UKCore-Patient</a>
  2.6.1
  2024-07-23
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Patient-MCED">England-Patient-MCED</a>
  0.0.1
  2024-02-27
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Patient-PDS">England-Patient-PDS</a>
  0.0.1
  2024-03-05
  <span class="status draft">draft</span>
</li>

### Practitioner

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Practitioner">UKCore-Practitioner</a>
  2.4.0
  2023-12-12
  <span class="status active">active</span>
</li>

### PractitionerRole

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-PractitionerRole">UKCore-PractitionerRole</a>
  2.4.0
  2024-07-11
  <span class="status active">active</span>
</li>

### Procedure

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Procedure">UKCore-Procedure</a>
  2.5.0
  2023-12-12
  <span class="status active">active</span>
</li>

### Provenance

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Provenance">UKCore-Provenance</a>
  1.2.0
  2023-12-12
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Provenance-Flag">England-Provenance-Flag</a>
  0.1.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

### Questionnaire

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Questionnaire">UKCore-Questionnaire</a>
  1.3.0
  2023-12-12
  <span class="status draft">draft</span>
</li>

### QuestionnaireResponse

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-QuestionnaireResponse">UKCore-QuestionnaireResponse</a>
  1.2.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### RelatedPerson

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-RelatedPerson">UKCore-RelatedPerson</a>
  2.5.0
  2024-07-11
  <span class="status active">active</span>
</li>

### RequestGroup

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-RequestGroup">UKCore-RequestGroup</a>
  1.0.0
  2024-07-11
  <span class="status draft">draft</span>
</li>

### Schedule

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Schedule">UKCore-Schedule</a>
  1.3.0
  2023-12-12
  <span class="status active">active</span>
</li>

### ServiceRequest

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-ServiceRequest">UKCore-ServiceRequest</a>
  2.5.1
  2024-07-23
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-ServiceRequest-Lab">UKCore-ServiceRequest-Lab</a>
  2.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-ServiceRequestLab-MCED">England-ServiceRequestLab-MCED</a>
  0.0.1
  2024-02-27
  <span class="status draft">draft</span>
</li>

### Slot

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Slot">UKCore-Slot</a>
  1.3.0
  2023-12-12
  <span class="status active">active</span>
</li>

### Specimen

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Specimen">UKCore-Specimen</a>
  2.4.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Specimen-MCED">England-Specimen-MCED</a>
  0.0.1
  2024-02-27
  <span class="status draft">draft</span>
</li>

### Task

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-Task">UKCore-Task</a>
  1.2.0
  2023-12-12
  <span class="status draft">draft</span>
</li>

</ul></div><br><br>

---


## Extensions

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/Extension-England-FlagNotes">Extension-England-FlagNotes</a>
  0.1.0
  2024-02-14
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

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/ValueSet-England-PeriodType">England-PeriodType</a>
  1.0.0
  2023-12-07
  <span class="status active">active</span>
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
  2023-04-28
  <span class="status active">active</span>
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


## CodeSystems

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/CodeSystem-England-ConditionCategoryRA">England-ConditionCategoryRA</a>
  0.4.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/CodeSystem-England-ConditionCodeRA">England-ConditionCodeRA</a>
  0.4.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-FGMRemovalReason">England-FGMRemovalReason</a>
  1.0.0
  2023-11-09
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/CodeSystem-England-FlagCategoryPatient">England-FlagCategoryPatient</a>
  0.4.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/CodeSystem-England-FlagCategoryRA">England-FlagCategoryRA</a>
  0.4.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/CodeSystem-England-HTTPErrorCodes">England-HTTPErrorCodes</a>
  1.0.0
  2024-06-13
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

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/CodeSystem-England-SDSJobRoleName">England-SDSJobRoleName</a>
  0.0.1
  2024-09-17
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-NHSDataModelAndDictionary-AdmissionMethod">NHSDataModelAndDictionary-AdmissionMethod</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-NHSDataModelAndDictionary-DischargeDestination">NHSDataModelAndDictionary-DischargeDestination</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-NHSDataModelAndDictionary-DischargeMethod">NHSDataModelAndDictionary-DischargeMethod</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-NHSDataModelAndDictionary-OutcomeOfAttendance">NHSDataModelAndDictionary-OutcomeOfAttendance</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-NHSDataModelAndDictionary-PersonMaritalStatusCode">NHSDataModelAndDictionary-PersonMaritalStatusCode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-NHSDataModelAndDictionary-PersonStatedGenderCode">NHSDataModelAndDictionary-PersonStatedGenderCode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-NHSDataModelAndDictionary-SourceOfAdmission">NHSDataModelAndDictionary-SourceOfAdmission</a>
  2.0.0
  2022-01-07
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-AdditionalPersonRelationshipRole">UKCore-AdditionalPersonRelationshipRole</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-AddressKeyType">UKCore-AddressKeyType</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-AdmissionMethodEngland">UKCore-AdmissionMethodEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-AdmissionMethodWales">UKCore-AdmissionMethodWales</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-AppointmentReasonCode">UKCore-AppointmentReasonCode</a>
  1.0.0
  2022-05-20
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-BiopsyState">UKCore-BiopsyState</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ConditionCategory">UKCore-ConditionCategory</a>
  1.1.0
  2023-12-12
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ConditionEpisodicity">UKCore-ConditionEpisodicity</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ConditionRelationship">UKCore-ConditionRelationship</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ConsentUpdateMode">UKCore-ConsentUpdateMode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-DateTimeType">UKCore-DateTimeType</a>
  2.1.0
  2023-10-13
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-DeathNotificationStatus">UKCore-DeathNotificationStatus</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-DeliveryChannel">UKCore-DeliveryChannel</a>
  1.1.0
  2022-05-20
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-DischargeDestinationEngland">UKCore-DischargeDestinationEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-DischargeDestinationWales">UKCore-DischargeDestinationWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-DischargeMethodEngland">UKCore-DischargeMethodEngland</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-DischargeMethodWales">UKCore-DischargeMethodWales</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-EPSIssueCode">UKCore-EPSIssueCode</a>
  1.1.0
  2023-02-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-EmergencyCareOutcomeOfAttendanceWales">UKCore-EmergencyCareOutcomeOfAttendanceWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-EncounterLocationTypeEngland">UKCore-EncounterLocationTypeEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-EncounterLocationTypeWales">UKCore-EncounterLocationTypeWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-EthnicCategory">UKCore-EthnicCategory</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-EthnicCategoryEngland">UKCore-EthnicCategoryEngland</a>
  1.1.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-EthnicCategoryScotland">UKCore-EthnicCategoryScotland</a>
  1.1.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-EthnicCategoryWales">UKCore-EthnicCategoryWales</a>
  1.1.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-FundingCategory">UKCore-FundingCategory</a>
  2.0.0
  2024-06-14
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-GenomeSequencingCategory">UKCore-GenomeSequencingCategory</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-HumanLanguage">UKCore-HumanLanguage</a>
  2.1.0
  2023-12-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ITKResponseCode">UKCore-ITKResponseCode</a>
  1.0.0
  2023-02-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-LanguageAbilityMode">UKCore-LanguageAbilityMode</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-LanguageAbilityProficiency">UKCore-LanguageAbilityProficiency</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-LegalStatusClassificationEngland">UKCore-LegalStatusClassificationEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-LegalStatusClassificationWales">UKCore-LegalStatusClassificationWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-LegalStatusContext">UKCore-LegalStatusContext</a>
  1.0.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ListEmptyReasonCode">UKCore-ListEmptyReasonCode</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ListWarningCode">UKCore-ListWarningCode</a>
  2.1.0
  2022-01-07
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationAdministrationCategory">UKCore-MedicationAdministrationCategory</a>
  1.0.0
  2022-12-16
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationChangeStatus">UKCore-MedicationChangeStatus</a>
  1.0.1
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationPrescribingAgency">UKCore-MedicationPrescribingAgency</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationPrescribingOrganization">UKCore-MedicationPrescribingOrganization</a>
  1.0.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationPrescribingOrganizationType">UKCore-MedicationPrescribingOrganizationType</a>
  1.0.0
  2022-08-26
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationRequestCategory">UKCore-MedicationRequestCategory</a>
  1.1.1
  2023-10-06
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationRequestCourseOfTherapy">UKCore-MedicationRequestCourseOfTherapy</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationStatementCategory">UKCore-MedicationStatementCategory</a>
  1.0.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MedicationSupplyType">UKCore-MedicationSupplyType</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MessageEvent">UKCore-MessageEvent</a>
  2.1.0
  2022-12-16
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-MessageHeaderInstruction">UKCore-MessageHeaderInstruction</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-NHSNumberUnavailableReason">UKCore-NHSNumberUnavailableReason</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-NHSNumberVerificationStatus">UKCore-NHSNumberVerificationStatus</a>
  2.1.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-NHSNumberVerificationStatusEngland">UKCore-NHSNumberVerificationStatusEngland</a>
  1.1.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-NHSNumberVerificationStatusWales">UKCore-NHSNumberVerificationStatusWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-OrganizationTypeGenomics">UKCore-OrganizationTypeGenomics</a>
  1.0.0
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-OtherContactSystem">UKCore-OtherContactSystem</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-OutcomeOfAttendanceEngland">UKCore-OutcomeOfAttendanceEngland</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-OutcomeOfAttendanceWales">UKCore-OutcomeOfAttendanceWales</a>
  1.1.0
  2024-01-04
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-OverseasVisitorChargingCategory">UKCore-OverseasVisitorChargingCategory</a>
  1.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PeriodType">UKCore-PeriodType</a>
  1.0.0
  2023-10-13
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PersonMaritalStatus">UKCore-PersonMaritalStatus</a>
  1.0.0
  2022-08-26
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PersonMaritalStatusEngland">UKCore-PersonMaritalStatusEngland</a>
  1.1.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PersonMaritalStatusScotland">UKCore-PersonMaritalStatusScotland</a>
  1.0.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PersonMaritalStatusWales">UKCore-PersonMaritalStatusWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PracticeSettingCode">UKCore-PracticeSettingCode</a>
  1.0.1
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PracticeSettingCodeEngland">UKCore-PracticeSettingCodeEngland</a>
  1.0.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PracticeSettingCodeScotland">UKCore-PracticeSettingCodeScotland</a>
  1.0.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PracticeSettingCodeWales">UKCore-PracticeSettingCodeWales</a>
  1.0.1
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PreferredContactMethod">UKCore-PreferredContactMethod</a>
  2.2.0
  2023-10-09
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PreferredWrittenCommunicationFormat">UKCore-PreferredWrittenCommunicationFormat</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-PrescriptionType">UKCore-PrescriptionType</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ProblemSignificance">UKCore-ProblemSignificance</a>
  1.0.0
  2023-04-28
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-RecordStandardHeadings">UKCore-RecordStandardHeadings</a>
  2.2.0
  2022-08-03
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-RecordingSetting">UKCore-RecordingSetting</a>
  1.0.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ResidentialStatus">UKCore-ResidentialStatus</a>
  2.1.0
  2021-09-10
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-SDSJobRoleName">UKCore-SDSJobRoleName</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-SampleCategory">UKCore-SampleCategory</a>
  2.0.0
  2024-08-05
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-ServiceRequestMethod">UKCore-ServiceRequestMethod</a>
  1.0.0
  2022-05-20
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-SourceOfAdmissionEngland">UKCore-SourceOfAdmissionEngland</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-SourceOfAdmissionWales">UKCore-SourceOfAdmissionWales</a>
  1.0.1
  2023-04-28
  <span class="status active">active</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-SpineErrorOrWarningCode">UKCore-SpineErrorOrWarningCode</a>
  1.0.0
  2023-02-12
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-TreatmentCategory">UKCore-TreatmentCategory</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/CodeSystem-UKCore-WithheldIdentityReason">UKCore-WithheldIdentityReason</a>
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


## ConceptMaps

<div class="status-container">
<ul>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-AdministrativeGender">UKCore-AdministrativeGender</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-ConditionEpisodicity">UKCore-ConditionEpisodicity</a>
  2.0.0
  2022-12-16
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-MaritalStatus">UKCore-MaritalStatus</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

</ul></div><br><br>

---


## CapabilityStatements

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/apim-conformance">apim-conformance</a>
  1.0.0
  2022-12-16T00:00:00+00:00
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-FHIRExamples-Conformance">England-FHIRExamples-Conformance</a>
  3.2.0
  2022-12-16T00:00:00+00:00
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-MCED-Requirements">England-MCED-Requirements</a>
  0.0.1
  2024-01-23
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-ODS-Requirements">England-ODS-Requirements</a>
  0.0.5
  2024-09-17
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Pathology-Requirements">England-Pathology-Requirements</a>
  0.0.2
  2024-03-20
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-PatientFlag-Server-Requirements">England-PatientFlag-Server-Requirements</a>
  0.1.0
  2024-09-20
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/apim-conformance">apim-conformance</a>
  3.2.0
  2022-12-16T00:00:00+00:00
  <span class="status active">active</span>
</li>

</ul></div><br><br>

---


## SearchParameters

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Extension-OrganisationRole-ActiveRoleCode">England-Extension-OrganisationRole-ActiveRoleCode</a>
  0.0.2
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Extension-OrganisationRole-RoleCode">England-Extension-OrganisationRole-RoleCode</a>
  0.0.2
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Extension-TypedDateTime-LastChangeDate">England-Extension-TypedDateTime-LastChangeDate</a>
  0.0.2
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-FlagCategory">England-FlagCategory</a>
  0.4.0
  2024-02-14
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-FlagCode">England-FlagCode</a>
  0.1.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-FlagDetail">England-FlagDetail</a>
  0.4.0
  2024-02-14
  <span class="status active">active</span>
</li>

</ul></div><br><br>

---


