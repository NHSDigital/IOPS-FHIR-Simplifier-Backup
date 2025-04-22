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

Retrieve PatientFlags

#### User Story Summary (Clinical Overview)

*User Story Summary (Clinical Overview)*

#### Actors (Role)

Practitioner
PatientFlag FHIR API
PatientFlag FHIR Repository

#### Frequency of Use

As needed

#### Triggers

Practitioner needs to see PatientFlags

#### Pre Conditions

Practitioner knows NHSNumber and/or Patient details

#### Post Conditions

Practitioner knows PatientFlags exist (or don't)

#### Main Course

1. Practitioner queries PatientFlag FHIR API with Patient NHSNumber
2. PatientFlag FHIR API queries PatientFlag FHIR Repository for PatientFlag records for Patient NHSNumber
3. PatientFlag FHIR Repository finds PatientFlag records for Patient NHSNumber
4. PatientFlag FHIR API returns PatientFlag records as searchset bundle to Practitioner

#### Alternate Course

3a. PatientFlag FHIR Repository finds no PatientFlag records for Patient NHSNumber
4a. PatientFlag FHIR API returns zero record searchset bundle to Practitioner

#### Exception

3b. PatientFlag FHIR API fails to find Patient NHSNumber
4b. PatientFlag FHIR API returns business exception OperationOutcome

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