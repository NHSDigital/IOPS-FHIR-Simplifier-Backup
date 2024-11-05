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
usecase "Record" as record <<abstract>>
usecase "Add Patient Flag record" as add <<abstract>>
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

The practitioner decides to record patient flag information.

This could be done by POSTing the PatientFlag resource to the Flag endpoint

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Patient Flag"     as flg

pra ->  pat : Consult patient
pra ->  api : Record adjustment record

api ->  flg : Create/update resource
flg ->  flg : Validate
api <-- flg : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>


### Queries

Using [FHIR create](http://hl7.org/fhir/r4/http.html#create) capabilities, it is possible to create/write the Patient Flag record.

#### Flag endpoint write

As an abstract PatientFlag, PatientFlag records are created by POSTing the resource to the relevant resource type endpoint. 

```
POST [baseURL]/Flag
```



---
