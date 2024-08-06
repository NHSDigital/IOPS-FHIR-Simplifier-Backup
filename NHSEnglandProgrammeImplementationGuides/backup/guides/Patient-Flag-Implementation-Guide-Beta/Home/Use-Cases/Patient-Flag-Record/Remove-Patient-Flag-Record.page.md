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
usecase "Remove Patient Flag record" as rem <<abstract>>
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
