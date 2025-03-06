## {{page-title}}

### Actors

| Name | Type | Description |
|------|------|-------------|
| Client Application | System | The application the user uses |
| NHS England PDS | System | NHS England Personal Demographics Service (PDS) |

### Use Case(s)

- {{pagelink:Home/Analysis/Use-Case-Match-Parents-on-General-Register-Office-GRO-Civil-Birth-Registration.page.md}}
- {{pagelink:Home/Analysis/Use-Case-National-Back-Office-NBO-Potential-Relationships.page.md}}
- {{pagelink:Home/Analysis/Use-Case-National-Back-Office-NBO-Views-a-relationship.page.md}}
- {{pagelink:Home/Analysis/Use-Case-API-Consumer-Gets-All-Related-Persons.page.md}}
- {{pagelink:Home/Analysis/Use-Case-API-Consumer-Gets-Specific-Relationship.page.md}}

### View a Relationship 

The sequence diagram below is a high level view of the actual process which focuses on the interactions exchanged between the actors. 

<plantuml>
@startuml
participant "API Consumer" as API
participant "PDS FHIR API" as PDS
participant "Related Person Database" as DB

API -> PDS: Request RelatedPerson (Parent-Child Relationship)
PDS -> DB: Retrieve Related Person Data
DB --> PDS: Return Related Person Data
PDS --> API: Return RelatedPerson (without provenance)

alt Returning with provenance
    PDS --> API: Return RelatedPerson with Provenance
end

@enduml
</plantuml>