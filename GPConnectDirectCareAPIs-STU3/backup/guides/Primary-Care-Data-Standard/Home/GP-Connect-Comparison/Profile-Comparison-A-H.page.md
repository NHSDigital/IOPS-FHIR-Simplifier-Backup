## {{page-title}}

## Allergy Intolerance
The following elements are present in GP Connect, but not used in the PCDS:

- AllergyIntolerance.onset
- AllergyIntolerance.recorder
- AllergyIntolerance.asserter
- AllergyIntolerance.lastOccurrence

***

## Composition
The following elements are present in GP Connect, but not used in the PCDS:

- Composition.status
- Composition.type
- Composition.class
- Composition.subject
- Composition.encounter
- Composition.date

***

## Condition
|Element Name|Description|PCDS Cardinality|GPC Cardinality|
|-
|Coded value|The coded value for the problem list.|0...1|1...1|

***

The following elements are present in GP Connect, but not used in the PCDS:

- Condition.clinicalStatus
- Condition.verificationStatus
- Condition.category
- Condition.severity
- Condition.evidence
- Condition.context

***

## Diagnostic Report

|Element Name|Description|PCDS Cardinality|GPC Cardinality|
|-
|Name/Code|Name/Code for this diagnostic report|1...*|1...1|

***

## Document Reference
|Element Name|Description|PCDS Cardinality|GPC Cardinality|
|-
|Confidentiality|The code specifying the level of confidentiality of the document.|0...1|0...*|
|Document Name|The name of the document.|0...1|N/A
Document relates to|Relationships that this document has with other document references that already exist.|0...1|0...*|

***

The following elements are present in GP Connect, but not used in the PCDS: 

- DocumentReference.docStatus
- DocumentReference.indexed

***

## Encounter
The following elements are present in GP Connect, but not used in the PCDS:

- Encounter.length

***
