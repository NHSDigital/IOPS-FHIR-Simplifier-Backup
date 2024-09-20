## {{page-title}}


### Purpose
To capture supporting information which has not been elsewhere specified

### Notes
If clinical information, likely mapped to Condition and Observation resources linked to the patient and referenced via ServiceRequest.supportingInfo. Otherwise collated within ServiceRequest.note

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Further supporting information|Linked Condition/Observation resources or ServiceRequest.note|Linked DG1/OBR segments or NTE segments in OML message|Supporting information which has not been captured elsewhere.|