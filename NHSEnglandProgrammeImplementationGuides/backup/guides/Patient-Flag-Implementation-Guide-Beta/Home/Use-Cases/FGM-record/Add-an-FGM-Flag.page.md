## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.

As only one flag of each flag type should exist for each patient, prior to creating the FGM flag, the patient's flags should be retrieved to check for an existing flag.
```
GET [baseURL]/PatientFlag?patient=[NHSNumber]
```

**Note**: Only one patient flag can exist per patient / type of flag. If a patient flag is posted for a patient that already has the flag, the records are merged using the following logic:

- any additional resources from the second post are added to the existing flag
- notes from any identical resources are added to the same resource in the existing flag


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

FGM records are created by POSTing the resource, conformant to {{pagelink: Home/fhir-assets/profiles/england-flag-patient-flag.page.md}} to the /PatientFlag endpoint. 

```
POST [baseURL]/PatientFlag
[Transaction Bundle that containing the FGM Flag]
```

### Examples

* {{pagelink:AddFGMRecordTransaction-Bundle-Example}}

---