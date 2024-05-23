## {{page-title}}


### Purpose
To know known/suspected disease including status and traits to support testing and interpretation.
Further details which may support testing and interpretation including the family history of a disease.

### Notes
Mapped to Condition and Observation resources linked to the patient

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Disease status|Condition.clinicalStatus, Condition.verificationStatus (**Needs mapping to MDS enums**)|PRB-14|If the patient is affected, uncertain, unaffected, or it is unknown.|
|Phenotypic details (Many)|Condition.code with HPO system|Additional PRB segments (PRB-3)|The HPO (or alternative ontology as appropriate) term names for the observable disease traits.|
|Has multiple tumours|Inferred through multiple Condition.bodySite entries|Multiple PRB segments (bodySite for condition not in scope for HL7v2)|Does the patient have multiple tumours.|
|Count of tumours|Inferred through number of Condition/Condition.bodysite entries for tumours|Multiple PRB segments (bodySite for condition not in scope for HL7v2)|How many tumours the patient has.|
|Site of tumour (many)|codes used for Condition.bodysite entries|Multiple PRB segments (bodySite for condition not in scope for HL7v2)|Location of the tumours on the body.|
|Solid tumour type|Specific Condition.code e.g. child concepts of 128462008 for metastatic tumours|PRB-3|The patient's solid tumour type.|
|Liquid tumour type|Specific Condition.code, e.g. 91861009 for AML|PRB-3|The patient's liquid tumour type.|
|Known/suspected disease|Condition.verificationStatus|PRB-13|Disease a patient is believed, known to have, or be at risk of developing. |
|Date of diagnosis|Condition.recordedDate|PRB-7|The patient's date of diagnosis.|
|Pedigree details / Relevant family history|FamilyMemberHistory referenced from ServiceRequest.supportingInfo, optionally referenced from Condition.evidence.detail|N/A not in scope for HL7v2, could be added as additional PRB segments related to relatives|The patient's pedigree details/diagram (inc family history of cancer).|
|Pedigree diagram|Media referenced from ServiceRequest.supportingInfo, optionally referenced from Condition.evidence.detail|N/A not in scope for HL7v2, could be added as additional PRB segments related to relatives|Image attachment of pedigree details.|
|Disease penetrance|Inferred through FamilyMemberHistory.condition.outcome elements for each individual e.g. 29679002 for carriers|PRB segments related to relatives, though PRB-12 could be used|Confirms if all individuals with a disease show clinical symptoms or if there are carriers who do not.|
|Laterality of hearing loss|Specific Condition.code under Hearing loss e.g. 473424007|PRB-3|Laterality of the hearing loss i.e. bilateral or unilateral.|
|Fetal maternal screening genotype|Presence of Condition.code 62621000119107 for Fetal hemoglobinopathy (disorder)|PRB-3|Maternal screening genotype for haemoglobinopathy testing.|
|Is patient on TKI therapy|Presence of in-progress Procedure with code 1237262009 for Receptor tyrosine-protein kinase erbB-2 inhibitor therapy (procedure)|OBR-44|If the patient is on tyrosine kinase inhibitor therapy.|
|Is patient in treatment free remission|Condition.clinicalStatus = remission|PRB-14|If the patient in treatment free remission.|
|Further clinical information|Linked Condition/Observation resources|Linked PRB/OBR segments|Clinical information which has not been captured elsewhere.|
|Further non clinical information.|ServiceRequest.note|NTE segments in OML message|Non-clinical information which has not been captured elsewhere.|
|Genomic ethnicity|Observation.valueString( code=723621000000103 )|OBX-5|Patient's ethnicity where 'Patient - Ethnicity field' doesn't provide an adequate description. E.g Ashkenazi Jewish|
|Tumour sites - Body image diagram|Media **TBC**|N/A - not in scope for HL7v2|Image attachment of body with tumour sites highlighted.|
|Date of disease onset|Condition.onsetDateTime|PRB-16|The date when a change in patients health was first noted in line with suspected diagnosis.|
|Legal considerations|**TBC** Needs more specificity to properly model|**TBC**|Legal considerations for a given request.|
|Symptoms at onset|Condition.evidence.code|OBX segments attached to PRB|The patient's symptoms at onset.|
|ISTH BAT score|Observation.valueQuantity (note: no SNOMED code currently exists for the ISTH-BAT tool so this will need to be coded as text within Observation.code)|OBX-5|Bleeding score - high bleeding score is associated with the presence of an inherited bleeding disorder|
|Fetal paternal screening genotype|Condition.code 80141007 for Hemoglobinopathy (disorder) attached to paternal Patient resource (or associated carrier code)|PRB-3|Paternal screening genotype for haemoglobinopathy testing.|
|Expected maternity unit - Organisation name|**TBC** Future dated Encounter with referenced serviceProvider|ROL segment attached to PV1|Requesting clinician's organisation name.|
|Expected maternity unit - Organisation address|**TBC** Future dated Encounter with referenced serviceProvider|ROL segment attached to PV1|Requesting clinician's organisation address.|
|Expected maternity unit - Organisation ODS code|**TBC** Future dated Encounter with referenced serviceProvider|ROL segment attached to PV1|Requesting clinician's organisation ODS code.|
|Expected maternity unit - Department name|**TBC** Future dated Encounter with referenced serviceProvider|ROL segment attached to PV1|Requesting clinician's department name.|
|Growth history|**TBC** Observation resources for head circumference etc.|OBX segments|Summary passage of text to highlight patient centile history e.g head circumference, weight, etc.|
|Severity of hearing loss|Condition.code with appropriate code under 15188001 or Condition.note with code 15188001|PRB-3|Free text regarding hearing loss|
|Retinal degeneration|Condition.code with appropriate code under 95695004 or Condition.note with code 95695004|PRB-3|Free text regarding retinal degeneration|
|Risk factors|MedicationStatement resources with certain codes **TBC**|RXA-5|Toxic medication - Prematurity (risk factor for hearing loss) e.g. Baby early birth - Ototoxic medication.|
|Hepatic vs neurological presentation|Condition.code with either Hepatic or Neurological SNOMED codes||Outcome of either Hepatic or Neurological.|
|Suspected inborn error type(s)|Condition.code with code under 86095007 and verificationStatus provisional/unconfirmed|PRB-3|Suspected inborn error type(s)|
|Abnormal infection history site|**TBC** Condition.bodySite for relevant infection entries|**TBC**|Abnormal infection history Site|
|Abnormal infection history site organism|**TBC** Condition.bodySite for relevant infection entries with reference to specific body structures|**TBC**|Abnormal infection history Site organism|
|Is on Ig replacement|**TBC** Procedure.code with code 698802001 with status=in-progress|**TBC**|If the patient is on immunoglobin replacement treatment.|

<!--
|MODY probability calculator score|Observation with code under 609561005 for Maturity-onset diabetes of the young (disorder)|OBX-5|Exeter's diabetic risk calculator|
|Insulin treated within 6 months of diagnosis|Presence of Procedure with appropriate Insulin Therapy code with performed\[x\] within six months of the ServiceRequest.authoredOn date|OBR-44|Has the patient been treated for insulin within the last 6 months of diagnosis.|
|Diagnosis during pregnancy|Overlap of Condition.recordedDate with Observation.effectivePeriod for pregnancy|PRB segment overlapping OBC for pregnancy|Was the patient diagnosed during pregnancy|
|Patient BMI at time of genomic test request|Observation with code 60621009 for Body mass index (observable entity) with effectiveDateTime same as ServiceRequest.authoredOn|OBX-5|Patient BMI at time of genomic test request|
|Patient BMI at time of diagnosis|Observation with code 60621009 with effectiveDateTime same Condition.recordedDate|OBX-5|Patient BMI at time of diagnosis|
|Maternal BMI at time of request|Observation with code 60621009 attached to maternal Patient resource with effectiveDateTime same as ServiceRequest.authoredOn|OBX-5|Maternal body mass index at time of request.|
|Paternal BMI at time of request|Observation with code 60621009 attached to paternal Patient resource with effectiveDateTime same as ServiceRequest.authoredOn|OBX-5|Paternal body mass index at time of request.|
|Initial therapy: Insulin subtype - Units per dose|First MedicationStatement.dosage.doseAndRate.doseQuantity with appropriate medicationCodeableConcept for Insulin|RXA-6|Initial therapy: Insulin subtype - Units per dose|
|Initial therapy: Insulin subtype - Frequency|First MedicationStatement.dosage.timing.repeat with appropriate medicationCodeableConcept for Insulin|RXA-12|Initial therapy: Insulin subtype - Frequency|
|Initial therapy: Insulin subtype - Oral hypoglycemic agents (OHA) subtype units per dose|First MedicationStatement.dosage.doseAndRate.doseQuantity with appropriate medicationCodeableConcept for Insulin OHA (codes under 420100005)|RXA-6|Initial therapy: Insulin subtype - Oral hypoglycemic agents (OHA) subtype units per dose|
|Initial therapy: Insulin subtype - Oral hypoglycemic agents (OHA) subtype frequency|First MedicationStatement.dosage.timing.repeat with appropriate medicationCodeableConcept for Insulin OHA (codes under 420100005)|RXA-12|Initial therapy: Insulin subtype - Oral hypoglycemic agents (OHA) subtype frequency|
|Current therapy: Insulin subtype - Units per dose|MedicationStatement.dosage.doseAndRate.doseQuantity with appropriate medicationCodeableConcept for Insulin|RXA-6|Current therapy: Insulin subtype - Units per dose|
|Current therapy: Insulin subtype - Frequency|MedicationStatement.dosage.timing.repeat with appropriate medicationCodeableConcept for Insulin|RXA-12|Current therapy: Insulin subtype - Frequency|
|Current therapy: Insulin subtype - Oral hypoglycaemic agents (OHA) subtype units per dose|MedicationStatement.dosage.doseAndRate.doseQuantity with appropriate medicationCodeableConcept for Insulin OHA (codes under 420100005)|RXA-6|Current therapy: Insulin subtype - Oral hypoglycaemic agents (OHA) subtype units per dose|
|Current therapy: Insulin subtype - Oral hypoglycaemic agents (OHA) subtype frequency|MedicationStatement.dosage.timing.repeat with appropriate medicationCodeableConcept for Insulin OHA (codes under 420100005)|RXA-12|Current therapy: Insulin subtype - Oral hypoglycemic agents (OHA) subtype frequency|
|Neonatal hypoglycemia treatment details|Procedure/MedicationStatement with appropriate code for treatment and reasonCode=52767006|OBR/RXA segments|Newborn hypoglycemia treatment details.|
|Neonatal hypoglycemia treatment start date|Procedure.performedPeriod.start / MedicationStatement.effectivePeriod.start|OBR-7|Newborn hypoglycemia treatment start date.|
|Neonatal hypoglycemia treatment end date|Procedure.performedPeriod.end / MedicationStatement.effectivePeriod.end|OBR-8|Newborn hypoglycemia treatment end date.|
|Birth weight|Observation with code 364589006|OBX-5|Weight at birth in grams.|
|Diabetic complications|Observation/Condition resources referencing original Diabetes Condition|OBX/PRB segments|Diabetic complications|
|Insulin dose at presentation|MedicationStatement.dosage.doseAndRate.doseQuantity with appropriate medicationCodeableConcept for Insulin and effectivePeriod overlapping Encounter date|RXA-6|Insulin dose at presentation (U/kg/day)|
|Insulin dose at time of genomic test request|MedicationStatement.dosage.doseAndRate.doseQuantity with appropriate medicationCodeableConcept for Insulin and effectivePeriod overlapping ServiceRequest.authoredOn date|RXA-6|Insulin dose at time of request (U/kg/day)|
|Is diabetes in remission|Inferred through Condition.clinicalStatus for Diabetes||Has patient's diabetes gone into remission.|
|Date of diabetes remission|Either inferred though history of changes to Condition resource or Condition.note|NTE segment attached to PRB|Date patient's diabetes went into remission.|
|Is diabetes in relapse|Inferred through Condition.clinicalStatus for Diabetes|PRB-14|Has patient's diabetes relapsed.|
|Date of diabetes relapse|Either inferred though history of changes to Condition resource or Condition.note||Date of diabetes relapse.|
|Current exocrine pancreatic treatment|Procedure/MedicationStatement for Conditions with exocrine/pancreatic codes|OBR/RXA segments|Is patient on exocrine pancreatic treatment.|
|Exocrine pancreatic treatment start date|MedicationStatement.effectiveDateTime or Procedure.performedDateTime|RXA-3|Date exocrine pancreatic treatment started.|
|Thyroid gland state|Condition.code with SNOMED code for issue|PRB-3|State of thyroid gland.|
|Pituitary tumour type|Condition.code with appropriate SNOMED code under 127024001|PRB-3|Pituitary tumour type|
|Pancreatic tumour type|Condition.code with appropriate SNOMED code under 126859007|PRB-3|Pancreatic tumour type|
|Phaeochromocytoma|Condition.bodySite, with appropriate Condition.code under SNOMED code 302835009|Not in scope for HL7v2|Phaeochromocytoma laterality|
|Paraganglioma location|Condition.bodySite, with appropriate Condition.code under SNOMED code 302833002|Not in scope for HL7v2|Paraganglioma location|
|Duration of hyperinsulism|Difference between Condition.onsetDateTime and abatementDataTime for code 83469008|PRB-9 - PRB-16|Duration of hyperinsulism|
|Current treatment|Set of MedicationStatement.medicationCodeableConcepts with effectivePeriod overlapping current time or status active|RXA-5|What is their current treatment to understand responsiveness.|
|Current treatment dose with units|MedicationStatement.dosage for treatment|RXA-6|Dose with units|
|Had response to current treatment|MedicationStatement.note (could include observations/condition resources to infer response but this may be difficult to interpret|NTE attached to RXA|Had response to current treatment|
|Name of other medications tried|Additional MedicationStatement resources|RXA segments|Name of other medications tried|
|Duration other medications tried|MedicationStatement.effectivePeriod|RXA-3|Duration other medications tried|
|Subcutaneous fat loss areas|Observation.bodySite with code 248316006 or child concepts of 248316006|OBX-5|Subcutaneous fat loss from:|
|Increased fat deposition areas|Observation.bodySite with code 248313003|Not in scope for HL7v2|Increased fat deposition location|
|Has absent reflexes|Observation with code 37280007|OBX-5|Has absent reflexes|
|Absent reflexes detail|Observation with child code under 37280007|OBX-5|Absent reflexes detail|
|Progeroid features|Condition.code with code 1216939003 or 1220589007|PRB-3|Progeroid features|
-->
<!-- 
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|CP - Date of diagnosis|N/A|N/A|N/A|Mandatory|Condition.recordedDate|PRB-7|The patient's date of diagnosis.|
|CP - Known or suspected rare disease|Optional|N/A|Optional|N/A|Condition.code (with verificationStatus provisional or unconfirmed)|PRB-3|Rare disease a patient is believed or known to have.|
|CP - Disease status|Mandatory|N/A|Mandatory|N/A|Condition.severity|PRB-14|If the patient is affected, unaffected or it is unknown, in regards to the disease.|
|CP - HPO term names|Optional|N/A|Mandatory|N/A|Condition.code with HPO system|Additional PRB segments (PRB-3)|The HPO term names for the patients observable disease traits.|
|CP - Date at onset|Optional|Optional|Optional|Optional|Condition.onsetDateTime|PRB-16|The patient's age at onset of disease.|
|CP - Symptoms at onset|Optional|Optional|Optional|Optional|Condition.evidence.code|OBX segments attached to PRB|The patient's symptoms at onset.|
|CP - Solid tumour type|N/A|Mandatory IF|N/A|Mandatory IF|Contained in Condition.code (a suitably specific code needs to be chosen)|PRB-3|The patient's solid tumour type.|
|CP - Liquid tumour type|N/A|Mandatory IF|N/A|Mandatory IF|Contained in Condition.code (a suitably specific code needs to be chosen)|PRB-3|The patient's liquid tumour type.|
|CP - Pedigree details/diagram|Mandatory IF|N/A|Mandatory IF|N/A|Condition.evidence.detail(reference(FamilyMemberHistory,Media))|N/A not in scope for HL7v2, could be added as additional PRB segments related to relatives|The patient's pedigree details/diagram.|
|CP - Consanguinity|Mandatory IF|N/A|Mandatory IF|N/A|Condition.evidence.detail(reference(FamilyMemberHistory.relationship))|N/A not in scope for HL7v2, use additional PRB segments as above, see Relative section for relationship mapping|The fact of immediate family being descended from the same ancestor.|
|CP - Disease penetrance (complete/incomplete)|Mandatory IF|N/A|Mandatory|N/A|Inferred through Condition.evidence.detail(reference(FamilyMemberHistory.condition)) elements for each individual |PRB segments related to relatives, though PRB-12 could be used|Confirms if all individuals with a disease show clinical symptoms or if there are carriers who do not.|
|CP - Pathological report|Optional|Optional|Optional|Mandatory|ServiceRequest.supportingInfo(DiagnosticReport)|ORU/OBR segments|The patient's pathological report produced prior to referral for genomic testing.|
|CP - Any additional information|Optional|Optional|Optional|Optional|Additional Condition or Observation resources with subject=Patient|Additional PRB segments|Further information linked to the patient's clinical presentation.|
-->