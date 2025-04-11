## {{page-title}}

### Overview

For high level requirements, {{pagelink:Home}}.

### Use Case

A Patient Flag Record may be retrieved if it exists. To do this, query the PatientFlag endpoint using a patient search parameter.


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

pra ->  api : Query for records
api ->  pfg : Query for records
api <-- pfg : SearchSet Bundle
pra <-- api : SearchSet Bundle
pra <-- api : OperationOutcome

@enduml
</plantuml>

### Queries

#### PatientFlag endpoint search

This section describes how to query the PatientFlag endpoint using [FHIR search](https://www.hl7.org/fhir/search.html).

The following returns all associated PatientFlag resources for a given patient.

```
GET [baseUrl]/PatientFlag?patient=[patientNHSNumber]
```

e.g:

```
GET [baseUrl]/PatientFlag?patient=9449306753
```
This limits the search to Flags for the patient that has the identifier `9449306753`

This query relies on the [Flag](http://www.hl7.org/fhir/R4/flag.html#search).patient SearchParameter.

---