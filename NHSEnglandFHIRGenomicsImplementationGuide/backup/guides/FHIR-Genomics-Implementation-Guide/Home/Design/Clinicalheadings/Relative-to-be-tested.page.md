## {{page-title}}

### Purpose
**Superseded by Specific fields under Patient heading**

GEL/PLCM requirements.
<!--
### Notes
Relationship mapped to RelatedPerson (linked to index patient through RelatedPerson.patient). If additional clinical history is required, this should be captured through a FamilyMemberHistory resource. If details need to be captured for additional testing, relative details should be included as separate Patient resources attached to their own ServiceRequest orders.
Clinical/demographic information related to the RelatedPerson SHOULD be captured within a Patient resource using the existing fields/extensions, and linked to the RelatedPerson through the Patient.link field. 

### Mapping
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|WGS relative - Identifier (NHS number/Other)|N/A|N/A|Mandatory IF|N/A|Patient.identifier(link.other=RelatedPerson)|NK1-33|WGS relative's identification code such as an NHS number.|
|WGS relative - Relationship to proband/index|N/A|N/A|Mandatory|N/A|RelatedPerson.relationship|NK1-3|WGS relative's relationship to proband/index.|
|WGS relative - First name|N/A|N/A|Mandatory|N/A|Patient.name.given(link.other=RelatedPerson)|NK1-2.2|WGS relative's first name.|
|WGS relative - Last name|N/A|N/A|Mandatory|N/A|Patient.name.family(link.other=RelatedPerson)|NK1-2.1|WGS relative's last name.|
|WGS relative - Date of birth|N/A|N/A|Mandatory|N/A|Patient.birthDate(link.other=RelatedPerson)|NK1-16|WGS relative's date of birth.|
|WGS relative - Postcode|N/A|N/A|Mandatory|N/A|Patient.address.postalCode(link.other=RelatedPerson)|NK1-4|WGS relative's postcode.|
|WGS relative - Life status|N/A|N/A|Mandatory|N/A|Patient.deceasedBoolean(link.other=RelatedPerson)|Not part of NK1 segment, use PID-29 with same identifier as NK1|WGS relative's life status.|
|WGS relative - Ethnicity|N/A|N/A|Mandatory|N/A|Patient.extension:EthnicCategory(link.other=RelatedPerson)|NK1-28|WGS relative's ethnicity. Will have the option 'unknown' available.|
|WGS relative - Gender Identity|N/A|N/A|Mandatory|N/A|Patient.gender(link.other=RelatedPerson)|N/A - not part of the HL7v2 standard, though PID-8 or an OBX segment could be used|WGS relative's stated gender. The gender by which the person is addressed. Determined by the patient. |
|WGS relative - Phenotypic sex (gender for PLCM)|N/A|N/A|Mandatory|N/A|Patient.extension:birthSex(link.other=RelatedPerson)|NK1-15|WGS relative's phenotypic sex classification. The external physical characteristics of the person. Determined by the Dr / birth gender.|
|WGS relative - GP Practice ODS Code|N/A|N/A|Mandatory|N/A|Patient.generalPractitioner(link.other=RelatedPerson)|PD1-4 with same identifier as the NK1 segment|The ODS code for the WG relative's GP practice.|


## Cascade Patient

### Purpose
To track a cascade patient, identify within shared systems and maintain complete records.
To apply processes applicable to deceased cascade patient requests, patient contact and urgency purposes.
Data needed to support genetic interpretation, for PLCM to locate further patient ODS codes for a given test and to link patients to potential family members and their genetic results.

### Notes
Mapped to Patient, linked to index patient through ServiceRequest e.g. ServiceRequest for Cascade Patient (intent=reflex-order) references original ServiceRequest through 'basedOn' field. The original ServiceRequest references the index Patient through the 'subject' field.
The MessageDefinition for Genomic Test Orders currently only allows one ServiceRequest per message so Cascade Patient test orders currently need to be separated into separate order messages. 
Multiple ServiceRequests per message for duo/trio and cascade patient test ordering is being considered.
Other considerations for field mappings are as per the Patient section.

### Mapping
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description  
|--|--|
|Cascade patient - Identifier (NHS number/Other)|Mandatory IF|N/A|N/A|N/A|Patient.identifier|PID-3|Cascade patient identification code such as an NHS number.|
|Cascade patient - Reason for unavailable NHS number|Mandatory IF|N/A|N/A|N/A|Patient.extension:nhsNumberUnavailableReason|N/A, could use PID-32 as surrogate|Reason for an NHS number not being provided.|
|Cascade patient - First name|Mandatory|N/A|N/A|N/A|Patient.name.given|PID-5.2|Cascade patient's first name.|
|Cascade patient - Last name|Mandatory|N/A|N/A|N/A|Patient.name.family|PID-5.1|Cascade patient's last name.|
|Cascade patient - Date of birth|Mandatory|N/A|N/A|N/A|Patient.birthDate|PID-7|Cascade patient's date of birth.|
|Cascade patient - Address|Mandatory|N/A|N/A|N/A|Patient.address|PID-11|Cascade patient's home address.|
|Cascade patient - Postcode|Mandatory|N/A|N/A|N/A|Patient.address.postalCode|PID-11.5|Cascade patient's home postcode.|
|Cascade patient - Life status|Mandatory IF|N/A|N/A|N/A|Patient.deceasedBoolean|PID-30|Cascade patient's alive or deceased status.|
|Cascade patient - Ethnicity|Mandatory|N/A|N/A|N/A|Patient.extension:EthnicCategory|PID-22|Cascade patient's ethnicity. Will have the option 'unknown' available.|
|Cascade patient - Gender Identity|Mandatory IF|N/A|N/A|N/A|Patient.gender|N/A - not part of the HL7v2 standard, though PID-8 or an OBX segment could be used|Cascade patient's stated gender. The gender by which the person is addressed. Determined by the patient. |
|Cascade patient - Phenotypic sex (gender for PLCM)|Mandatory|N/A|N/A|N/A|Patient.extension:birthSex|PID-8|Cascade patient's phenotypic sex classification. The external physical characteristics of the person. Determined by the Dr / birth gender.|
|Cascade patient - Karyotypic sex|Mandatory IF|N/A|N/A|N/A|Observation.code(subject=Patient)|OBX-5 with appropriate SNOMED/READ/LOINC code|Cascade patient's genomic / karyotypic characteristics. Determined after laboratory testing.|
|Cascade patient - GP Practice ODS Code|Mandatory IF|N/A|N/A|N/A|Patient.generalPractitioner(PractitionerRole.organization(Organization.identifier))|PD1-4|The ODS code for the cascade patient's GP practice.|
|Cascade patient - Clinical genetics no/pedigree number|Mandatory IF|N/A|N/A|N/A|Patient.identifier:pedigreeNumber|Additional identifiers under PID-3|Cascade patient's genetic/pedigree number which connects a family.|
|Cascade patient - Pregnancy status|Mandatory IF|N/A|N/A|N/A|Observation.code(subject=Patient)|OBX-5 with appropriate SNOMED/READ/LOINC code|Cascade patient's pregnancy status.|
|Cascade patient - Pregnancy gestation period|Mandatory IF|N/A|N/A|N/A|Inferred through difference between Observation.effectiveDateTime and ServiceRequest.authoredOn|OBX-14 (subtracted from ORC-9)|Cascade patient's term of active pregnancy at point of test request.|
|Cascade patient - Fetal gestation|Optional|N/A|N/A|N/A|Inferred through difference between Observation.effectiveDateTime for pregnancy and Procedure.performedDateTime for termination|OBX-14 (subtracted from OBR-7 for termination procedure)|Stage during cascade patient pregnancy at which it terminated.|
-->