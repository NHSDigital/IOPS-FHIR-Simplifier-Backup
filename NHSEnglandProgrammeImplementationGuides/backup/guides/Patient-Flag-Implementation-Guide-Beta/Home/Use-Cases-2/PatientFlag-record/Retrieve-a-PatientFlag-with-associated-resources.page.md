## {{page-title}}

### Overview

For high level requirements, {{pagelink:Home}}.

### Use Case

A Patient Flag Record of a given type may be retrieved if it exists along with all supporting Additional Detail resources.  It will be possible to determine that adjustment flags exist by searching for a {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} with:

- {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} patient and code search parameters.


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

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the reasonable adjustment records in several ways.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return Patient Flag resource of set type and all associated Additional Detail resources for a given Patient.

```
GET [baseUrl]/Flag?patient=[patientNHSNumber]&code=[type]
```

e.g:

```
GET [baseUrl]/Flag?patient=9449306753&code=national-reasonable-adjustment-flag
```

This limits the search to Flags for the patient that has the identifier `9449306753` and are part of the Reasonable Adjustment flag


This query relies on the [Flag](http://www.hl7.org/fhir/R4/flag.html#search) SearchParameter.

---

This query relies on the {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}}, and {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagDetail.page.md}} SearchParameters.

---
