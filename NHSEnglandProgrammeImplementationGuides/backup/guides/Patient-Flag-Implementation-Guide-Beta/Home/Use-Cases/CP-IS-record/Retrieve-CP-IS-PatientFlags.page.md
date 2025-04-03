## {{page-title}}

### Overview

For high level requirements, see {{pagelink:Home}}.

### Use Case

- As a practitioner at an unscheduled care setting, i can look up whether a patient has a child protection plan (looked after child, Unborn child subject to child protection plan)

Authorized healthcare workers can:

 Query to determine if a patient has a Child Protection Plan
 * either as part of general PatientFlag query that returns all PatientFlags
 * or query for just Child Protection Plans for the patient & return all associated CarePlan and CareTeam resources

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

skinparam dpi 120  ' Slightly higher resolution
skinparam ParticipantFontSize 11
skinparam ActorFontSize 11
skinparam ArrowFontSize 10
skinparam BoxPadding 6
skinparam ParticipantPadding 12

actor "Practitioner" as Practitioner
participant "Unscheduled Care System" as System
participant "FHIR Server" as FHIR

Practitioner -> System: Search for CP-IS status
System -> FHIR: GET /[baseURL]/PatientFlag?patient=[patientnhsnumber]&code=[cpis code]
FHIR --> System: Returns CP-IS Flag, CarePlan, and CareTeam details
System --> Practitioner: Display CP-IS Flag, CarePlan, and CareTeam Info

@enduml

</plantuml>

### Queries


Using [FHIR search](https://www.hl7.org/fhir/search.html) capabilities, it is possible to retrieve the Patient Flag records in several ways.


### GET Request to Retreive CP-IS Details 

```
GET [baseURL]/PatientFlag?patient=[patientnhsnumber]&code=[cpis code]
```
Example:

```
GET [baseURL]/PatientFlag?patient=9449306753&code=child-protection-information-system-flag
```
This returns all the CP-IS Details in one request (i.e. Flag Details, CarePlan Details, CareTeam Details)

Example:

{{pagelink:Home/Examples/CPIS-Bundle-Example.page.md}}