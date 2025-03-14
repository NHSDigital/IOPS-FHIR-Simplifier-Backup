## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.

### Use Case

After consultation with a patient, a Reasonable Adjustment Record may be created.  Normally a Reasonable Adjustment consists of a Flag resource containing an adjustment; a Condition resource may also optionally be created to record the details of an impairment or an underlying condition. However, a Reasonable Adjustment may be represented by just a PatientFlag with no associated recources 9this indicates that a patient may have reasonable adjustments, but they are not available via PatientFlag).

A query should be performed prior to Flag creation to determine if there is already a reasonable adjustment flag for the patient

```
GET [baseURL]/PatientFlag?patient=[NHSNumber]&code=NRAF

```
If no reasonable adjustment flag is returned, a new one can be created.

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

The practitioner decides to record a Reasonable Adjustment Record.  

This is done with a call to the /PatientFlag endpoint

A transaction Bundle is used to help with data integrity requirements and also help to reduce required http calls.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
actor        "Patient"          as pat
participant  "FHIR API"         as api
entity       "Patient Flag"     as flg

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

pra <-- api : OperationOutcome

@enduml
</plantuml>

### Queries

Using [FHIR create](http://hl7.org/fhir/r4/http.html#create) capabilities, it is possible to create/write the Reasonable Adjustment record to the PatientFlag API.

#### Flag endpoint write

Reasonable Adjustment records are created by POSTing the resource, conformant to {{pagelink: Home/fhir-assets/profiles/england-flag-patient-flag.page.md}} to the /PatientFlag endpoint, with a body containing a transaction bundle that in turn contains the Reasonable Adjustment flag.

```
POST [baseURL]/PatientFlag
[Transaction Bundle that contains the Reasonable Adjustment Flag]

```

---

### Examples

The following set of examples constitute the individual associated resources with the initial addition of a flag for Reasonable Adjustment.  This includes a patient Flag resource, the adjustment Flag resource and the associated Condition resource.  All resources have contained provenances.

# no example for just a FLAG

* {{pagelink:Home/Examples/RA-PatientFlag-Example.page.md}}
* {{pagelink:Home/Examples/RA-Flag-Example.page.md}}
* {{pagelink:Home/Examples/RA-Condition-Example.page.md}}
* {{pagelink:Home/Examples/AddRARecordTransaction-Bundle-Example.page.md}}

The following set of examples are for the same patient, and constitute an addition flag and condition.  The transaction Bundle here illustrates an idempotent update by simply adding the new resources to the first transaction Bundle.

* {{pagelink:Home/Examples/RA-Flag2-Example.page.md}}
* {{pagelink:Home/Examples/RA-Condition2-Example.page.md}}
* {{pagelink:Home/Examples/UpdateRARecordTransaction-Bundle-Example.page.md}}

---
