---
topic: FHIRAssetsR4Profiles
---
## Profiles
The key FHIR profiles that are referenced by this implementation guide are listed below. Each profile is documented using the format described in {{pagelink:ProfileDescriptions}}.

Refer to the {{pagelink:DesignOverview}} section for supporting information, including a description of the Pathology FHIR data model and the design approach that has been adopted as part of this implementation guide.

**Note:** The profiles are derived from the [UK Core Implementation Guide (Version 2.0.0 - STU2 Sequence)](https://simplifier.net/guide/uk-core-implementation-guide-stu2?current). The profile descriptions and additional guidance described in this implementation guide (i.e. the Pathology FHIR Implementation Guide) should be read in conjunction with the UK Core Implementation Guide. The STU2 version of the UK Core Implementation Guide introduced a new set of laboratory specific FHIR R4 derived profiles, indicated by the ‘Lab’ suffix in the profile name. These profiles are derived from the corresponding base R4 FHIR resource, rather than the UK Core version e.g. UKCore-DiagnosticReport-Lab is based on DiagnosticReport, not UKCore-DiagnosticReport.

* {{pagelink:R4Bundle}}
* {{pagelink:R4DiagnosticReport}}
* {{pagelink:R4MessageHeader}}
* {{pagelink:R4ObservationTestGroup}}
* {{pagelink:R4ObservationTestResult}}
* {{pagelink:R4Organization}}
* {{pagelink:R4Patient}}
* {{pagelink:R4Practitioner}}
* {{pagelink:R4PractitionerRole}}
* {{pagelink:R4ServiceRequest}}
* {{pagelink:R4Specimen}}

Refer to the following for a description of how the profiles may be used to form FHIR `Bundles` for test requesting and reporting:

* {{pagelink:BuildContructPathologyRequestBundle}}
* {{pagelink:BuildContructPathologyReportBundle}} 