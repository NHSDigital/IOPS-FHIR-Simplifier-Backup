## {{page-title}}


### Overview

For high level requirements, see {{pagelink:Home}}.

#### Adjustments 

  Adjustments are used to represent individual reasonable adjustments.
  Adjustments SHOULD be recorded in Flag.code as a code selected from the SNOMED CT valueset [https://fhir.nhs.uk/England/ValueSet/England-FlagCodeRA] (https://fhir.nhs.uk/England/ValueSet/England-FlagCodeRA)


#### Impairments

  A Reasonable Adjustment Flag record MAY (optionally) contain further Condition resources detailing additional Impairments details
  These SHALL be recorded as Condition resources with .code set to a code value from CodeSystem [CodeSystem/England-ConditionCodeRA](https://fhir.nhs.uk/England/CodeSystem/England-ConditionCodeRA)

#### Underlying Conditions

  A Reasonable Adjustment Flag record MAY (optionally) also contain further Condition resources detailing Underlying Conditions that are relevant to provision of reasonable adjustments to care
  These SHALL be recorded as Condition resources with .code set to the relevant SNOMED CT concept


### Add Use Cases

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag (Reasonable Adjustments)"{
actor Practitioner as pra
usecase "Record" as record
usecase "Add Adjustment" as addadj
usecase "Add Impairment" as addimp
usecase "Add Underlying Condition" as addcond
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
record <.. addadj : include
record <.. addimp : include
record <.. addcond : include

@enduml
</plantuml>

### System Interactions

The practitioner decides to record additional detail to support or enrich the Reasonable Adjustment Flag record

This could be done with individual calls to the required endpoints, or can be done in a single transaction Bundle.  A transaction Bundle can help with data integrity requirements and also help to reduce required http calls.

#### Add Adjustment

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

api ->  adj : Create/update resource
adj ->  adj : Validate
api <-- adj : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>

#### Add Impairment/Underlying Condition

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

api ->  cod : Create/update resource
cod ->  cod : Validate
api <-- cod : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>



### Queries

Using [FHIR create](http://hl7.org/fhir/r4/http.html#create) capabilities, it is possible to create/write the Additional Detail resource, adding it to the Patient Flag record.

#### Flag endpoint write

Following the standard ReST pattern `POST [baseURL]/[resourceType]` for create operations, to:

Add Adjustment

  Use `POST [baseURL]/Flag` with query payload a Flag resource conformant with profile {{pagelink: Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}}

Add Impairment/Underlying Condition

  Use `POST [baseURL]/Flag` with query payload a Flag resource conformant with profile {{pagelink: Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}}

---