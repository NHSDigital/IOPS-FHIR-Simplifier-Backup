## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.

### Usecase
After obtaining consent from a patient, a Reasonable Adjustment Record may be created.  This consists of a Flag resource containing an adjustment and a Condition resource may also optionally be created to record the details of an impairment.  

If a Reasonable Adjustment Record exists, a Flag resource designated as the patient flag must be created to indicate that there are reasonable adjustments recorded for the patient.  There is a single instance of this type of resource per patient.

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record
usecase "Add Reasonable Adjustment record" as add
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

The practioner decides to record a condition with the patients consent.  This could be done with individual calls to the required endpoints, or can be done in a single transaction Bundle.  A transaction Bundle can help with data integrity requirements and also help to reduce required http calls.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
actor        "Patient"          as pat
participant  "FHIR API"         as api
entity       "Patient Flag"     as flg
entity       "Adjustment Flag"  as adj
entity       "Condition"        as cod

pra ->  pat : Examine patient
pra ->  pat : Suggest adjustments
pra ->  api : Record adjustment record (transaction Bundle)

alt Validation failed
  api -> api : rollback
end

api ->  flg : Create/update resource
flg ->  flg : Validate
api <-- flg : return
alt Validation failed
  api -> api : rollback
end

api ->  adj : Create/update resource
adj ->  adj : Validate
api <-- adj : return
alt Validation failed
  api -> api : rollback
end

alt Condition also to be recorded
api ->  cod : Create/update resource
cod ->  cod : Validate
api <-- cod : return
alt Validation failed
  api -> api : rollback
end
pra <-- api : OperationOutcome

@enduml
</plantuml>

### Examples

* [Patient example](Patient-PatientExample1.html)

The following set of examples constitute the individual associated resources with the intial addition of a flag for Reasonable Adjustment.  This includes a patient Flag resource, the adjustment Flag resource and the associated Condition resource.  All resources have contained provenances.

A transaction Bundle is also given that allows these resources (plus the patient) to be entered in an atomic traction.  It uses PUTs, where in the case of an intial update, it may be done as a [conditional update](https://www.hl7.org/fhir/http.html#cond-update)

* {{pagelink:Home/Examples/RA-PatientFlag-Example.page.md}}
* {{pagelink:Home/Examples/RA-Flag-Example.page.md}}
* {{pagelink:Home/Examples/RA-Condition-Example.page.md}}
* {{pagelink:Home/Examples/AddRARecordTransaction-Bundle-Example.page.md}}

The following set of examples are for the same patient, and constitute an addition flag and condition.  The transaction Bundle here illustates an idempotent update by simply adding the new resources to the first transaction Bundle.

* {{pagelink:Home/Examples/RA-Flag2-Example.page.md}}
* {{pagelink:Home/Examples/RA-Condition2-Example.page.md}}
* {{pagelink:Home/Examples/UpdateRARecordTransaction-Bundle-Example.page.md}}

