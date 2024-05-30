## {{page-title}}

### Purpose
To track a patient, identify within shared systems and maintain complete records.
To apply processes applicable to deceased patient requests, patient contact and urgency purposes.
Data needed to support genetic interpretation, for PLCM to locate further patient ODS codes for a given test and to link patients to potential family members and their genetic results.

### Notes
Mapped to Patient resource, extensions not in UKCore are under review. Representation of Karyotypic Sex is through an Observation with code under Karyotype (cell structure) - SCTID: 734840008 or Anomaly of sex chromosome (disorder) - SCTID: 95462004 (these codes are under review). Representation of pregnancy and gestation is under discussion.

It is expected that practitioner and organization details for GPs will be referenced from Patient.generalPractitioner (e.g. using ODS/SDS identifiers) rather than be included as FHIR resources within Test Request payloads, though the full FHIR mapping has been provided below for completeness.

For Life Status at time of request for Foetal records, as per PRSB guidance, this should be inferred through outcome codes attached to the Pregnancy observation.

e.g. under Observation with code 77386006, ```Observation.component.valueCodeableConcept (with Observation.component.code = 267013003 | Past pregnancy outcome (observable entity) |)```

The component SNOMED codes SHOULD match the following list to map from foetal life statuses:

|PRSB Prgnancy Outcome|GEL Foetal Life Status|SNOMED CT Pregnancy Outcome Code|
|--|--|--|
|01	Live birth|N/A - not included in GEL list|281050002 - Livebirth (finding) (or captured through Patient.extension:bornStatus)|
|02	Antepartum Stillbirth|stillborn|713202001 - Antepartum stillbirth (finding)|
|03	Intrapartum Stillbirth|stillborn|921611000000101 - Intrapartum stillbirth (finding)|
|04	Stillbirth – timing unknown|stillborn|237364002 - Stillbirth (finding)|
|05	Termination of Pregnancy equal to or greater than 24 weeks|aborted|57797005 - Induced termination of pregnancy (disorder)|
|98	Other (not listed)|N/A not part of GEL life status ValueSet|potentially captured through Patient.extension:bornStatus = unknown|
|N/A not mapped exactly to PRSB ValueSet|miscarriage|17369002 - Miscarriage (disorder)|
|N/A no pregnancy outcome code|unborn|N/A no pregnancy outcome code (captured through Patient.extension:bornStatus)|


**Profiling for Procedure is currently in progress**

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Patient - First name|Patient.name.given|PID-5.2|Patient's first name.|
|Patient - Surname|Patient.name.family|PID-5.1|Patient's last name.|
|Patient - Date of birth|Patient.birthDate|PID-7|Patient's date of birth.|
|Patient - Address|Patient.address|PID-11|Patient's home address.|
|Patient - Postcode|Patient.address.postalCode|PID-11.5|Patient's home postcode.|
|Patient - Country|Patient.address.country|PID-11.6|Patient's home country.|
|Patient - Life status at time of request|Patient.deceasedBoolean (would be replaced by deceasedDateTime if date of death is known), representation of unknown implied by deceasedBoolean not being present. For Foetal records, foetal death SHOULD be recorded through the Patient.extension:bornStatus field. The type of death can be inferred through Observation components related to the mother's pregnancy observation (as in table above)|PID-30|Patient's alive or deceased status. |
|Patient - Ethnicity|Patient.extension:EthnicCategory|PID-22|Patient's ethnicity. Will have the option 'unknown' available.|
|Patient - Sex assigned at birth|Patient.extension:birthSex|PID-8|Patient's phenotypic sex classification. The external physical characteristics of the person. Currently determined by the Dr at birth. Gender for PLCM.|
|Patient - Organisation responsibile for GP practice ODS code|N/A obtained through parent of GP Practice as recorded within ODS, obtained through Patient.generalPractitioner|PD1-4.14|ODS code of organisation responsible for the GP Practice where the patient is registered.|
|Patient - GP Practice ODS Code|Patient.generalPractitioner.identifier (with system matching ODS NamingSystem)|PD1-4.14|Patient's GP practice ODS code.|
|Patient - Gender Identity same as at birth|N/A inferred through difference between Patient.extension:birthSex and Patient.extension:patient-genderIdentity|N/A - not part of the HL7v2 standard, though PID-8 or an OBX segment could be used|Confirmation if the patient's gender is the same as at birth.|
|Patient - Is from consanguinous union|FamilyMemberHistory.extension = family-member-history-genetics-observation( Observation.code=[842009](https://termbrowser.nhs.uk/?perspective=full&conceptId1=842009&edition=uk-edition&release=v20230607&server=https://termbrowser.nhs.uk/sct-browser-api/snomed&langRefset=999001261000000100,999000691000001104 ) ) or Observation attached to Patient|OBX-5 with appropriate SNOMED/READ/LOINC code|The fact of biological parents being descended from the same ancestor.|
|Patient - GP full name|Patient.generalPractitioner.display for general practitioner reference to practitioner (SDS identifier), not practice|PD1-4.2 and PD1-4.3|Patient's GP's full name.|
|Patient - NHS number|Patient.identifier:system = https://fhir.nhs.uk/Id/nhs-number |PID-3 where PID-3.5=2.16.840.1.113883.2.1.3.2.4.18.23|Patient NHS number.|
|Patient - Local identifier|Patient.identifier:system != https://fhir.nhs.uk/Id/nhs-number (local NamingSystem can be used, assigner determined through assigner field)|PID-3 where PID-3.5 = 2.16.840.1.113883.2.1.3.2.4.18.24|Patient identification code such as an NHS number.|
|Patient - Reason for unavailable NHS number|Patient.extension:nhsNumberUnavailableReason|N/A, could use PID-32 as surrogate|Reason for an NHS number not being provided.|
|Patient - Relationship to proband|RelatedPerson.relationship (alingment to MDS valueset pending review)|NK1-3|Relative's relationship to proband/index.|
|Patient - Gender Identity|Patient.extension:patient-genderIdentity|N/A - not part of the HL7v2 standard, though PID-8 or an OBX segment could be used|Patient's stated gender. The gender by which the person is addressed. Determined by the patient.|
|Patient - Date of death|Patient.deceasedDateTime|PID-29|Patient's date/time of death.|
|Patient - Karyotypic sex|Observation.code( subject=Patient, code = code under 734840008 or 95462004 as examples )|OBX-5 with appropriate SNOMED/READ/LOINC code|Patient's genomic / karyotypic characteristics. Determined after laboratory testing.|
|Patient - Pregnancy gestation period|Observation.component.valueDuration with code for gestation|OBX-14 (subtracted from ORC-9)|Patient's term of active pregnancy at point of test request.|
|Patient - Fetal gestation|As above, though could be inferred through difference between Observation.effectiveDateTime for pregnancy and Procedure.performedDateTime for termination|OBX-14 (subtracted from OBR-7 for termination procedure)|Stage during patient pregnancy at which it terminated.|
|Patient - Estimated Delivery Date (EDD)|As above, though could be inferred through Observation.effectiveDateTime for pregnancy + 40 weeks or new observation with code 161714006|OBX-14 + 40 weeks|Patient's estimated delivery date.|
|Patient - Pregnancy type|Inferred through presence of Procedure with codes under IUI/IVF (e.g. codes under 63487001)|OBR segments with appropriate codes|Type of conception.|
|Patient - IVF age of egg donor|**TBC** Observation referencing IVF procedure (through partOf) with code = 433475001 (if category of over 35 is sufficient, otherwise code.display of "IVF age of egg donor")|OBR segments with appropriate codes|The age of the patient who donated the egg at the time of donation.|
|Patient - Diagnosed with or being treated for cancer|**TBC** Inferred through attached Condition resources with code under 363346000 or Procedure etc. with reasonCode under same concept|OBR segments with appropriate codes|Has the patient been diagnosed with or are they being treated for cancer.|
|Patient - Had transplant|Inferred through presence of Procedure( subject=Patient ) with code under 77465005 - Transplantation, alternatively, Observation with code 77465005 with valueBoolean=false|Presence of OBR segment with OBR-44 code for transplant|Has the patient ever had a transplant.|
|Patient - Type of transplant|Procedure.code( subject=Patient, code= code under 77465005 )|OBR-44|What type of transplant the patient had. (Bone marrow / Stem cell)|
|Patient - Transplant date|Procedure.performedDateTime( subject=Patient )|OBR-7|When the patient had the transplant.|
|Patient - Had transfusion|Inferred through presence of Procedure( subject=Patient ) with code under 5447007 - Transfusion, alternatively, Observation with code 5447007 with valueBoolean=false|Presence of OBR segment with OBR-44 code for transplant|Has the patient ever had a transfusion.|
|Patient - Type of transfusion|Procedure.code( subject=Patient, code= code under 5447007 )|OBR-7|What type of transfusion the patient has had. (Packed Red Cells /Plasma / Platelets)|
|Patient - Transfusion date|Procedure.performedDateTime( subject=Patient )|OBR-7|When the patient had the transfusion.|
|Patient - Height (m)|Observation.valueQuantity( code=[54871000237100](https://termbrowser.nhs.uk/?perspective=full&conceptId1=54871000237100&edition=uk-edition&release=v20230607&server=https://termbrowser.nhs.uk/sct-browser-api/snomed&langRefset=999001261000000100,999000691000001104 ), subject=Patient)|OBX-5|Patient's height.|
|Patient - Sexual orientation (**pending review**)|Observation.value( subject=Patient, code=66621004)|OBX-5 with appropriate SNOMED/READ/LOINC code|Patient's sexual orientation.|
|Patient - Withheld identity reason|Additional codes to be part of Patient.extension:nhsNumberUnavailableReason ValueSet (as per [NHS Data Model and Dictionary](https://www.datadictionary.nhs.uk/data_elements/withheld_identity_reason.html), pending addition)|N/A, could use PID-32 as surrogate|Confirmation why the patient is withholding identity details.|
|Patient - GP's professional registration number|Patient.generalPractitioner.identifier with system for appropriate registration authority|PD1-4.1|Patient's GP's professional registration number.|
|Patient - Pedigree/Family Identifier|Patient.identifier:pedigreeNumber|Additional identifiers under PID-3|Patient's genetic/pedigree number which links their family.|
|Patient - Pregnancy status|Observation.code( subject=Patient, code=77386006 )|OBX-5 with appropriate SNOMED/READ/LOINC code|Patient's pregnancy status.|

<!--|Patient - Is relative|N/A determined through patient attached to ServiceRequest.subject|N/A determined though first PID segment in OML message (relatives referenced through NK1 segments)|Confirmation if this patient is the reported-on patient or a supplementary relative.|
|Patient - Fetal karyotypic sex|Observation.code( subject.display="fetus" )|OBX-5 with appropriate SNOMED/READ/LOINC code|Absence or presence of Y chromosome in the fetus.|
-->













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