## {{page-title}}


### Overview

For high level requirements, see {{pagelink:Home}}.
 
### Add Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Add Additional Detail" as add <<abstract>>
}


actor Patient as pat

usecase "Consult" as consult <<abstract>>

pat -- consult
pra -- consult
pra -- record
record <.. add : include

@enduml
</plantuml>

#### Name

*Name*

#### User Story Summary (Clinical Overview)

*User Story Summary (Clinical Overview)*

#### Actors (Role)

*Actors (Role)*

#### Frequency of Use

*Frequency of Use*

#### Triggers

*Triggers*

#### Pre Conditions

*Pre Conditions*

#### Post Conditions

*Post Conditions*

#### Main Course

*Main Course*

#### Alternate Course

*Alternate Course*

#### Exception

*Exception*


### System Interactions

The practitioner decides to record Additional Detail to support or enrich a Patient Flag record

This is achieved by POSTing resources to their relevant FHIR endpoint (for example a Condition is POSTed to a /Condition endpoint).

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"          as pat
actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Additional Detail"  as add

pra ->  pat : Consult patient
pra ->  api : Record adjustment record (transaction Bundle)

api ->  add : Create/update resource
add ->  add : Validate
api <-- add : return
alt Validation failed
  api -> api : rollback
end

pra <-- api : OperationOutcome

@enduml
</plantuml>


### Queries

Using [FHIR create](http://hl7.org/fhir/r4/http.html#create) capabilities, it is possible to create/write the Additional Detail resource, adding it to the Patient Flag record.

#### Flag endpoint write

# are they POSTing a transaction bundle to the PatienFlag endpoint?

PatientFlag records are created by POSTing the resource to the relevant resource type endpoint. ResourceType will depend on the requirements of the Additional Detail. e.g. Reasonable Adjustments uses Additional Detail resources, modelling Adjustments as[EnglandFlagPatientFlagAdjustment](https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag-Adjustment) resources ,and Impairments and Underlying Conditions as [EnglandConditionFlag](https://fhir.nhs.uk/England/StructureDefinition/England-Condition-Flag) resources.

In order for the new additional resource to be attached to the relevant PatientFlag resource, the following details must match
- NewResource.patient = PatientFlag.patient
- NewResource.category = PatientFlag.code

```
POST [baseURL]/[resourceType]
```
---

### Remove Associated Resources Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Remove Additional Detail" as rem <<abstract>>
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

# this needs updating

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

Associated resources, when not deleted as part of a PatientFlag deletion, are deleted individually, by id. To do this, PatientFlags must first be retrieved, thenassociated resources deleted using their resource.id element.

Each deletion should be accompanied by a reason in a reson parameter as part of the DELETE statement.

```
DELETE [baseURL]/[resourceType]/[id]?reason=[reason]

```
for example

```
DELETE [baseURL]/Condition/b8ab463d-f698-41a0-aae2-6d6163dd0825?reason=Error

```
# ###CHECK THESE###
#### Example

Multiple resources can be deleted using a transaction bundle.  This  {{pagelink:Home/Examples/RemoveRARecord-Bundle-Example.page.md}}:

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} example.  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}} example.  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}} example.  

---
