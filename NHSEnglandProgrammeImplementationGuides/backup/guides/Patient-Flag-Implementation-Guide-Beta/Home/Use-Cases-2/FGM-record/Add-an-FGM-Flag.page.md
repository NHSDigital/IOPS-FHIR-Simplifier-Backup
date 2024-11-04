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
usecase "Add FGM Flag record" as add
}


actor Patient as pat

usecase "Consult" as consult

pat -- consult
pra -- consult
pra -- record
record <.. add : include

@enduml
</plantuml>

### System Interactions

The practitioner decides to record a 

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Patient Flag"     as flg

pra ->  pat : Consult patient
pra ->  api : Record FGM Flag record
api ->  flg : Create resource
flg ->  flg : Validate
api <-- flg : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>

### Queries

Using [FHIR create](http://hl7.org/fhir/r4/http.html#create) capabilities, it is possible to create/write the FGM Patient Flag record.

#### Flag endpoint write

FGM records are created by POSTing the resource, conformant to {{pagelink: Home/fhir-assets/profiles/england-flag-patient-flag.page.md}} to the relevant /Flag resource type endpoint. 

```
POST [baseURL]/Flag
```


### Examples

* {{pagelink:AddFGMRecordTransaction-Bundle-Example}}

---