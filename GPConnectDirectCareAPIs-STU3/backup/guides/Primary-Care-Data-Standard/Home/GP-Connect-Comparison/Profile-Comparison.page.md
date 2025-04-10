## {{page-title}}

<p>This page outlines the differences in cardinality between data elements in the PCDS, and the same elements in GP Connect FHIR Profiles. Any data elements that exist and both, and are not listed below, have the same cardinality.
The changes all fall into, at least one of and potentially a combination of, the below categories for each element: 

- PCDS accepts more than one entry 
- PCDS accepts only one entry
- PCDS accepts at least one entry

There are cases where the PCDS does not use some elements within certain GP Connect profiles, where this is the case it has been listed below. </p> 

***

## Patient (Profile Name)
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

## Profile Name
|header|header|header|header|
|-
|content|content|content|content|