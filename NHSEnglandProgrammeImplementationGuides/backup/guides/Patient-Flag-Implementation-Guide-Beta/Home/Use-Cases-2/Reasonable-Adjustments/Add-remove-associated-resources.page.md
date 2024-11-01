## {{page-title}}


### Overview

For high level requirements, see {{pagelink:Home}}.

#### Adjustments 

Adjustments are used to represent individual reasonable adjustments.
Adjustments SHOULD be recorded in Flag.code as a code selected from the SNOMED CT [ValueSet/England-FlagCodeRA](https://fhir.nhs.uk/England/ValueSet/England-FlagCodeRA)


#### Impairments

A Reasonable Adjustment Flag record MAY (optionally) contain further Condition resources detailing additional Impairments details
These SHALL be recorded as Condition resources with .code set to a code value from  [CodeSystem/England-ConditionCodeRA](https://fhir.nhs.uk/England/CodeSystem/England-ConditionCodeRA)

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

As an abstract PatientFlag, PatientFlag records are created by POSTing the resource to the relevant resource type endpoint. ResourceType will depend on modelling of the Additional Detail as a suitable resource within a given concrete implementation. e.g. Reasonable Adjustments uses Additional Detail resources, modelling Adjustments as[EnglandFlagPatientFlagAdjustment](https://fhir.nhs.uk/England/StructureDefinition/England-Flag-PatientFlag-Adjustment) resources ,and Impairments and Underlying Conditions as [EnglandConditionFlag](https://fhir.nhs.uk/England/StructureDefinition/England-Condition-Flag) resources.

```
POST [baseURL]/[resourceType]
```



---

---


### Remove Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Remove Patient Flag record" as rem <<abstract>>
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

The following resource types will be deleted from the record: 

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}  
* any resources detailing supporting information

#### Example

Multiple resources can be deleted using a transaction bundle.  This  {{pagelink:Home/Examples/RemoveRARecord-Bundle-Example.page.md}}:

* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} example.  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}} example.  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}} example.  

---
