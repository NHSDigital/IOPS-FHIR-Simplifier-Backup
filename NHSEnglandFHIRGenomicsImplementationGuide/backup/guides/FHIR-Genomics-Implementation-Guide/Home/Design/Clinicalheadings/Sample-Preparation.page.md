## {{page-title}}

### Purpose
Where cell separation is to be applied to a primary sample

### Notes
Mapped to Specimen.
It is expected processing performed on a specimen will be added to the original Specimen resource unless daughter samples are taken (splitting of the sample prior to processing), in which case a new Specimen resource SHOULD be created

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Sample Preparation - Parent primary sample id|Specimen.parent|SPM-3|Id of primary sample this derived from|
|Sample Preparation - Id (many)|Specimen.identifier.value|SPM-2|Id of sample provided linked to the previously stated assigning authority. Occurs multiple times.|
|Sample Preparation - Id assigning authority ODS code (many)|Specimen.identifier.assigner|SPM-2.1.2|Authority who assigned the sample id (e.g. histopathology, SHIMDS, etc). Occurs multiple times.|
|Sample Preparation - Sample storage details|Not in scope for FHIR R4, could use Specimen.note or record this information against Task.input (**TBC**, if required a request to backport Specimen.container.location will be made to support capture of this information)|SAC-15|Where a sample preparation is in storage or where it needs to be stored.|
|Sample Preparation - Volume|Specimen.collection.quantity|SPM-12|Volume of provided sample.|
|Sample Preparation - Performed date|Specimen.processing.timeDateTime|N/A not in scope for HL7v2, may need to replace SPM-17|Date at which the sample preparation was completed.|
|Sample Preparation - Received date|Specimen.receivedTime|SPM-18|Date at which a specimen was received at a laboratory.|
|Sample Preparation - Sample preparation|Specimen.processing.procedure|N/A not in scope for HL7v2, may need to be captured within SPM-6|Cell separation applied to a primary sample.|