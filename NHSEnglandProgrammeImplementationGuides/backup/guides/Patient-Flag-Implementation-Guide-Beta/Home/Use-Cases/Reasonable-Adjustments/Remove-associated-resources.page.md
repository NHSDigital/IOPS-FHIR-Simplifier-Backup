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

This is done with individual DELETE calls to the required endpoints.

The Reasonable Adjustments for a patient should be first queried from the /PatientFlag endpoint
```
GET [baseURL]/PatientFlag?patient=[NHSNumber]&code=NRAF
```
This will retrieve the Reasonable Adjust flag and associated resources for a patient. Associated recources are deleted using the .id of the resource (for example Condition.id). In addition a reason is given for the delete using a "reason" parameter.
```
DELETE [baseURL]/[ResourceType]/[ResourceType.id]?reason=[ReasonText]
```

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


#### Flag endpoint delete



##### Remove Adjustment

An adjustment has a resource type of Flag so the /Flag endpoint is used.

  ```
  DELETE [baseURL]/Flag/[Flag.id]?reason=[ReasonText]
  ``` 
For example, to delete an adjustment (represented by a Flag resource) with an id of "b8ab463d-f698-41a0-aae2-6d6163dd0825" because it was entered in error would be deleted by

```
  DELETE [baseURL]/Flag/b8ab463d-f698-41a0-aae2-6d6163dd0825?reason=Error
  ```


##### Remove Impairment/Underlying Condition

An impairment has a resource type of Condition, so the /Condition endpoint is used

  ```
  DELETE [baseURL]/Condition/[Condition.id]?reason=[ReasonText]
  ``` 
For example, to delete an impairment (represented by a Condition resource) with an id of "by095e371f-738a-45f7-b1ae-0546a4d45c71" because it no longer applies would be deleted by

```
DELETE [baseURL]/Condition/by095e371f-738a-45f7-b1ae-0546a4d45c71?reason=NoLongerApplies
```
---