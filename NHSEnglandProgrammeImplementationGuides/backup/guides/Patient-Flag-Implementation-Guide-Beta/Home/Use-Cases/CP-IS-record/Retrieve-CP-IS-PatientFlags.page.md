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
skinparam dpi 72  // Lower resolution for smaller size
skinparam scale 0.6  // Scale the diagram to make it smaller

skinparam usecase {
  FontSize 10
  Width 100
  Height 50
}

skinparam actor {
  FontSize 10
}

actor "Practitioner" as practitioner

rectangle "CP-IS System" {
  usecase "Look up CP-IS Flag" as U1
  usecase "Retrieve CarePlan" as U2
  usecase "Retrieve CareTeam" as U3
}

practitioner - U1
U1 - U2 : "If CP-IS Flag exists"
U2 - U3 : "If CarePlan exists"
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

System -> FHIR: GET /CarePlan?subject=patient/[patientNHSNumber]
FHIR --> System: Returns CarePlan details

System -> FHIR: GET /CareTeam/{CareTeam_ID}
FHIR --> System: Returns CareTeam details

System --> Practitioner: Display CP-IS, CarePlan, and CareTeam Info

@enduml


</plantuml>

### Queries


Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the Patient Flag records in several ways.

#### Flag endpoint search

This section describes how to query from the [Flag](http://www.hl7.org/fhir/R4/flag.html) endpoint using [FHIR search](https://www.hl7.org/fhir/search.html)

This will return all associated Flag resources including CP-IS Flag for a given Patient.

```
GET [baseUrl]/PatientFlag?patient=[patientNHSNumber]
```

e.g:

```
GET [baseUrl]/PatientFlag?patient=9449306753
```

Example:

{{pagelink:Home/Examples/CPIS-Flag-Example.page.md}}

### GET Request for CarePlan (Using Extension Reference)

Since we linked the CarePlan to the Flag using an FHIR Extension, we now fetch the CarePlan separately:

Retrieve the CareTeam linked to a Flag:


```
GET [FHIR_BASE_URL]/CarePlan?subject=patient/[patientNHSNumber]
```

Example:

```
GET https://fhir.nhs.uk/CarePlan?subject=Patient/9449306753
```

This returns the CarePlan detail.

OR

```
GET [FHIR_BASE_URL]/CarePlan/{CarePlan_ID}
```

Example:

```
GET https://fhir.nhs.uk/CarePlan/CPP-062572
```

This returns the CarePlan detail.

Example:

{{pagelink:Home/Examples/CPIS-CarePlan-Example.page.md}}


### GET Request for CareTeam

Since we linked the CareTeam to the CarePlan, we now fetch the CareTeam separately:

Retrieve the CareTeam linked to a Flag:

```
GET [FHIR_BASE_URL]/CareTeam/{CareTeam_ID}
```

Example:

```
GET https://fhir.nhs.uk/CareTeam/LocalAuthoritySafeguardingTeam
```

This returns the CareTeam details (e.g., social workers, managing organization, contact info).

Example:

{{pagelink:Home/Examples/CPIS-CareTeam-Example.page.md}}

### GET Request to Retreive CP-IS Details in one request

```
GET [FHIR_BASE_URL]/PatientFlag?patient=[patientnhsnumber]&code=[cpis code]
```
Example:

```
GET https://fhir.nhs.uk/PatientFlag?patient=9449306753&code=child-protection-information-sharing-flag
```
This returns all the CP-IS Details in one request (i.e. Flag Details, CarePlan Details, CareTeam Details)

Example:

{{pagelink:Home/Examples/CPIS-Bundle-Example.page.md}}