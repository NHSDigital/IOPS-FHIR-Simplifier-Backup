## {{page-title}}

### Overview

For high level requirements, see {{pagelink:Home}}.

### Use Case

- As a practitioner at an unscheduled care setting, i can look up whether a patient has a child protection plan (looked after child, Unborn child subject to child protection plan)

Authorized healthcare workers can:

- Query to check if a child has a Child Protection Plan, including:
  - Looked-After Child (LAC) status
  - Unborn child subject to a protection plan
- Retrieve details of the responsible Local Authority for further action

<plantuml>
@startuml
left to right direction
actor "Practitioner" as practitioner
rectangle "CP-IS System" {
  usecase "Look up Child Protection Plan" as U1
  usecase "Retrieve Plan Details" as U2
}

practitioner -- U1
U1 -- U2 : "If record exists"
@enduml
</plantuml>


### System Interaction


<plantuml>
@startuml
participant "Practitioner" as P
participant "Unscheduled Care System" as UCS
participant "CP-IS API" as CPIS
participant "Local Authority" as LADB

P -> UCS: Search for Patient's CP-IS Record
UCS -> CPIS: Query Child Protection Status (NHS Number)
CPIS -> LADB: Retrieve Child Protection Plan
LADB --> CPIS: Return Plan Details (if exists)
CPIS --> UCS: Return Plan Information
UCS --> P: Display Protection Plan Details
@enduml
</plantuml>

### Queries

Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the CP-IS Patient Flag records in several ways.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return all associated CP-IS records for a given Patient.

```
GET [baseUrl]/Flag?patient=[patientNHSNumber]
```

e.g:

```
GET [baseUrl]/Flag?patient=9449306753
```
This limits the search to Flags for the patient that has the identifier `9449306753`

This query relies on the [Flag](http://www.hl7.org/fhir/R4/flag.html#search).patient SearchParameter.





