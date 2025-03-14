## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.

### Use Case

After consultation with a patient, a Reasonable Adjustment Record may be created.  This consists of a Flag resource containing an adjustment; a Condition resource or resources may also optionally be created to record the details of an impairment or an underlying condition.  

Multiple Reasonable Adjustments may be created at the same time. This would consist of
- PatientFlag resource (1 single resource)
- underlying conditions (any number of resources)
- impairments (any number of resources)
- adjustments (any number of resources)

A query should be performed prior to Flag creation to determine if there is already a reasonable adjustment PatientFlag for the patient

```
GET [baseURL]/PatientFlag?patient=[NHSNumber]&code=NRAF

```
If no Reasonable Adjustment flag is not returned, a new PatientFlag and Reasonable Adjustment record is created. If a Reasonable Adjustment flag is returned, new adjustments may be added to the existing PatientFlag.

**Note**: If a patient flag is POSTed for a patient that already has the flag, the records are merged using the following logic:

- any additional resources from the second post are added to the existing flag
- notes from any identical resources are added to the same resource in the existing flag


<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag (Reasonable Adjustments)"{
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

The practitioner decides to record a Reasonable Adjustment Flag, an Adjustment, and associated condition.  This could be done with individual calls to the required endpoints (see "Adding associated resources" below), or can be done in a single transaction Bundle.  A transaction Bundle can help with data integrity requirements and also help to reduce required http calls.

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

The following set of examples constitute the individual associated resources with the initial addition of a flag for Reasonable Adjustment.  This includes a patient Flag resource, the adjustment Flag resource and the associated Condition resource.  All resources have contained provenances.

A transaction Bundle POSTed to the /PatientFlag endpoint containing all the resources necessary to create the Reasonable Adjustment record

```
POST [baseURL]/PatientFlag
[Transaction Bundle that contains the Reasonable Adjustment resources]

```

* {{pagelink:Home/Examples/AddRARecordTransaction-Bundle-Example.page.md}}


# DO WE NEED THESE ??

The following set of examples are for the same patient, and constitute an addition flag and condition.  The transaction Bundle here illustrates an idempotent update by simply adding the new resources to the first transaction Bundle.

* {{pagelink:Home/Examples/RA-Flag2-Example.page.md}}
* {{pagelink:Home/Examples/RA-Condition2-Example.page.md}}
* {{pagelink:Home/Examples/UpdateRARecordTransaction-Bundle-Example.page.md}}

---
