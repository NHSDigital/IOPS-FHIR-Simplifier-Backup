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

## Patient
|Element Name|Description|PCDS Cardinality|GPC Cardinality|
|-
|Person first name|The first name(s) of the person. This includes middle names.|1...*|0...*|
|Person family name|The family name or surname of the person.|1...*|1...1|
|Title|Person's title|0..1|0...*|
|Date of birth|The date of birth of the person|1...1|0...1|
|Language|Patient's preferred language|1...1|0...*|
|Address line 1|Persons's first line of address|1...1|0...*|
|Relationship|The relationship the personal contact has to the person, e.g. father, grandmother, family friend etc.|0...1|0...*|
|Immigration Status|Details of the immigration status of the person|0...1|N/A|
|Start Date|Start date of immigration status|0...1|N/A|
|End Date|End date of immigration status|0...1|N/A|
|Comment|Relevant comments about the person's immigration status|0...1|N/A|
|Registration Period|The period of time during which the patient registration applies|1...1|0...1|
|Registration Type|The type of patient registration at the healthcare organization|1...1|0...1|
|Registration Status|The registration status for this patient at the healthcare organisation|1...1|0...1|
|content|content|content|content|

***