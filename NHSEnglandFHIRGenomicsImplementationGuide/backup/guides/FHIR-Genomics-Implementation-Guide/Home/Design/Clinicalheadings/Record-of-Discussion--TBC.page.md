## {{page-title}}

### Purpose
For recording consent of patient data for research, based off the paper form available from the [Genomics GitHub repository](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/blob/main/documents/nhs-genomic-medicine-service-record-of-discussion-form.pdf)

### Notes
WGS Only
RoD forms will be stored as QuestionnaireResponse resources following the structure of the RoD Questionnaire resource, {{pagelink:Questionnaire-Genomic-Testing}}. 
Answers are not currently linked to structured identifiers, e.g. for patient and responsible clinician, this will be reviewed in a future release.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|RoD - Included|N/A - Inferred through inclusion of RoD Questionnaire Response|N/A - Inferred through inclusion of CON segment|Has RoD been included with request.|
|RoD - Patient category|Answer to RoD question with linkId patientCategory|CON-16|Confirmation of who made the RoD decisions.|
|Test type|Answer to RoD question with linkId testType|CON-2|If the test is WGS Cancer or WGS rare disease.|
|RoD - Research opt out reason|Answer to RoD question with linkId reasonsforChoiceA|CON-22|Why patient has opted out of research.|
|RoD - Remote consent|Answer to RoD question with linkId remoteConsent|CON-10|Where consent has been recorded on behalf of the patient via remote confirmation.|
|RoD - Recording clinician|Answer to RoD question with linkId healthcareProfessionalName|STF segment attached to CON|Name of the clinician who recorded the RoD details.|
|RoD - Responsible clinician|Answer to RoD question with linkId responsibleClinician|STF segment attached to CON|Name of the clinician who is responsible for the patient's genomic test request.|
|RoD - Record of discussion form - copy attached|Consent.sourceAttachment (or QuestionnaireResponse attached directly to message, TBC)|CON-19|Marker to confirm on a test request form that an RoD has been included.|
|RoD - Patient conversation taken place, ROD form to follow|Consent.status (TBC)|Inferred through CON-19 value|Marker to confirm RoD conversation has taken place but will be sent separately.|
|RoD - Patient choice status|Answer to RoD question with linkId researchConfirmation2|CON-11|Indication of the patient consenting to the genomic test request.|
|RoD - Has research participation been discussed|Answer to RoD question with linkId researchConfirmation1|Inferred through CON-12|Marker to confirm RoD conversation has taken place.|
|RoD - Signature|Answer to RoD question with linkId patientSignature|N/A not in scope for HL7v2|Copy of wet signature or valid e-signature.|
|RoD - Document/Link|N/A - Presence of DiagnosticReport in message|N/A not in scope for HL7v2|A copy of/or link to the previous genomic or non genomic report.|

<!--
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Patient category|N/A|N/A|Mandatory|Mandatory|Answer to RoD question with linkId patientCategory|CON-16||
|Test type|N/A|N/A|Mandatory|Mandatory|Answer to RoD question with linkId testType|CON-2||
|Research opt out reason|N/A|N/A|N/A|N/A|Answer to RoD question with linkId reasonsforChoiceA|CON-22||
|Remote consent|N/A|N/A|N/A|N/A|Answer to RoD question with linkId remoteConsent|CON-10||
|Recording clinician|N/A|N/A|Mandatory|Mandatory|Answer to RoD question with linkId healthcareProfessionalName|STF segment attached to CON||
|Responsible clinician|N/A|N/A|N/A|N/A|Answer to RoD question with linkId responsibleClinician|STF segment attached to CON||
|Record of discussion form - copy attached|N/A|N/A|Mandatory|Mandatory|Consent.sourceAttachment (or QuestionnaireResponse attached directly to message, TBC)|CON-19||
|Patient conversation taken place, ROD form to follow|N/A|N/A|Optional|Optional|Consent.status (TBC)|Inferred through CON-19 value||
|Patient choice status|N/A|N/A|Mandatory|Mandatory|Answer to RoD question with linkId researchConfirmation2|CON-11||
|Has research participation been discussed|N/A|N/A|Mandatory|Mandatory|Answer to RoD question with linkId researchConfirmation1|Inferred through CON-12||-->