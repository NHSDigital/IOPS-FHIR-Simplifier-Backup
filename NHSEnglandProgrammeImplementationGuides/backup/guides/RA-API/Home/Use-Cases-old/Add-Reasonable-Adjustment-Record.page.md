## {{page-title}}

### Overview

Patient consent must be obtained before recording any adjustment or impairment. See {{pagelink:Home/Use-Cases/Consent-to-share-Information.page.md}} for details of requirements around consent.

### Usecase
After obtaining consent from a patient, a Reasonable Adjustment Record may be created.  This consists of a Flag resource containing an adjustment and a Condition resource may also optionally be created to record the details of an impairment.  

If a Reasonable Adjustment Record exists, a Flag resource designated as the patient flag must be created to indicate that there are reasonable adjustments recorded for the patient.  There is a single instance of this type of resource per patient.

<plantuml>
@startuml

skinparam actorStyle awesome

actor Practitioner as pra
package Consenter {
  actor "Patient Advocate" as pad
  actor Patient as pat
}

usecase "Consent to share information" as CON
usecase "Add Reasonable Adjustment record" as ADD

pat -- CON
pad -- CON
pra -- CON
pra -- ADD

CON <.. ADD : include

@enduml
</plantuml>

### Workflow

A practitioner performs an examination and determines that a condition and/or an adjustment should be recorded.  If the patient does not consent, no details are recorded.  If the patient consents, then the adjustment is recorded, and optionally the condition as well.

### System Interactions

The practioner decides to record a condition with the patients consent.  This could be done with individual calls to the required endpoints, or can be done in a single transaction Bundle.  A transaction Bundle can help with data integrity requirements and also help to reduce required http calls.

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
actor        "Patient"          as pat
participant  "FHIR API"         as api
entity       "Consent"          as con
entity       "Patient Flag"     as flg
entity       "Adjustment Flag"  as adj
entity       "Condition"        as cod

pra ->  pat : Examine patient
pra ->  pat : Suggest adjustments
pra <-- pat : Provide consent\nto share information

pra ->  api : Record adjustment record (transaction Bundle)

api ->  con : Create/update resource
con ->  con : Validate
api <-- con : return
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

The following set of examples constitute the individual associated resources with the intial addition of a flag for Reasonable Adjustment.  This includes the Consent resource where the patient has agreed to share information.  Also a patient Flag resource, the adjustment Flag resource and the associated Condition resource.  All resources have contained provenances.

A transaction Bundle is also given that allows these resources (plus the patient) to be entered in an atomic traction.  It uses PUTs, where in the case of an intial update, it may be done as a [conditional update](https://www.hl7.org/fhir/http.html#cond-update)

* [Consent](Consent-RAConsentExample1.html)
* [Patient flag](Flag-RAPatientFlagExample1.html)
* [Reasonable Adjustment flag 1](Flag-RAFlagExample1.html)
* [Condition 1](Condition-RAConditionExample1.html)
* [Transaction Bundle 1](Bundle-AddRARecordTransactionExample1.html)

The following set of examples are for the same patient, and constitute an addition flag and condition.  The transaction Bundle here illustates an idempotent update by simply adding the new resources to the first transaction Bundle.

* [Reasonable Adjustment flag 2](Flag-RAFlagExample2.html)
* [Condition 2](Condition-RAConditionExample2.html)
* [Transaction Bundle 2](Bundle-AddRARecordTransactionExample2.html)

### Relevant Documentation

* [Bundle](https://hl7.org/fhir/r4/bundle.html)  
* [Transaction](https://hl7.org/fhir/r4/http.html#transaction)  
* [Upsert](https://hl7.org/fhir/r4/http.html#upsert)  