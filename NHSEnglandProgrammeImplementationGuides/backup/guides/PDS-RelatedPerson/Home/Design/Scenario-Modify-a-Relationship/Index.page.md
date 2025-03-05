## {{page-title}}

### Actors

| Name | Type | Description |
|------|------|-------------|
| Client Application | System | The application the user uses |
| NHS England PDS | System | NHS England Personal Demographics Service (PDS) |

### Use Case(s)

- {{pagelink:Home/Analysis/Use-Case-National-Back-Office-NBO-Updates-a-relationship.page.md}}

## Modify a Relationship

The sequence diagram below is a high level view of the actual process which focuses on the interactions exchanged between the actors.

<plantuml>
@startuml
participant "API Consumer (NBO Demographics Admin)" as API
participant "PDS FHIR API" as PDS
participant "Related Person Database" as DB

API -> PDS: Retrieve existing RelatedPerson (GET /FHIR/R4/RelatedPerson/{id})
PDS -> DB: Lookup existing relationship data
DB --> PDS: Return RelatedPerson data
PDS --> API: Return RelatedPerson resource for review

API -> PDS: Update RelatedPerson (PUT /FHIR/R4/RelatedPerson/{id})
PDS -> DB: Validate update request
DB --> PDS: Apply changes to RelatedPerson record
DB --> PDS: Confirm update success

PDS --> API: Return updated RelatedPerson with Provenance
@enduml
</plantuml>