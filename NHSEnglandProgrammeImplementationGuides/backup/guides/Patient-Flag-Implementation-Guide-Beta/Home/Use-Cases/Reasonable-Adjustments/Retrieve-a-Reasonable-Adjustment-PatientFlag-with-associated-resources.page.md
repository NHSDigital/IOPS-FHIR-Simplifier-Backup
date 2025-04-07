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

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the reasonable adjustment records.

#### Flag endpoint search 

This section describes how to query for Reasonable Adjustments from the PatientFlag endpoint using [FHIR search](https://www.hl7.org/fhir/search.html) with the patient and code search parameters.

```
GET [baseUrl]/PatientFlag?patient=[NHSNumber]&code=NRAF

```
e.g.

```
GET [baseUrl]/PatientFlag?patient=9449306753&code=NRAF

```

This will return all associated flag resources for Reasonable Adjustments for patient 9449306753 in the returned searchset Bundle.

---
