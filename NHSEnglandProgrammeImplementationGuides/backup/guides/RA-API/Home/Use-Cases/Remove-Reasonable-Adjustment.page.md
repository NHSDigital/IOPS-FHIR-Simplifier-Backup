## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.

#### UseCase

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Remove Reasonable Adjustment" as rem <<abstract>>
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

In the following sequence diagram, a patient and/or practitioner decide to remove an individual reasonable adjustment. The relevant England-Flag-PatientFlag-Adjustment resource is removed.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Additional Detail\n(Adjustment)"  as add

  pat ->  pra : Remove
  pra ->  api : Remove
  api ->  add : Remove resourc
  
  api ->  add : Remove resource (any)
  add ->  add : Validate
  api <-- add : return
  alt Validation failed
    api -> api : rollback
  end

pra <-- api : OperationOutcome

@enduml
</plantuml>

The following resource types will be deleted from the record:

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}}  

#### Example

Multiple resources can be deleted using a transaction bundle.  This {{pagelink:Home/Examples/RemoveRARecord-Bundle-Example.page.md}} demonstates deleting the following resources

* {{pagelink:Home/Examples/PatientFlag-AlanMann-Example.page.md}} example.  
* {{pagelink:Home/Examples/RA-Flag-Example.page.md}} example.  
* {{pagelink:Home/Examples/RA-Condition-Example.page.md}} example.  

