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

This could be done with individual calls to the required endpoints, or can be done in a single transaction Bundle.  A transaction Bundle can help with data integrity requirements and also help to reduce required http calls.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Patient Flag"     as flg
entity       "Additional Detail"  as add

pra ->  pat : Consult patient
pra ->  api : Record adjustment record (transaction Bundle)

api ->  flg : Create/update resource
flg ->  flg : Validate
api <-- flg : return
alt Validation failed
  api -> api : rollback
end

loop for each Additional Detail resource
  api ->  add : Create/update resource (any)
  add ->  add : Validate
  api <-- add : return
  alt Validation failed
    api -> api : rollback
  end
end
pra <-- api : OperationOutcome

@enduml
</plantuml>

### Examples

* {{pagelink:PatientFlag-AlanMann-Example}}

The following set of examples constitute the individual associated resources with the initial addition of a flag for Reasonable Adjustment.  This include a patient Flag resource, the adjustment Flag resource and the associated Condition resource.  All resources have contained provenances.

A transaction Bundle is also given that allows these resources (plus the patient) to be entered in an atomic traction.  It uses PUTs, where in the case of an initial update, it may be done as a [conditional update](https://www.hl7.org/fhir/http.html#cond-update)

* {{pagelink:PatientFlag-AlanMann-Example}}
* {{pagelink:RA-Flag-Example}}
* {{pagelink:RA-Condition-Example}}
* {{pagelink:AddRARecordTransaction-Bundle-Example}}

The following set of examples are for the same patient, and constitute an addition flag and condition.  The transaction Bundle here illustrates an idempotent update by simply adding the new resources to the first transaction Bundle.

* {{pagelink:Home/Examples/RA-Flag2-Example.page.md}}
* {{pagelink:RA-Condition2-Example}}
* {{pagelink:Home/Examples/UpdateRARecordTransaction-Bundle-Example.page.md}}



---
