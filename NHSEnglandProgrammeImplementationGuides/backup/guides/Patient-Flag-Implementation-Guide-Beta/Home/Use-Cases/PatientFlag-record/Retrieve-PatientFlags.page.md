## {{page-title}}

### Overview

For high level requirements, {{pagelink:Home}}.

### Use Case

A Patient Flag Record may be retrieved if it exists.  It will be possible to determine that adjustment flags exist by searching for a {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}   with:

- {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} and patient search parameter.


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

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the Patient Flag records in several ways.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return all associated Flag resources for a given Patient.

```
GET [baseUrl]/Flag?patient=[patientNHSNumber]
```

e.g:

```
GET [baseUrl]/Flag?patient=9449306753
```
This limits the search to Flags for the patient that has the identifier `9449306753`

This query relies on the [Flag](http://www.hl7.org/fhir/R4/flag.html#search).patient SearchParameter.

---