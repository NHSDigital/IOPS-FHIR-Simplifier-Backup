## {{page-title}}

### Overview

For high level requirements, see {{pagelink:Home}}.

### Use Case

A Reasonable Adjustment Record may be retrieved if it exists.  It will be possible to determine that adjustment flags exist by searching for a {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} with: 
- {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}} patient and code search parameters.

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag"{
actor Practitioner as pra
usecase "Research" as record
usecase "Retrieve Reasonable Adjustment record" as add
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
record <.. add : include

@enduml
</plantuml>

### System Interaction

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Practitioner"     as pra
participant  "FHIR API"         as api
entity       "Patient Flag"     as pfg
entity       "Adjustment Flag"  as adj
entity       "Condition"        as cod

  pra ->  api : Query for records

      api -> pfg : Query for records
      api -> adj : Query for records
      api -> cod : Query for records

  api ->  api : Assemble returns
  pra <-- api : SearchSet Bundle


@enduml
</plantuml>

### Queries

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the reasonable adjustment records in several ways.

#### Flag endpoint search 

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html#search) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)
and patient and code search parameters.

GET [baseUrl]/Flag?patient=9449306753&code=national-reasonable-adjustment-flag

This will return all associated flag resources for Reasonable Adjustments for a given patient.



e.g. 
```
GET [baseUrl]/Flag?patient=9449306753&code=national-reasonable-adjustment-flag
```
This limits the search to patients that have the identifier `9912003888`

```
identifier=9912003888
```

This limits the search to Flag resources linked via patient and have the code `national-reasonable-adjustment-flag`, and also includes the resource in the returned searchset Bundle.

Resources returned will conform to:
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag.page.md}}  
* {{pagelink:Home/FHIR-Assets/Profiles/England-Flag-Patient-Flag-Adjustment.page.md}}
* {{pagelink:Home/FHIR-Assets/Profiles/England-Condition-Flag.page.md}} 

This query relies on the [Flag patient](http://www.hl7.org/fhir/R4/flag.html#search) and {{pagelink:Home/FHIR-Assets/SearchParameters/England-FlagCode.page.md}} search parameters.

---
