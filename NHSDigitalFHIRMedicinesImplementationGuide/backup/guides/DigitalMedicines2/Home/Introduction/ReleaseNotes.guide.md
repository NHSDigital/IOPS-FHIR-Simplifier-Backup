## Release Notes

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS Digital</div>

#### 2.6.0

- Based on UKCore fhir.r4.ukcore.stu1 version 0.5.1
- Based on NHS Digital IG 2.6.0. See [Release Notes](https://simplifier.net/guide/nhsdigital/Home/Introduction/ReleaseNotes)


#### 2.3.0

- Based on UK Core Implementation Guide 0.1.0 - STU1 (ukcore.release1.stu1.01.01)
- Based on NHS Digital IG 2.3.0
- NHSDigital-Task reprofiled to ensure consistency.
  - reasonCode moved to statusReason
  - reasonCode is now SNOMED CT
- NHSDigital-Claim altered to make less use of subDetail, subDetail is now optional (to support non dispensed medications)
- NHSDigital-MedicationRequest and NHSDigital-MedicationDispense now have extra validation constraints.
- Examples corrected to use valid dm+d SNOMED CT


#### 2.1.40-alpha (5/Aug/2021)

- Dependencies moved to 
  - UKCore STU package: ukcore.r4.stu.02.00.00 version: 2.0.0
  - UKCore package: UKCore.R4.02.00.00 version: 2.0.0
  - NHS Digital package: uk.nhsdigital.r4 version: 2.2.0-discovery 
- Fix for https://simplifier.net/hl7fhirukcoreprofiler4-dstu/ukcoremedicationdispense/~issues/1707
- Fix for https://simplifier.net/hl7fhirukcoreprofiler4-dstu/ukcoremedicationdispense/~issues/1706
