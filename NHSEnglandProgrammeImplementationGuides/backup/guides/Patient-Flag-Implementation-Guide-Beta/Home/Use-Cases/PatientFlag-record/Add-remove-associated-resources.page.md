## {{page-title}}


### Overview

For high level requirements, see {{pagelink:Home}}.
 
### Add Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Add Additional Detail" as add <<abstract>>
}


actor Patient as pat

usecase "Consult" as consult <<abstract>>

pat -- consult
pra -- consult
pra -- record
record <.. add : include

@enduml
</plantuml>

### System Interactions

The practitioner decides to record Additional Detail to support or enrich the Patient Flag record

This could be done with individual calls to the required endpoints, or can be done in a single transaction Bundle.  A transaction Bundle can help with data integrity requirements and also help to reduce required http calls.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Additional Detail"  as add

pra ->  pat : Consult patient
pra ->  api : Record adjustment record (transaction Bundle)

api ->  add : Create/update resource
add ->  add : Validate
api <-- add : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>


### Queries

Using [FHIR create](http://hl7.org/fhir/r4/http.html#create) capabilities, it is possible to create/write the Additional Detail resource, adding it to the Patient Flag record.

#### Flag endpoint write

As an abstract PatientFlag, PatientFlag records are created by POSTing the resource to the relevant resource type endpoint. ResourceType will depend on modelling of the Additional Detail as a suitable resource within a given concrete implementation. e.g. Reasonable Adjustments uses Additional Detail resources, modelling Adjustments as[EnglandFlagPatientFlagAdjustment](https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag-Adjustment) resources ,and Impairments and Underlying Conditions as [EnglandConditionFlag](https://fhir.nhs.uk/England/StructureDefinition/England-Condition-Flag) resources.

```
POST [baseURL]/[resourceType]
```



---

---


### Remove Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Remove Additional Detail" as rem <<abstract>>
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

In the following sequence diagram, a patient and/or practitioner decide to remove the patient flag.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
participant  "FHIR API"         as api
entity       "Patient Flag"     as pfg
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

The following resource types will be deleted from the record: 

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}  
* any resources detailing supporting information

#### Example

Multiple resources can be deleted using a transaction bundle.  This  {{pagelink:Home/Examples/RemoveRARecord-Bundle-Example.page.md}}:

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} example.  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}} example.  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}} example.  

---
