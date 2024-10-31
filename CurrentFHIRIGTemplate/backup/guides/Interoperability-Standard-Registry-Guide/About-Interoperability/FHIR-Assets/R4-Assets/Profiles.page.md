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

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Consent-National-Proxy">England-Consent-National-Proxy</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
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

### Identifier

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Identifier-General-Medical-Council-Reference-Number">England-Identifier-General-Medical-Council-Reference-Number</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Identifier-General-Medical-Practitioner-Code">England-Identifier-General-Medical-Practitioner-Code</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Identifier-NHS-Number">England-Identifier-NHS-Number</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Identifier-Organisation-Code">England-Identifier-Organisation-Code</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Identifier-SDS-User-Id">England-Identifier-SDS-User-Id</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Identifier-SDS-User-Profile-Id">England-Identifier-SDS-User-Profile-Id</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
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

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Practitioner">England-Practitioner</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

### PractitionerRole

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-PractitionerRole">UKCore-PractitionerRole</a>
  2.4.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-PractitionerRole-Healthcare-Worker">England-PractitionerRole-Healthcare-Worker</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
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

### Reference

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-CodeableReference">England-CodeableReference</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

### RelatedPerson

<li class="ukcore"><a href="https://simplifier.net/hl7fhirukcorer4/UKCore-RelatedPerson">UKCore-RelatedPerson</a>
  2.5.0
  2024-07-11
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-RelatedPerson-National-Proxy">England-RelatedPerson-National-Proxy</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-RelatedPerson-PDS">England-RelatedPerson-PDS</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
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
  3.0.0
  2024-10-07
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

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-programme-implementation-guides/England-Task-National-Proxy">England-Task-National-Proxy</a>
  0.0.1-current
  2024-10-25T07:31:19+00:00
  <span class="status draft">draft</span>
</li>

</ul></div><br><br>

---


