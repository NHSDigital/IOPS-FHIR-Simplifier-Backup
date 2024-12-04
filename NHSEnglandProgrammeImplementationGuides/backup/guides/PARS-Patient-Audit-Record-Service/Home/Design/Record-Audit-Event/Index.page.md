## {{page-title}}

## Actors

| Actor | Description |
|-------|-------------|
| Audit Creator | The service creating the audit | 
| Audit Record Repository | Spine - The repository holding the centralised audit records | 

## Use Cases

For a background on the basic concepts see [IHE Basic Audit Log Patterns (BALP)](https://profiles.ihe.net/ITI/BALP/volume-1.html#1524-basicaudit-overview)

## Record Audit Event


<plantuml>
@startuml

hide footbox

participant proxy as "Audit Creator"

participant repository as "Audit Record Repository"

proxy -> repository: Record Audit [[https://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_RESTful-ATNA.pdf ITI-20]]

@enduml
</plantuml>

The service using the FHIR API for spine auditing sends a FHIR AuditEvent to the Audit Record Repository. 

See also [IHE RESTful ATNA (Query and Feed)](https://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_RESTful-ATNA.pdf)

```
POST https://auditrecordrepository.example.nhs.uk/FHIR/R4/AuditEvent
```
### Event Payload Example

- {{pagelink:Home/FHIR-Assets/Examples/AuditEvent-app-restricted-fhir-pds-read-Example.page.md}}
- {{pagelink:Home/FHIR-Assets/Examples/AuditEvent-patient-flag-Example.page.md}}
- {{pagelink:Home/FHIR-Assets/Examples/AuditEvent-patient-restricted-fhir-pds-update-Example.page.md}}
- {{pagelink:Home/FHIR-Assets/Examples/AuditEvent-user-restricted-hl7v3-gpsummary-read-Example.page.md}}


## Entity Mapping 

| Description | FHIR AuditEvent                                            | 
|-------------|------------------------------------------------------------|
| Type of operation - Create Read Update Delete | action                           |              
| DateTime the event happened | recorded                                                   |
| ODS code of the organisation | agent[organisation].identifier.value                       |  
| Name of the organisation | agent[organisation].display                                |  
| User identifier | agent[user].identifier.value                               | 
| User Name | agent[user].display                                        |
| ProductId or ASID of the service | agent[endpoint].who.identifier                                        |
| Role Profile ID of the user | agent[userRole].identifier.value                           | 
| Audit Creator Identifier  code | source.observer.identifier.value                           |
| Audit Creator system Identifier | source.site                                                | 
| Audit Creator Name (the system which has generated the event) | source.observer.display   |
| Patient NHS number | entity[patient].what.identifier.value                      |
| Transaction ID of the message | entity[transaction].what.identifier                        |
| Human readable interactionID | entity[endpoint].name                                      | 
| Spine Accredited System Id | entity[endpoint].what.identifier.value                     |
| HL7V3 identifier, for FHIR there is no standard | entity[endpoint].detail[interactionIdentifier].valueString |
| High level grouping of the message types | entity[endpoint].detail[productIdentifier].valueString     |
| ODS code of the organisation submitted in the message/headers | entity[submittedOrganisation].what.identifier.value        | 







           
