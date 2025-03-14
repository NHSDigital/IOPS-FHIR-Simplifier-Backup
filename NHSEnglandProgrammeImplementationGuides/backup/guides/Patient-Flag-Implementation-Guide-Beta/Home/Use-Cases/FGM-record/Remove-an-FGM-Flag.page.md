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

#### Flag endpoint delete

The patient and code parameters should be supplied to ensure the FGM flag for the patient is deleted and a reason for the flag deletion should be provided using a "reason" parameter.
```
DELETE [baseURL]/PatientFlag/?patient=[NHSNumber]&code=FGM&reason=[ReasonText]
```

##### Remove entire FGM record

To delete a FGM flag for a patient with NHS Number 9787576543 beacuse the flag is no longer needed
```
DELETE [baseURL]/PatientFlag/?patient=9787576543&code=FGM&reason=NoLongerRequired
```

# THIS IS WRONG

#### Example

* {{pagelink:RemoveFGMRecord-Bundle-Example}}

---
