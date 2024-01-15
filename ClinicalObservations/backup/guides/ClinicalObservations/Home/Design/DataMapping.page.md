---
parent: 
---
## Data Mapping


<a href="#P0">Patient data mapping</a><br/>
<a href="#P1">Organization data mapping</a><br/>
<a href="#P2">Practitioner data mapping</a><br/>
<a href="#P3">PractitionerRole data mapping</a><br/>
<a href="#P4">Consciousness observation data mapping</a><br/>
<a href="#P5">Inspired Oxygen observation data mapping</a><br/>
<a href="#P6">Oxygen saturation observation data mapping</a><br/> 
<a href="#P7">Pulse rate observation data mapping</a><br/>
<a href="#P8">Respiration rate observation data mapping</a><br/>
<a href="#P9">Systolic pressure observation data mapping</a><br/>
<a href="#P10">Temperature observation data mapping</a><br/>
<a href="#P11">Early Warning Score Type data mapping</a><br/>
<a href="#P12">Early Warning Sub Score Type data mapping</a><br/>

<h2 id="P0">Patient data mapping</h2>

**Profile**: {{pagelink:Patient}}

| Source Data item  | Cardinality |Target FHIR Element  | Notes|     
|--|--|
|Patient Unique ID|1..1|Patient.identfier.value.value||
|Name|1..*|Patient.name||																	
|Family Name|1..1|Patient.name.family.value||	
|Given Name|1..1|Patient.name.given.value||	
|Prefix (Name)|0..1|Patient.name.prefix.value||	
|Gender|0..1|Patient.gender.value||	
|Birthdate|1..1|Patient.birthDate.value||
|Address|0..1|||									
|Address type|0.1|Patient.address.use.value||	
|Line|0.*|Patient.address.line.value|	
|City|0.*|Patient.address.city.value|	
|District|0.1|Patient.address.district.value||	
|Postcode|0.1|Patient.address.postalcode.value||	
|Marital Status|0..1|Patient.address.maritalStatus.coding.code||	

<h2 id="P1">Organization data mapping</h2>
This is the organization which is the performer of the observations.

**Profile**: {{pagelink:Organization}}

| Source Data item  | Cardinality |Target FHIR Element  | Notes|     
|--|--|
|Unique Identifier|1..1|Organization.identifer.value||
|Organization Name|0..1|Organization.name.value||
|Telecom|0..1|Organization.telecom.value||
|Telecom type|0..1|Organization.system.value||
|Address|0..1|Organization.address||
|Line1|0..*|Organization.address.line.value||
|City|0..1|Organization.address.city.value||
|Postcode|0..1|Organization.address.postalCore.value||

<h2 id="P2">Practitioner data mapping</h2>
The person who performed the observations.

**Profile**: {{pagelink:Practitioner}}

| Source Data item  | Cardinality |Target FHIR Element  | Notes|     
|--|--|
|Unique ID of person|1..1|Practitioner.identifier.value|| 
|Name|0..1|Practitioner.name||
|Family Name|0..1|Practitioner.name.family.value||
|Given Name|0..1|Practitioner.name.given.value||
|Prefix (Name)|0..1|Practitioner.prefix.value||
|Telephone|0..1|Practitioner.telecom.value.value||
|Telecom type|0..1|Practitioner.telecom.system.value||
|Gender|0..1|Practitioner.gender.value||

<h2 id="P3">PractitionerRole data mapping</h2>

**Profile**: {{pagelink:PractitionerRole}}

| Source Data item  | Cardinality |Target FHIR Element  | Notes|     
|--|--|
|Unique role ID of person|1..1|PractitionerRole.identifier.value|| 
|Role Name|0..1|PractitionerRole.code.value||


<h2 id="P4">Consciousness observation data mapping</h2>

**Profile**: {{pagelink:VitalSignsObservation}}

The table below shows how Consciousness observations are mapped to the Observation resource.

| Source Data item  | Cardinality |Target FHIR Element  | Notes|    
|-
|Identifier|1..1|Observation.identifier.value	|A unique identifier assigned to this observation (such as a generated Universally Unique Identifier {UUID})|	
|Code|1..1|Observation.code.coding.code.value||
|Patient|1..1|Observation.subject||
|Time & date of observation|1..1|Observation.effectiveDateTime.value|	The date and time that the Consciousness assessment was made	|
|Practitioner|1..1|Observation.performer|	A link to the performer who carried out this observation. This must be a qualified practitioner and associated organisation	|
|Result|1..1|Observation.valueCodeableConcept.code.value|	The Consciousness assessment outcome as a coded value|
|Additional notes	|0..1|Observation.note|Any additional notes or actions that the performer wishes to convey|
|Related observation	|0..*|Observation.derivedFrom|Reference(Observation)	Related resource that belongs to the Observation group|
|Derivation	|0..*|Observation.derivedFrom| |
|Component|0..*|Observation.component| |	


<h2 id="P5">Inspired Oxygen data mapping</h2>

The table below shows how Inspired Oxygen observations are mapped to the Observation resource.

**Profile**: {{pagelink:VitalSignsObservation}}

|Source data item|Cardinality|Target FHIR Element|Guidance|
|-
|Identifier|1..1|Observation.identifier.value|A unique identifier assigned to this observation (such as a generated Universally Unique Identifier {UUID})	|
|Code	|1..1|Observation.code.coding.code.value||
|Patient|1..1|Observation.subject|	A link to the Patient	|
|Time & date of observation |1..1|Observation.effectiveDateTime.value|The date and time that the inspired oxygen reading was taken|
|Practitioner|0..1|Observation.performer|	A link to the performer who carried out this observation. This must be a qualified practitioner and associated organization	|
|Result|1..1|Observation.value|Observation outcome|
|Additional notes	|0..1|Observation.note|Any additional notes or actions that the performer wishes to convey|
|Related observation	|0..*|Observation.derivedFrom|Reference(Observation)	Related resource that belongs to the Observation group|
|Derivation	|0..*|Observation.derivedFrom| |
|Component|0..*|Observation.component| |


<h2 id="P6">Oxygen saturation data mapping</h2>

The table below shows how the Oxygen satuation observations are mapped to the Observation profile.

**Profile**: {{pagelink:VitalSignsObservation}}

|Source data item|Cardinality|Target FHIR Element|Guidance|
|-
|Identifier|1..1|Observation.identifier.value|	A unique identifier assigned to this observation (such as a generated Universally Unique Identifier {UUID})|
|Code	|1..1|Observation.code.coding.code.value||
|Patient|1..1|Observation.subject|	A link to the Patient|
|Time & date of observation|1..1|Observation.effectiveDateTime.value|	The date and time that the oxygen saturation was taken|
|Practitioner|0..1|Observation.performer|	A link to the performer who carried out this observation. This must be a qualified practitioner and associated organization|
|Result	|1..1|Observation.valueQuantity|The actual oxygen saturation reading |
|note|0..1|observation.note|	Any additional notes or actions that the performer wishes to convey|

<h2 id="P7">Pulse rate data mapping</h2>

The table below shows how the Pulse rate observations are mapped to the Observation profile.

**Profile**: {{pagelink:VitalSignsObservation}}

|Source data item|Cardinality|Target FHIR Element|Guidance|
|-
|Identifier|1..1|Observation.identifier.value|	A unique identifier assigned to this observation (such as a generated Universally Unique Identifier {UUID})|
|Code	|1..1|Observation.code.coding.code.value|
|Patient|1..1|Observation.subject|	A link to the Patient|
|Time & date of observation|1..1|Observation.effectiveDateTime.value|	The date and time that the pulse rate was taken|
|Practitioner	|1..1|Observation.performer|A link to the performer who carried out this observation. This must be a qualified practitioner and associated organisation|
|Result|1..1|Observation.valueQuantity|	The actual pulse rate reading |
|Notes	|0..1|Observation.note|Any additional notes or actions that the performer wishes to convey|

<h2 id="P8">Respiration rate data mapping</h2>

The table below shows how the respiration rate observations are mapped to the FHIR Observation profile.

**Profile**: {{pagelink:VitalSignsObservation}}

|FHIR Element|Cardinality|FHIR Target|Guidance|
|-
|identifier|1..1|Observation.identifier.value|	A unique identifier assigned to this observation (such as a generated Universally Unique Identifier {UUID})|
|code	|1..1|Observation.code.coding.code.value|
|patient|1..1|Observation.subject|	A link to the Patient|
|effective|1..1|Observation.effectiveDateTime.value|	The date and time that the pulse rate was taken|
|performer|1..1|Observation.performer|	A link to the performer who carried out this observation. This must be a qualified practitioner and associated organisation|
|Result|1..1|Observation.valueQuantity|	The actual pulse rate reading|
|note	|0..1|Observation.note|Any additional notes or actions that the performer wishes to convey|

<h2 id="P9">Systolic pressure data mapping</h2>

The table below shows how the Systolic pressure observations are mapped to the Observation profile.

**Profile**: {{pagelink:VitalSignsObservation}}

|FHIR Element|Cardinality|FHIR Target|Guidance|
|-
|identifier|1..1|Observation.identifier.value|	A unique identifier assigned to this observation (such as a generated Universally Unique Identifier {UUID})|
|code	|1..1|Observation.code.coding.code.value|
|patient|1..1|Observation.subject|	A link to the Patient|
|effective	|1..1|Observation.effectiveDateTime.value|The date and time that the blood pressure was taken|
|performer|1..1|Observation.performer|	A link to the performer who carried out this observation. This must be a qualified practitioner and associated organization|
|note	|0..1|Observation.note|Any additional notes or actions that the performer wishes to convey|
|bodySite	|0..1|Observation.bodysite|
|systolic value|0..1|Observation.component.value|
|diastolic value|0..1|Observation.component.value|

<h2 id="P10">Temperature data mapping</h2>

The table below shows how the body temperature observations are mapped to the Observation profile.

**Profile**: {{pagelink:VitalSignsObservation}}

|FHIR Element|Cardinality|FHIR Target|Guidance|
|-
|identifier|1..1|Observation.identifier.value|	A unique identifier assigned to this observation (such as a generated Universally Unique Identifier {UUID})|
|code	|1..1|Observation.code.coding.code.value|
|patient|1..1|Observation.subject|	A link to the Patient|
|effective	|1..1|Observation.effectiveDateTime.value|The date and time that the body temperature was taken|
|performer	|1..1|Observation.performer|A link to the performer who carried out this observation. This must be a qualified practitioner and associated organisation|
|value	|1..1|Observation.valueQuantity|The actual body temperature reading|
|note|0..1|	Observation.note|Any additional notes or actions that the performer wishes to convey|

<h2 id="P11">Early Warning Score Type data mapping</a><br/></h2

**Profile**: {{pagelink:Observation}}

|FHIR Element|Cardinality|FHIR Target|Guidance|
|-
|identifier|1..1|Observation.identifier.value|	A unique identifier assigned to this early warning score (such as a generated Universally Unique Identifier {UUID})|
|early warning score type	|1..1|Observation.code.coding.code.value|
|patient|1..1|Observation.subject|	A link to the Patient|
|effective	|1..1|Observation.effectiveDateTime.value|The date and time that the score was created|

<h2 id="P12">Early Warning Sub-Score Type data mapping</a><br/></h2

**Profile**: {{pagelink:Observation}}

|FHIR Element|Cardinality|FHIR Target|Guidance|
|-
|early warning sub score type	|1..1|Observation.code.coding.code.value|



