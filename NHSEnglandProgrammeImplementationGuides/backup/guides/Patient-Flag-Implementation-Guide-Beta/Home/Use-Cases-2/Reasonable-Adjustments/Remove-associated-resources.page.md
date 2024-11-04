## {{page-title}}


### Overview

For high level requirements, see {{pagelink:Home}}.


### Remove Use Cases

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag (Reasonable Adjustments)"{
actor Practitioner as pra
usecase "Record" as record
usecase "Remove Adjustment" as remadj
usecase "Remove Impairment" as remimp
usecase "Remove Underlying Condition" as remcond
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
record <.. remadj : include
record <.. remimp : include
record <.. remcond : include

@enduml
</plantuml>

### System Interactions

The practitioner decides to remove additional detail supporting or enriching the Reasonable Adjustment Flag record

This could be done with individual calls to the required endpoints, or can be done in a single transaction Bundle.  A transaction Bundle can help with data integrity requirements and also help to reduce required http calls.

#### Remove Adjustment

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
actor        "Patient"          as pat
participant  "FHIR API"         as api
entity       "Adjustment Flag"  as adj

pra ->  pat : Examine patient
pra ->  pat : Suggest adjustments
pra ->  api : Record adjustment record

api ->  adj : Delete resource
adj ->  adj : Validate
api <-- adj : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>

#### Remove Impairment/Underlying Condition

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
actor        "Patient"          as pat
participant  "FHIR API"         as api
entity       "Condition"        as cod

pra ->  pat : Examine patient
pra ->  pat : Suggest adjustments
pra ->  api : Record adjustment record

api ->  cod : Delete resource
cod ->  cod : Validate
api <-- cod : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>



### Queries

Using [FHIR delete](http://hl7.org/fhir/r4/http.html#delete) capabilities, it is possible to delete the Additional Detail resource, removing it from the Patient Flag record.

#### Flag endpoint write

Following the standard ReST pattern `DELETE [baseURL]/[resourceType]` for create operations, to:

##### Remove Adjustment

  Use `DELETE [baseURL]/Flag/[FlagID]` 
  Provide a Removal reason string as header: `x-removal: [removalReason]`
  
##### Remove Impairment/Underlying Condition

  Use `DELETE [baseURL]/Condition/[FlagID]` 
  Provide a Removal reason string as header: `x-removal: [removalReason]`

---