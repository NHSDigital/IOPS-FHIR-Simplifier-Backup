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


#### Example

* {{pagelink:RemoveFGMRecord-Bundle-Example}}

---
