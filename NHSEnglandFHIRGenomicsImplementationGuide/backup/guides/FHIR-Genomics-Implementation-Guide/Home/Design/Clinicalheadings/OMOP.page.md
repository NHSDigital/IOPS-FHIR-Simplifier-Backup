## {{page-title}}

### Purpose
Many research activities represent genomic information within [OHDSI's OMOP Common Data Model](https://www.ohdsi.org/data-standardization/), e.g. the [GOSH DRIVE Digital Research Environment (DRE) initiatives](https://www.goshdrive.com/copy-of-every-second-1) in representing report information within common data standards. 

To facilitate sharing of this information for Order Managment and the Unified Genomic Record, this information needs to be mapped to the FHIR standard. This mapping utilises the [HL7 Common Data Models for Harmonization (CDMH) Implementation Guide](https://build.fhir.org/ig/HL7/cdmh/profiles.html#omop-52-to-fhir-r4-mappings).

High level mappings from commonly used OMOP tables to FHIR Resources are provided below. For the full by element transformations, please see the CDMH guide linked above.

### Notes
Some of the tables commonly used within data collections are not yet investigated for use in Genomics, e.g. AdverseEvent, these will be investigated as the Structured Reporting efforts mature but it is expected that if these resources need to be shared, they should conform to the FHIR UK Core or base FHIR R4 specifications (in the absence of a UK Core profile).

### Mapping
| Source Data Table | Target FHIR Resource | Notes on Mapping |
|--|--|
|PERSON|Patient|ethnicity_concept_id SHOULD be mapped to the UK Core Ethnic Category extension|
|VISIT_OCCURRENCE|Encounter||
|CONDITION_OCCURRENCE|Condition||
|DEATH|AdverseEvent|If only datetime of death is required, this SHOULD be added to the Patient.deceasedDateTime field|
|DRUG_EXPOSURE|MedicationStatement|Medication and drug dosage information SHOULD conform to the [NHS Digital Medicines](https://simplifier.net/guide/nhsdigital-medicines?version=2.8.18) and [UK Core Interoperable Medicines](https://simplifier.net/guide/ukcoreimplementationguideformedicines/introduction?version=current) Implementation Guides|
|MEASUREMENT|Observation||
|OBSERVATION|Observation||
|PROCEDURE_OCCURRENCE|Procedure||
|SPECIMEN|Specimen||
|DEVICE_EXPOSURE|Procedure||