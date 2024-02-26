---
topic: FHIRAssetsR4Profiles
---
## Profiles
The FHIR profiles that are referenced by this implementation guide are listed below. Each profile is documented using the format described in {{pagelink:ProfileDescriptions}}.

Refer to the {{pagelink:DesignOverview}} section for supporting information, including a description of the Pathology FHIR data model and the design approach that has been adopted as part of this implementation guide.

**Note:** The profiles are derived from the [UK Core Implementation Guide](https://simplifier.net/guide/ukcoreversionhistory/home?version=current), currently STU2. The pathology related profiles are currently under review as part of the [HL7 UK STU2 Ballot](https://confluence.hl7.org/pages/viewpage.action?pageId=175611042) process and are therefore subject to change. The STU2 version of the UK Core Implementation Guide introduced a new set of laboratory specific FHIR R4 derived profiles, indicated by the ‘Lab’ suffix in the profile name. These profiles are derived from the corresponding base R4 FHIR resource e.g. UKCore-DiagnosticReport-Lab is based on [DiagnosticReport](https://hl7.org/fhir/R4/diagnosticreport.html).

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

Refer to the following for a description of how the profiles may be used to form FHIR <code>Bundles</code> for test requesting and reporting:

* {{pagelink:BuildContructPathologyRequestBundle}}
* {{pagelink:BuildContructPathologyReportBundle}} 