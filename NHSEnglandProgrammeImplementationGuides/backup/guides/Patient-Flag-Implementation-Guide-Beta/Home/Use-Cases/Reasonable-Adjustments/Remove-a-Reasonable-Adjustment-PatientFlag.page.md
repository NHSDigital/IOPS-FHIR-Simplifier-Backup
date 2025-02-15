## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.
 

### Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag (Reasonable Adjustments)"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Remove Reasonable Adjustment record" as rem <<abstract>>
}


actor Patient as pat

usecase "Consult" as consult <<abstract>>

pat -- consult
pra -- consult
pra -- record
record <.. rem : include

@enduml
</plantuml>

### System Interactions

In the following sequence diagram, a patient and/or practitioner decide to remove the Reasonable Adjustment patient flag and all suppporting resources (either Adjustments, Impairments or Underlying Conditions).

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"            as pat
actor        "Practitioner"       as pra
participant  "FHIR API"           as api
entity       "Patient Flag"       as pfg
entity       "Additional Detail"  as add

  pat ->  pra : Remove
  pra ->  api : Remove
  api ->  pfg : Remove resource
  

loop for each Additional Detail resource
  api ->  add : Remove resource (any)
  add ->  add : Validate
  api <-- add : return
  alt Validation failed
    api -> api : rollback
  end
end

pra <-- api : OperationOutcome

@enduml
</plantuml>


### Queries

Using [FHIR conditional delete](http://hl7.org/fhir/r4/http.html#3.1.0.7.1) capabilities, it is possible to delete the entire Reasonable Adjustment Flag record for a given patient.

#### Flag endpoint write

Following the standard FHIR conditional delete ReST pattern `DELETE [baseURL]/[resourceType]` for delete operations, to:

##### Remove entire Reasonable Adjustment record

Use `DELETE [baseURL]/Flag?[searchParameters]`
Include searchParameters:
- 'patient' - [patientNHSNumber]
- 'code' - [patientFlagCode]
Provide a Removal reason string as header: `x-removal: [removalReason]`
  
---
The following resource types will be deleted from the record: 

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}  
* any resources detailing supporting Reasonable Adjustment information:
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}} 
* {{pagelink:Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}} 

This query relies on the [Flag patient](http://www.hl7.org/fhir/R4/flag.html#search) and {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}} search parameters.

#### Example

Multiple resources can be deleted using a transaction bundle.  This  {{pagelink:Home/Examples/RemoveRARecord-Bundle-Example.page.md}}:

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} example.  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}} example.  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}} example.  

---

