## {{page-title}}

### Purpose
For testing, obtained from raw specimen
To support storage, testing and interpretation.

### Notes
Mapped to Specimen.
It is expected extracted specimens will be additional specimens referencing the parent specimen via the Specimen.parent field.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Extracted specimen - Type|Specimen.type **Note: The ValueSet for this field is pending review to align with MDSv1.03**|SPM-4|Tissue of origin.|
|Extracted specimen - State|Specimen.condition **Note: The ValueSet for this field is pending review to align with MDSv1.03**|SPM-24|How has the specimen been preserved/fixed.|
|Extracted specimen - Extracted date|Specimen.processing.timeDateTime where Specimen.processing.procedure = 62972009, alternatively, could use Specimen.collection.collectedDateTime for the new Specimen|OBR-7 attached to processing procedure in SAC-30|Date at which a specimen was extracted from a previous specimen.|
|Extracted specimen - Id assigning authority ODS code (many)|Specimen.identifier.assigner|SPM-2.1.2|Authority who assigned the specimen id.|
|Extracted specimen - Id (many)|Specimen.identifier.value|SPM-2|Id of sample provided linked to the previously stated assigning authority. Occurs multiple times.|
|Extracted specimen - Location details|Not in scope for FHIR r4, could be attached to Tasks assigned to particular organizations, see also location details field under Raw Specimen/Biopsy|SAC-15|Where a raw specimen is in storage and not provided with a request.|
|Extracted specimen - Additional specimen information|Observation resources referencing Specimen for coded information or Specimen.note|OBX segments attached to SPM|Raw specimen/biopsy - Additional specimen/biopsy information.|
|Extracted specimen - Sample well identifier|Specimen.container.identifier|SAC-3|Id of the sample well.|