## {{page-title}}

### Actors

| Name | Type | Description |
|------|------|-------------|
| Client Application | System | The application the Proxy uses to create the request. IHE refers to this as the `Consent Recorder` |
| NHS England Proxy Service | System | NHS England National Proxy Service |
| National Proxy Registry | System | NHS England National Proxy Data Registry. IHE refers to this as the `Consent Registry` |
| Primary Care | System | General Practice System |

### Use Case(s)

- {{pagelink:Home/Analysis/Use-Case-Create-a-Relationship.page.md}}
- {{pagelink:Home/Analysis/Use-Case-Request-Access.page.md}}

### Background Standards

- [IHE Privacy Consent on FHIR (PCF)](https://profiles.ihe.net/ITI/PCF/volume-1.html)
- [HL7 Structured Data Capture (SDC) - Form Data Extraction](https://build.fhir.org/ig/HL7/sdc/extraction.html)

### Request Proxy Access

The sequence diagram below is a high level view of the actual process which focuses on the interactions exchanged between the actors. 

<plantuml>
@startuml

participant proxy as "Client Application"
participant service as "NHS England Proxy Service"
participant repository as "National Proxy Registry"
participant gp as "Primary Care"

proxy -> service : Send Proxy Access Request
service -> repository: Submit Proxy Access Request \n(IHE Access Consent - Create (ITI-108))


@enduml
</plantuml>