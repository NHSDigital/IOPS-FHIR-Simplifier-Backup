## {{page-title}}

### Purpose
To track a patient, identify within shared systems and maintain complete records.
To apply processes applicable to deceased patient requests, patient contact and urgency purposes.
Data needed to support genetic interpretation, for PLCM to locate further patient ODS codes for a given test and to link patients to potential family members and their genetic results.

### Notes
Mapped to Patient resource, extensions not in UKCore are under review. Representation of Karyotypic Sex is through an Observation with code under Karyotype (cell structure) - SCTID: 734840008 or Anomaly of sex chromosome (disorder) - SCTID: 95462004 (these codes are under review). Representation of pregnancy and gestation is under discussion.

**Profiling for Procedure is currently in progress**

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Patient - Is relative|N/A determined through patient attached to ServiceRequest.subject|N/A determined though first PID segment in OML message (relatives referenced through NK1 segments)|Confirmation if this patient is the reported-on patient or a supplementary relative.|
|Patient - NHS number|Patient.identifier:system=https://fhir.nhs.uk/Id/nhs-number|PID-3 where PID-3.5=2.16.840.1.113883.2.1.3.2.4.18.23|Patient NHS number.|
|Patient - Local identifier|Patient.identifier:system!=https://fhir.nhs.uk/Id/nhs-number|PID-3 where PID-3.5=2.16.840.1.113883.2.1.3.2.4.18.24|Patient identification code such as an NHS number.|
|Patient - Reason for unavailable NHS number|Patient.extension:nhsNumberUnavailableReason|N/A, could use PID-32 as surrogate|Reason for an NHS number not being provided.|
|Patient - Withheld identity reason|Additional codes to be part of Patient.extension:nhsNumberUnavailableReason ValueSet (as per [NHS Data Model and Dictionary](https://www.datadictionary.nhs.uk/data_elements/withheld_identity_reason.html), pending addition)|N/A, could use PID-32 as surrogate|Confirmation why the patient is withholding identity details.|
|Patient - First name|Patient.name.given|PID-5.2|Patient's first name.|
|Patient - Surname|Patient.name.family|PID-5.1|Patient's last name.|
|Patient - Date of birth|Patient.birthDate|PID-7|Patient's date of birth.|
|Patient - Address|Patient.address|PID-11|Patient's home address.|
|Patient - Postcode|Patient.address.postalCode|PID-11.5|Patient's home postcode.|
|Patient - Country|Patient.address.country|PID-11.6|Patient's home country.|
|Patient - Life status at time of request|Patient.deceasedBoolean|PID-30|Patient's alive or deceased status.|
|Patient - Date of death|Patient.deceasedDateTime|PID-29|Patient's date/time of death.|
|Patient - Relationship to proband|RelatedPerson.relationship|NK1-3|Relative's relationship to proband/index.|
|Patient - Ethnicity|Patient.extension:EthnicCategory|PID-22|Patient's ethnicity. Will have the option 'unknown' available.|
|Patient - Sex assigned at birth|Patient.extension:birthSex|PID-8|Patient's phenotypic sex classification. The external physical characteristics of the person. Determined by the Dr / birth gender.|
|Patient - Gender Identity same as at birth|N/A inferred through difference between Patient.extension:birthSex and Patient.extension:patient-genderIdentity|N/A - not part of the HL7v2 standard, though PID-8 or an OBX segment could be used|Confirmation if the patient's gender is the same as at birth.|
|Patient - Gender Identity|Patient.extension:patient-genderIdentity|N/A - not part of the HL7v2 standard, though PID-8 or an OBX segment could be used|Patient's stated gender. The gender by which the person is addressed. Determined by the patient.|
|Patient - Sexual orientation|Observation.code(subject=Patient)|OBX-5 with appropriate SNOMED/READ/LOINC code|Patient's sexual orientation.|
|Patient - Karyotypic sex|Observation.code(subject=Patient)|OBX-5 with appropriate SNOMED/READ/LOINC code|Patient's genomic / karyotypic characteristics. Determined after laboratory testing.|
|Patient - GP Practice ODS Code|Patient.generalPractitioner(PractitionerRole.organization(Organization.identifier))|PD1-4.14|Patient's GP practice ODS code.|
|Patient - GP full name|Patient.generalPractitioner(PractitionerRole.practitioner(Practitioner.name))|PD1-4.2 and PD1-4.3|Patient's GP's full name.|
|Patient - GP GMC number|Patient.generalPractitioner(PractitionerRole.practitioner(Practitioner.identifier))|PD1-4.1|Patient's GP's professional registration number.|
|Patient - Pedigree/Family Identifier|Patient.identifier:pedigreeNumber|Additional identifiers under PID-3|Patient's genetic/pedigree number which links their family.|
|Patient - Pregnancy status|Observation.code(subject=Patient)|OBX-5 with appropriate SNOMED/READ/LOINC code|Patient's pregnancy status.|
|Patient - Pregnancy gestation period|Inferred through difference between Observation.effectiveDateTime and ServiceRequest.authoredOn|OBX-14 (subtracted from ORC-9)|Patient's term of active pregnancy at point of test request.|
|Patient - Fetal gestation|Inferred through difference between Observation.effectiveDateTime for pregnancy and Procedure.performedDateTime for termination|OBX-14 (subtracted from OBR-7 for termination procedure)|Stage during patient pregnancy at which it terminated.|
|Patient - Estimated Delivery Date (EDD)|Inferred through Observation.effectiveDateTime for pregnancy + 40 weeks or new observation with code 161714006|OBX-14 + 40 weeks|Patient's estimated delivery date.|
|Patient - Pregnancy type|Inferred through presence of Procedure with codes under IUI/IVF|OBR segments with appropriate codes|Type of conception.|
|Patient - Fetal karyotypic sex|Observation.code(subject.display="fetus")|OBX-5 with appropriate SNOMED/READ/LOINC code|Absence or presence of Y chromosome in the fetus.|
|Patient - Had transplant|Inferred through presence of Procedure(subject=Patient) with code under 77465005 - Transplantation|Presence of OBR segment with OBR-44 code for transplant|Has the patient ever had a transplant.|
|Patient - Type of transplant|Procedure.code(subject=Patient)|OBR-44|What type of transplant the patient had. (Bone marrow / Stem cell)|
|Patient - Transplant date|OBR-7|Procedure.performedDateTime(subject=Patient)|When the patient had the transplant.|
|Patient - Had transfusion|Inferred through presence of Procedure(subject=Patient) with code under 5447007 - Transfusion|Presence of OBR segment with OBR-44 code for transplant|Has the patient ever had a transfusion.|
|Patient - Type of transfusion|Procedure.code(subject=Patient)|OBR-7|What type of transfusion the patient has had. (Packed Red Cells /Plasma / Platelets)|
|Patient - Transfusion date|Procedure.performedDateTime(subject=Patient)|OBR-7|When the patient had the transfusion.|
|Patient - Is from consanguinous union|FamilyMemberHistory.extension=family-member-history-genetics-observation(Observation.code=[842009](https://termbrowser.nhs.uk/?perspective=full&conceptId1=842009&edition=uk-edition&release=v20230607&server=https://termbrowser.nhs.uk/sct-browser-api/snomed&langRefset=999001261000000100,999000691000001104)) or Observation attached to Patient|OBX-5 with appropriate SNOMED/READ/LOINC code|The fact of biological parents being descended from the same ancestor.|
|Patient - Height (m)|Observation.valueQuantity(code=[54871000237100](https://termbrowser.nhs.uk/?perspective=full&conceptId1=54871000237100&edition=uk-edition&release=v20230607&server=https://termbrowser.nhs.uk/sct-browser-api/snomed&langRefset=999001261000000100,999000691000001104), subject=Patient)|Patient's height.|

<!--
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Patient - Identifier (NHS number/Other)|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Patient.identifier|PID-3|Patient identification code such as an NHS number.|
|Patient - Reason for unavailable NHS number|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Patient.extension:nhsNumberUnavailableReason|N/A, could use PID-32 as surrogate|Reason for an NHS number not being provided.|
|Patient - First name|Mandatory|Mandatory|Mandatory|Mandatory|Patient.name.given|PID-5.2|Patient's first name.|
|Patient - Last name|Mandatory|Mandatory|Mandatory|Mandatory|Patient.name.family|PID-5.1|Patient's last name.|
|Patient - Date of birth|Mandatory|Mandatory|Mandatory|Mandatory|Patient.birthDate|PID-7|Patient's date of birth.|
|Patient - Address|Mandatory|Mandatory|Optional|Optional|Patient.address|PID-11|Patient's home address.|
|Patient - Postcode|Mandatory|Mandatory|Mandatory|Mandatory|Patient.address.postalCode|PID-11.5|Patient's home postcode.|
|Patient - Life status at time of request|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Patient.deceasedBoolean|PID-30|Patient's alive or deceased status.|
|Patient - Date/Time death|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Patient.deceasedDateTime|PID-29|Patient's date/time of death.|
|Patient - Ethnicity|Mandatory|Mandatory|Mandatory|Mandatory|Patient.extension:EthnicCategory|PID-22|Patient's ethnicity. Will have the option 'unknown' available.|
|Patient - Gender Identity|Mandatory IF|Mandatory IF|Mandatory|Mandatory|Patient.gender|N/A - not part of the HL7v2 standard, though PID-8 or an OBX segment could be used|Patient's stated gender. The gender by which the person is addressed. Determined by the patient. |
|Patient - Phenotypic sex (gender for PLCM)|Mandatory|Mandatory|Mandatory|Mandatory|Patient.extension:birthSex|PID-8|Patient's phenotypic sex classification. The external physical characteristics of the person. Determined by the Dr / birth gender.|
|Patient - Karyotypic sex|Mandatory IF|Optional|Optional|Optional|Observation.code(subject=Patient)|OBX-5 with appropriate SNOMED/READ/LOINC code|Patient's genomic / karyotypic characteristics. Determined after laboratory testing.|
|Patient - GP Practice ODS Code|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Patient.generalPractitioner(PractitionerRole.organization(Organization.identifier))|PD1-4|Patient's GP practice ODS code.|
|Patient - Clinical genetics no/pedigree number|Mandatory IF|N/A|Mandatory IF|N/A|Patient.identifier:pedigreeNumber|Additional identifiers under PID-3|Patient's genetic/pedigree number which links their family.|
|Patient - Pregnancy status|Mandatory IF|N/A|Mandatory IF|N/A|Observation.code(subject=Patient)|OBX-5 with appropriate SNOMED/READ/LOINC code|Patient's pregnancy status.|
|Patient - Pregnancy gestation period|Mandatory IF|N/A|Mandatory IF|N/A|Inferred through difference between Observation.effectiveDateTime and ServiceRequest.authoredOn|OBX-14 (subtracted from ORC-9)|Patient's term of active pregnancy at point of test request.|
|Patient - Fetal gestation|Optional|N/A|Optional|N/A|Inferred through difference between Observation.effectiveDateTime for pregnancy and Procedure.performedDateTime for termination|OBX-14 (subtracted from OBR-7 for termination procedure)|Stage during patient pregnancy at which it terminated.|
|Patient - Transplant status|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Inferred through presence of Procedure(subject=Patient) with code under 77465005 - Transplantation|Presence of OBR segment with OBR-44 code for transplant|Has the patient ever had a transplant.|
|Patient - Type of transplant|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Procedure.code(subject=Patient)|OBR-44|What type of transplant the patient had. (Bone marrow / Stem cell)|
|Patient - Transplant date|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|OBR-7|Procedure.performedDateTime(subject=Patient)|When the patient had the transplant.|
|Patient - Transfusion status|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Inferred through presence of Procedure(subject=Patient) with code under 5447007 - Transfusion|Presence of OBR segment with OBR-44 code for transplant|Has the patient ever had a transfusion.|
|Patient - Type of transfusion|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Procedure.code(subject=Patient)|OBR-7|What type of transfusion the patient has had. (Packed Red Cells /Plasma / Platelets)|
|Patient - Transfusion date|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Procedure.performedDateTime(subject=Patient)|OBR-7|When the patient had the transfusion.|
|Patient - Consanguinity|Mandatory IF|N/A|Mandatory IF|N/A|N/A - Determined through RelatedPerson.relationship codes|NK1-3|The fact of immediate family being descended from the same ancestor.|
-->