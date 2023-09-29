## Release notes
This page gives exact and clear details of the change done for this version.

All release notes are maintained. The latest is added to the top of page. 
<br/><br/>

|Release: Release Candidate 1.3.2 (Alert Changes)|
|--
|Ameded list of AlertReason to include values 1 - 6|
|Added list of AlertType (ValueSet & CodeSystem to include values 1 - 2|
|Updated profile SCR-AuditEvent and Example|

|Release: Release Candidate 1.2.2 (Scope clarifications)|
|--
|Clarified that the processing of a defined set of Covid-19 SNOMED-CT codes is in scope for processing structured medical information|
|Clarified that Initial GP Summary Upload is out of scope|
|Clarified that reading an Initial GP Summary Upload is in scope|
|Clarified that COVID code 1240581000000104, mapping is to 163131000000108  ClinicalObservationsandFindings-CareRecordElement (and NOT Investigation Result)|

<br/><br/>

|Release: Release Candidate 1.2.1 (Scope update)|
|--
|Out of scope: SCR Additional information as defined in SCR v2.1 changed to In scope: SCR Additional information as defined in SCR v2.1|

<br/><br/>

|Release: Release Candidate 1.2.0 (URL updates)|
|--
|references to https://fhir.nhs.uk/R4/StructureDefinition/UKCore-Observation" changed to https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation|
|references to https://fhir.nhs.uk/R4/StructureDefinition/UKCore-Encounter changed to https://fhir.hl7.org.uk/StructureDefinition/UKCore-Encounter|
|changed https://fhir.nhs.uk/R4/CodeSystem/SCR-ACSPermission to https://fhir.nhs.uk/CodeSystem/SCR-ACSPermission|
|changed https://fhir.nhs.uk/R4/CodeSystem/SCR-AlertReason to https://fhir.nhs.uk/CodeSystem/SCR-AlertReason|
|changed https://fhir.nhs.uk/R4/ValueSet/SCR-ACSPermission to https://fhir.nhs.uk/ValueSet/SCR-ACSPermission|
|changed https://fhir.nhs.uk/R4/ValueSet/SCR-AlertReason to https://fhir.nhs.uk/ValueSet/SCR-AlertReason|
|references to https://fhir.nhs.uk/R4/StructureDefinition/UKCore-Communication changed to https://fhir.hl7.org.uk/StructureDefinition/UKCore-Communication |
|Spec now uses UK Core v2 Composition https://fhir.hl7.org.uk/StructureDefinition/UKCore-Composition|
|changed https://fhir.nhs.uk/R4/StructureDefinition/UKCore-DocumentReference to reference to https://fhir.hl7.org.uk/StructureDefinition/UKCore-DocumentReference|
|change https://fhir.nhs.uk/R4/StructureDefinition/UKCore-Practitioner to https://fhir.hl7.org.uk/StructureDefinition/UKCore-Practitioner|
|changed https://fhir.nhs.uk/R4/StructureDefinition/UKCore-PractitionerRole to https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole|
|changed https://fhir.nhs.uk/R4/StructureDefinition/UKCore-Patient to https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient|
|changes https://fhir.nhs.uk/R4/StructureDefinition/UKCore-Procedure to https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure|
|changed https://fhir.nhs.uk/R4/StructureDefinition/UKCore-Immunization to https://fhir.hl7.org.uk/StructureDefinition/UKCore-Immunization
|changed https://fhir.nhs.uk/R4/StructureDefinition/UKCore-Organization to https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization|
|changed https://fhir.nhs.uk/R4/StructureDefinition/SCR-Alert-AuditEvent to https://fhir.nhs.uk/StructureDefinition/SCR-Alert-AuditEvent|
|changed https://fhir.nhs.uk/R4/StructureDefinition/Extension-SCR-NotificationMessage to https://fhir.nhs.uk/StructureDefinition/Extension-SCR-NotificationMessage |
||



<br/><br/>

|Release: Release Candidate 1.1.0|
|--
|Optional coded entries for COVID added|
|Removed pertinentInformation2 mapping from GPSummary page & added a link to the COVID population page|
|CareProfessionalDocumentationCRE/component/presentationText/effectiveTime/@value mapped to Composition.date|
|Corrected dateTime in <Observation> snippet|
|Corrected Observation status mapping from completed to final|

<br/><br/>

|Release: Release Candidate 1.0.0
|--
|initial release of the Summary Care Record upload document|


