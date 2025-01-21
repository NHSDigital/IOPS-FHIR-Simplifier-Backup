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

### View a Relationship 

The sequence diagram below is a high level view of the actual process which focuses on the interactions exchanged between the actors. 

<plantuml>
@startuml

hide footbox

participant proxy as "Client Application"

participant repository as "Personal Demographics Service"

proxy -> repository: View Relationship Request
repository --> proxy: Search Results

@enduml
</plantuml>