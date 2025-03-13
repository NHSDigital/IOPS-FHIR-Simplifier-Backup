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

This is be done by POSTing a Flag resource to the PatientFlag endpoint.

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

The body of the POST request is a transaction bundle made up of the PatientFlag resource.

**Note**: Only one PatientFlag resource can exist per patient, per type of flag. If a patient flag is POSTed for a patient that already has that flag type, the records are merged using the following logic:

- notes from any identical resources are added to the same resource in the existing resource
- confirmation details that the PatientFlag is create are returned to the sender

```
POST [baseURL]/PatientFlag
```

---
