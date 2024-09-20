## {{page-title}}

### Purpose
For samples directly obtained from a patient.
To track samples, direct storage, handling and testing decisions including ensuring volumes received match what was sent.
Further detail which may support testing and interpretation.
To enable patient to opt out of having a sample/biopsy stored.

### Notes
Mapped to Specimen.
Extensions lifted from mCODE are currently under review.
Observation codes linked to samples are pending addition to SNOMED-CT

**Additional observation code fields from MDS v1.04 mappings are still under review**

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Primary Sample - Destination organization ODS code|Not in scope for FHIR R4, could use Specimen.note or record this information against Task, e.g. inferred through the Task.owner who is intended to receive the specimen (**TBC**, if required a request to backport Specimen.container.location will be made to support capture of this information)|SAC-15|Destination for primary sample.|
|Primary Sample - Id (many)|Specimen.identifier.value|SPM-2|Id of sample provided linked to the previously stated assigning authority. Occurs multiple times.|
|Primary Sample - Id assigning authority ODS code (many)|Specimen.identifier.assigner|SPM-2.1.2|Authority who assigned the sample id (e.g. histopathology, SHIMDS, etc). Occurs multiple times.|
|Primary Sample - Received date|Specimen.receivedTime|SPM-18|Date at which a specimen was received at a laboratory.|
|Primary Sample - Sample storage details|Not in scope for FHIR R4, could use Specimen.note or record this information against Task.input (**TBC**, if required a request to backport Specimen.container.location will be made to support capture of this information)|SAC-15|Where a primary sample is in storage or where it needs to be stored.|
|Primary Sample - Volume|Specimen.collection.quantity|SPM-12|Volume of provided sample.|
|Primary Sample - Test Request Id|Specimen.request|ORC-2, included within the same OML message|The id of the associated genomic test being requested.|
|Primary Sample - Patient NHS number|Patient.identifier:system = https://fhir.nhs.uk/Id/nhs-number |PID-3 where PID-3.5=2.16.840.1.113883.2.1.3.2.4.18.23, within same OML message|Patient NHS number.|
|Primary Sample - Patient Local identifier|Patient.identifier:system != https://fhir.nhs.uk/Id/nhs-number (local NamingSystem can be used, assigner determined through assigner field)|PID-3 where PID-3.5 = 2.16.840.1.113883.2.1.3.2.4.18.24, within same OML message|Patient identification code other than NHS number.|
|Primary Sample - Obtained date|Specimen.collection.collectedDateTime|SPM-17|The time at which the sample/biopsy was obtained from the patient.|
|Primary Sample - Primary Sample|Specimen.type|SPM-4|Tissue of origin.|
|Primary Sample - Primary Sample State|Specimen.condition|SPM-24|How has the specimen been preserved/fixed. **Note: The ValueSet for this field is pending review to align with MDSv1.04**|
|Primary Sample - Necrosis|Observation.code( code=6574001 (**TBC**), specimen=Specimen )|OBX segment with appropriate code|% necrotic cells in specimen volume.|
|Primary Sample - Nucleated cell count|Observation.code( code=1022461000000100, specimen=Specimen )|OBX segment with appropriate code|Nucleated cell count in the specimen/biopsy (Solid Tumour and Haem-Onc).|
|Primary Sample - Tumour nuclear content|Observation.code( code=444901007 (**TBC**), specimen=Specimen )|OBX segment with appropriate code|Neoplastic cell content in the specimen/biopsy (Solid Tumour) - sourced at local lab. (%)|
|Primary Sample - Tumour cellularity|Observation.code( code=**TBC**, specimen=Specimen )|OBX segment with appropriate code|The proportion which is tumour nuclei.|
|Primary Sample - Solid tumour morphology|BodyStructure.morphology( patient=Patient ), referenced from Specimen.collection.bodysite.extension:bodySiteReference if in reference to a specimen, or referenced from a Condition if in relation to the patient's condition (**pending profiling of bodySiteReference backport to R4 Condition**)|Additional SPM-4/5 qualifiers|The histology and likely course of development of a tumour.|
|Primary Sample - Solid tumour topography|BodyStructure.location(patient=Patient), referenced from Specimen.collection.bodysite.extension:bodySiteReference if in reference to a specimen, or referenced from a Condition if in relation to the patient's condition (**pending profiling of bodySiteReference backport to R4 Condition**)|SPM-8|The tumour sample site. eg from colon, stomach etc.|
|Primary Sample - Biopsy site|Specimen.collection.bodySite|SPM-8/SPM-9|Site of biopsy.|
|Primary Sample - Skin/Bone affected status|Observation.valueBoolean ( code=22201000087104, specimen=Specimen ), assume unaffected if not provided|OBX segment with appropriate code|If the skin or bone provided is unaffected or affected.|
|Primary Sample - Maternal cell contamination (MCC)|Observation.valueBoolean( code=726741007, specimen=Specimen ), assume no MCC if not provided|OBX segment with appropriate code|Confirmation if MCC has been excluded from sample.|
|Primary Sample - Option for all products of conception|Additional Specimen.collection.extension:specimen-specialHandling with appropriate code/text|SPM-15|Future management for products of conception.|
|Primary Sample - Blasts %|Observation.code( code=1022601000000101, specimen=Specimen )|OBX segment with appropriate code|Blast count in the specimen/biopsy (Haemonc) - sourced at local SIHMDS.|
|Primary Sample - High infection risk reason|Specimen.collection.extension:specimen-specialHandling.valueCoding.code|SPM-16.2|The high contamination risk reason for a sample/biopsy.|



<!--
|Primary Sample - Is assigning authority a histopathology laboratory (many)|Derived from ODS - Specimen.identifier.assigner (**it is assumed ODS would have the necessary metadata to confirm lab type, this is pending internal review**)|Derived from ODS - SPM-2.1.2|Confirmation of an assigning authority ODS code being from a histopathology laboratory.|
|Primary Sample - Sample preparation (submitted to GLH)|Specimen.processing **Note: The ValueSet for this field is pending review to align with MDSv1.03**|Combination of SPM-6/SPM-24 or NTE segments if other processing|How has the specimen has been prepared for the GLH.|
|Primary Sample - WGS specimen type category|Specimen.extension:sampleCategory|SPM-5|WGS cancer high level category for the specimen.|
|Primary Sample - Family member provided by|Specimen.subject (links between Patient/RelatedPerson resources in test order would indicate family relationships)|Described within SPM-14|Which family member the specimen is provided by.|
|Primary Sample - Sample well identifier|Specimen.container.identifier|SAC-3|Id of the sample well.|
|Primary Sample - Blood component|Specific codes under Specimen.type|SPM-4|For a blood specimen, confirmation of which blood component the specimen consists of.|
|Primary Sample - Sample to follow|N/A implied through absence of Specimen in Test Order message, or Specimen.status=unavailable and missing Specimen.collection.collectedDateTime samples ordered but not collected|N/A SPM-20=N|Confirmation that the sample will be sent separately to, and after the test request.|
|Primary Sample - Sample to follow reason|Text in ServiceRequest.note field|NTE segment attached to ORC|Confirmation as to why the sample is being sent after the test request.|
|Primary Sample - Taken alive/post mortem|Observation.valueBoolean( code=839021000000109, specimen=Specimen ), true=post-mortem sample, assume taken alive if not provided|OBX segment with appropriate code|If a sample/biopsy was taken when the patient was alive or deceased.|
|Primary Sample - Additional specimen/biopsy information|Observation resources referencing Specimen for coded information or Specimen.note if unstructured|OBX segments attached to SPM|Raw specimen/biopsy - Additional specimen/biopsy information.|

| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Sample/Biopsy - Sample id assigning authority|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Specimen.identifier.assigner|SPM-2.1.2|Authority who assigned the sample id (Eg. histopathology, SHIMDS, etc). Occurs multiple times.|
|Sample/Biopsy - Sample id|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Specimen.identifier.value|SPM-2|Id of sample provided linked to the previously states assigning authority. Occurs multiple times.|
|Sample/Biopsy - Taken date|Optional|Optional|Mandatory|Mandatory|Specimen.collection.collectedDateTime|SPM-17|The time at which the sample/biopsy was taken from the patient.|
|Sample/Biopsy - High risk reason|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Specimen.collection.extension:specimen-specialHandling.valueCoding.code|SPM-16.2|The high contamination risk reason for a sample/biopsy.|
|Sample/Biopsy - Pathology tissue id|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Specimen.identifier (NamingSystem for different identifiers is currently inder consideration)|SPM-2.1|Id associated to tissue sample provided by pathology.|
|Sample/Biopsy - Type|Mandatory|Mandatory|Mandatory|Mandatory|Specimen.type|SPM-4|Type of sample/biopsy.|
|Sample/Biopsy - State|N/A|N/A|N/A|Mandatory|Specimen.extension:state|SPM-5|One of: Solid tumour sample, Liquid tumour sample, Normal or germline sample.|
|Sample/Biopsy - Solid tumour morphology|N/A|Mandatory IF|N/A|Mandatory IF|BodyStructure.morphology(patient=Patient)|Additional SPM-4/5 qualifiers|The histology and likely course of development of a tumour.|
|Sample/Biopsy - Solid tumour histological type (topography)|N/A|Mandatory IF|N/A|Mandatory IF|BodyStructure.location(patient=Patient)|SPM-8|The patient's solid tumour histological type (topography), where the tumour arose.|
|Sample/Biopsy - Biopsy site|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Specimen.collection.bodySite|SPM-8/SPM-9|Site of biopsy.|
|Sample/Biopsy - Skin/Bone affected status|Mandatory IF|N/A|N/A|N/A|Observation.valueBoolean (code=22201000087104,specimen=Specimen), assume unaffected if not provided|OBX segment with appropriate code|If the skin or bone provided is unaffected or affected.|
|Sample/Biopsy - Nuclei blasts / Neoplastic cell content|N/A|Mandatory IF|N/A|Mandatory IF|Observation.code(specimen=Specimen)|OBX segment with appropriate code|Neoplastic cell count is for solid tumour, nuclei blasts for haemonc.|
|Sample/Biopsy - Nucleated cell count|N/A|Mandatory IF|N/A|Mandatory IF|Observation.code(specimen=Specimen)|OBX segment with appropriate code|Nucleated cell count in the sample/biopsy.|
|Sample/Biopsy - Fetal sample count|Optional|N/A|Optional|N/A|Inferred through subject of Specimen (under discussion)|Inferred through subject of Specimen (under discussion)|Count of fetuses which have had a sample submitted.|
|Sample/Biopsy - Storage opt out|Optional|Optional|Optional|Optional|Consent.provision(type=deny,action=store,data.reference=Specimen)|CON segment, with CON-11=R|Option for patient to opt out of sample/biopsy storage.|
|Sample/Biopsy - Volume|Optional|Optional|Optional|Optional|Specimen.collection.quantity|SPM-12|Volume of provided sample.|
|Sample/Biopsy - Taken alive/post mortem|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Observation.valueBoolean (code=839021000000109,specimen=Specimen), true=post-mortem sample, assume taken alive if not provided|OBX segment with appropriate code|If a sample/biopsy was taken when the patient was alive or deceased.|
|Sample/Biopsy - Maternal cell contamination (MCC)|Mandatory IF|N/A|Mandatory IF|N/A|Observation.valueBoolean (code=726741007,specimen=Specimen), assume no MCC if not provided|OBX segment with appropriate code|Confirmation if MCC has been excluded from sample.|
-->