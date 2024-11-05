## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.
 

### Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record
usecase "Remove FGM Flag record" as rem
}


actor Patient as pat

usecase "Consult" as consult

pat -- consult
pra -- consult
pra -- record
record <.. rem : include

@enduml
</plantuml>

### System Interactions

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
participant  "FHIR API"         as api
entity       "Patient Flag"     as pfg

  pat ->  pra : Remove
  pra ->  api : Remove
  api ->  pfg : Remove resourc
  pra <-- api : OperationOutcome

@enduml
</plantuml>

### Queries

Using [FHIR conditional delete](http://hl7.org/fhir/r4/http.html#3.1.0.7.1) capabilities, it is possible to delete the entire FGM Flag record for a given patient.

#### Flag endpoint write

Following the standard FHIR conditional delete ReST pattern `DELETE [baseURL]/[resourceType]` for delete operations, to:

##### Remove entire FGM record

Use `DELETE [baseURL]/Flag?[searchParameters]`
Include searchParameters:
- 'patient' - [patientNHSNumber]
- 'code' - [patientFlagCode]
Provide a Removal reason string as header: `x-removal: [removalReason]`
  

e.g. `DELETE [baseURL]/Flag?patient=9449306753&code=female-genital-mutilation-flag`


The following resource types will be deleted from the record: 

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}  

This query relies on the [Flag patient](http://www.hl7.org/fhir/R4/flag.html#search) and {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}} search parameters.


#### Example

* {{pagelink:RemoveFGMRecord-Bundle-Example}}

---
