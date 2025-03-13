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

The practitioner decides to record patient flag information that has associated resources.

This is done in a single transaction Bundle.  A transaction Bundle helps with data integrity and also helps to reduce required http calls.

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


### Queries

Using [FHIR create](http://hl7.org/fhir/r4/http.html#create) capabilities, it is possible to create/write the Patient Flag record.

The body of the POST request is a transaction bundle made up of the PatientFlag resource, and any other accepted FHIR resources to support that flag

**Note**: Only one PatientFlag resource can exist per patient, per type of flag. If a patient flag is POSTed for a patient that already has that flag type, the records are merged using the following logic:
- any additional resources from the second post are added to the existing flag
- notes from any identical resources are added to the same resource in the existing resource
- confirmation details that the PatientFlag is create are returned to the sender


# ##NEEDS LOOKING AT###

### Examples

* {{pagelink:PatientFlag-AlanMann-Example}}

The following set of examples constitute the individual associated resources with the initial addition of a flag for Reasonable Adjustment.  This includes a PatientFlag resource, the adjustment Flag resource and the associated Condition resource.  All resources have contained provenances.

* {{pagelink:PatientFlag-AlanMann-Example}}
* {{pagelink:RA-Flag-Example}}
* {{pagelink:RA-Condition-Example}}
* {{pagelink:AddRARecordTransaction-Bundle-Example}}

The following set of examples are for the same patient, and constitute an addition adjustment Flag and Condition.  The transaction Bundle here illustrates an idempotent update by simply adding the new resources to the first transaction Bundle.

* {{pagelink:Home/Examples/RA-Flag2-Example.page.md}}
* {{pagelink:RA-Condition2-Example}}
* {{pagelink:Home/Examples/UpdateRARecordTransaction-Bundle-Example.page.md}}



---
