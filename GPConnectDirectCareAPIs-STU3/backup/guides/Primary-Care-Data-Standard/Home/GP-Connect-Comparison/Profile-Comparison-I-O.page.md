## {{page-title}}

## Immunization
|Element Name|Description|PCDS Cardinality|GPC Cardinality|
|-
|Not given flag|Flag to indicate that the vaccination was NOT given at this time by a healthcare professional|0...1|1...1|
|Reported|A flag to indicate the information was reported to a professional|0...1|1...1|
***

The following elements are present in GP Connect, but not used in the PCDS: 

- Immunization.encounter
- Immunization.date
- Immunization.location

***

## Medication Request

The following elements are present in GP Connect, but not used in the PCDS:

- MedicationRequest.groupIdentifier
- MedicationRequest.basedOn
- MedicationRequest.groupIdentifier
- MedicationRequest.medication
- MedicationRequest.reasonReference

***

## Medication Statement

The following elements are present in GP Connect, but not used in the PCDS:

- MedicationStatement.partOf
- MedicationStatement.context
- MedicationStatement.informationSource
- MedicationStatement.derivedFrom
- MedicationStatement.reasonNotTaken
- MedicationStatement.reasonReference

***

## Observation

The following elements are present in GP Connect, but not used in the PCDS: 

- Observation.basedOn
- Observation.status
- Observation.category
- Observation.context
- Observation.issued
- Observation.dataAbsentReason
- Observation.method
- Observation.specimen
- Observation.device
- Observation.referenceRange
- Observation.related
- Observation.component

***

## Organization
|Element Name|Description|PCDS Cardinality|GPC Cardinality|
|-
|GP practice identifier|The identifier of the registered GP practice.|1...1|0...1|
***

The following elements are present in GP Connect, but not used in the PCDS: 

- Organization.active		
- Organization.type		
- Organization.alias		
- Organization.partOf		
- Organization.contact		
- Organization.endpoint	

***
