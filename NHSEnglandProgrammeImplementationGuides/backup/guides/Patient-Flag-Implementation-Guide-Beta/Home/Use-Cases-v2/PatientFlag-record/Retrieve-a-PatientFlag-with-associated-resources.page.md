## {{page-title}}

### Overview

For high level requirements, {{pagelink:Home}}.

### Use Case

A Patient Flag Record of a given type may be retrieved if it exists along with all supporting Additional Detail resources.  This is done by searching the PatientFlag endpoint using both the patient and code search parameters.

**Note**: The FHIR Flag resource defintion doesn't support a code search parameter. However, the PatientFlag used in this API is based on a profile of Flag - {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}. This profile has a code search parameter defined {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}}.


<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Research" as res <<abstract>>
usecase "Retrieve Patient Flag record" as ret <<abstract>>
}

pra -- res
res <.. ret : include

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


### System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
boundary     "FHIR API"         as api
entity       "Patient Flag"     as pfg
entity       "Additional Detail"  as add

pra ->  api : Query for record
api ->  pfg : Query for record
api <-- pfg : SearchSet Bundle
opt
  loop for each Additional Detail resource type
  api ->  add : Query for records
  api <-- add : SearchSet Bundle
  end
end
pra <-- api : SearchSet Bundle
pra <-- api : OperationOutcome

@enduml
</plantuml>

### Queries

#### Flag endpoint search

Querying on both the patient and code search patameters returns a PatientFlag resource and all associated Additional Detail resources for a given patient for the flag type stated in the code parameter.
```
GET [baseUrl]/PatientFlag?patient=[patientNHSNumber]&code=[patientFlagCode]
```

e.g:

```
GET [baseUrl]/PatientFlag?patient=9449306753&code=NRAF
```

This example limits the search to PatientFlags for the patient that has the identifier `9449306753` and resources that are part of their Reasonable Adjustment flag.

---