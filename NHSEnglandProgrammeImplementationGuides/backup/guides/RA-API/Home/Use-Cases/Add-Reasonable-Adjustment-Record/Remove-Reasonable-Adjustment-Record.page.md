## {{page-title}}
### Overview

A patient and/or practitioner decide to remove the reasonable adjustment record.

For high level requirements, see {{pagelink:Home}}.
 

### Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record
usecase "Remove Reasonable Adjustment record" as add
}


package "Patient or Proxy" {
  actor Patient as pat
  actor "Patient Advocate" as pad
}

usecase "Consult" as consult

pat -- consult
pra -- consult
pad -- consult
pra -- record
record <.. add : include

@enduml
</plantuml>

### System Interactions

In the following sequence diagram, a patient and/or practitioner decide to remove the reasonable adjustment record. All adjustment records are deleted.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
actor        "Patient"          as pat
participant  "FHIR API"         as api
entity       "Patient Flag"     as pfg
entity       "Adjustment Flag"  as adj
entity       "Condition"        as cod

  pra ->  pat : Consult

  alt Validation passed
    api ->  pfg : Delete adjustment patient flag
    api ->  adj : Delete adjustment flag(s)
    api ->  cod : Delete condition flag(s)
    pra <-- api : OperationOutcome
  else Validation failed
    api -> api : rollback
    pra <-- api : OperationOutcome
  end

@enduml
</plantuml>

The following resource types will be deleted from the record:

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}}
* {{pagelink:Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}}

#### Example

Multiple resources can be deleted using a transaction bundle.  This {{pagelink:Home/Examples/RemoveRARecord-Bundle-Example.page.md}} demonstrates deleting the following resources

* {{pagelink:Home/Examples/PatientFlag-AlanMann-Example.page.md}} example.  
* {{pagelink:Home/Examples/RA-Flag-Example.page.md}} example.  
* {{pagelink:Home/Examples/RA-Condition-Example.page.md}} example.  

---
