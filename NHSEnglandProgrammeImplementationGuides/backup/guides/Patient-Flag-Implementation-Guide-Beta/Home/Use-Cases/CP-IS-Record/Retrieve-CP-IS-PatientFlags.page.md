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
  usecase "Look up CP-IS Flag" as U1
  usecase "Retrieve CareTeam Details" as U2
}

practitioner -- U1
U1 -- U2 : "If CP-IS Flag exists"
@enduml

</plantuml>


### System Interaction


<plantuml>
@startuml

actor "Practitioner" as Practitioner
participant "Unscheduled Care System" as System
participant "FHIR Server" as FHIR

Practitioner -> System: Search for CP-IS status
System -> FHIR: GET /Flag?patient={patientNHSNumber}
FHIR --> System: Returns CP-IS Flag details

System -> FHIR: GET /CareTeam/{CareTeam_ID}
FHIR --> System: Returns CareTeam details

System --> Practitioner: Display CP-IS and CareTeam Info

@enduml

</plantuml>

### Queries


Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the Patient Flag records in several ways.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return all associated Flag resources including CP-IS Flag for a given Patient.

```
GET [baseUrl]/Flag?patient=[patientNHSNumber]
```

e.g:

```
GET [baseUrl]/Flag?patient=9449306753
```
This limits the search to Flags for the patient that has the identifier `9449306753`

This query relies on the [Flag](http://www.hl7.org/fhir/R4/flag.html#search).patient SearchParameter.


### GET Request for CareTeam (Using Extension Reference)

Since we linked the CareTeam to the Flag using an FHIR Extension, we now fetch the CareTeam separately:

Retrieve the CareTeam linked to a Flag:

```
GET [FHIR_BASE_URL]/CareTeam/{CareTeam_ID}
```

Example:

```
GET https://fhir.nhs.uk/CareTeam/LocalAuthoritySafeguardingTeam
```

This returns the CareTeam details (e.g., social workers, managing organization, contact info).

### (Optional) Fetch CP-IS Flag + CareTeam in One Query

If the Flag contains an extension reference to CareTeam, you can expand the request to fetch both Flag and CareTeam in a single request:

```
GET [FHIR_BASE_URL]/Flag?subject=Patient/{Patient_ID}&_include=Flag.extension
```

Example:

```
GET https://fhir.nhs.uk/Flag?subject=Patient/123456&_include=Flag.extension
```

This returns the CP-IS Flag and automatically includes the linked CareTeam.

---




