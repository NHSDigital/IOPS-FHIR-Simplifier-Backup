## {{page-title}}

### Purpose
For testing, obtained from raw specimen, material to be genomically tested.
To support storage, testing and interpretation.

### Notes
Mapped to Specimen.
It is expected extracted specimens will be additional specimens referencing the parent specimen via the Specimen.parent field.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Final Sample - Parent primary sample id|Specimen.parent (may be inferred through sample preparation parent, if this is not the primary sample resource)|SPM-3|Id of primary sample this derived from|
|Final Sample - Parent sample preparation id|Specimen.parent|SPM-3|Id of sample preparation this derived from|
|Final Sample - Id (many)|Specimen.identifier.value|SPM-2|Id of final sample provided, linked to the associated assigning authority. Occurs multiple times.|
|Final Sample - Id assigning authority ODS code (many)|Specimen.identifier.assigner|SPM-2.1.2|Authority who assigned the final sample id.|
|Final Sample - Sample storage details|Not in scope for FHIR R4, could use Specimen.note or record this information against Specimen.container.identifier (**TBC**, if required a request to backport Specimen.container.location will be made to support capture of this information)|SAC-15|Where a final sample is in storage or where it needs to be stored.|
|Final Sample - Volume|Specimen.collection.quantity|SPM-12|Volume of provided final sample.|
|Final Sample - Performed date|Specimen.processing.timeDateTime|N/A not in scope for HL7v2, may need to replace SPM-17|Date at which the final sample was extracted.|
|Final Sample - Received date|Specimen.receivedTime|SPM-18|Date at which a final specimen was received at a laboratory.|
|Final Sample - Final sample|Specimen.type|SPM-4|Material to be genomically tested.|

<!--
|Extracted specimen - Type|Specimen.type **Note: The ValueSet for this field is pending review to align with MDSv1.03**|SPM-4|Tissue of origin.|
|Extracted specimen - State|Specimen.condition **Note: The ValueSet for this field is pending review to align with MDSv1.03**|SPM-24|How has the specimen been preserved/fixed.|
|Extracted specimen - Extracted date|Specimen.processing.timeDateTime where Specimen.processing.procedure = 62972009, alternatively, could use Specimen.collection.collectedDateTime for the new Specimen|OBR-7 attached to processing procedure in SAC-30|Date at which a specimen was extracted from a previous specimen.|
|Extracted specimen - Id assigning authority ODS code (many)|Specimen.identifier.assigner|SPM-2.1.2|Authority who assigned the specimen id.|
|Extracted specimen - Id (many)|Specimen.identifier.value|SPM-2|Id of sample provided linked to the previously stated assigning authority. Occurs multiple times.|
|Extracted specimen - Location details|Not in scope for FHIR r4, could be attached to Tasks assigned to particular organizations, see also location details field under Raw Specimen/Biopsy|SAC-15|Where a raw specimen is in storage and not provided with a request.|
|Extracted specimen - Additional specimen information|Observation resources referencing Specimen for coded information or Specimen.note|OBX segments attached to SPM|Raw specimen/biopsy - Additional specimen/biopsy information.|
|Extracted specimen - Sample well identifier|Specimen.container.identifier|SAC-3|Id of the sample well.|
-->