## {{page-title}}

### Actors

| Name | Type | Description |
|------|------|-------------|
| Client Application | System | The application the Proxy or Practitioner uses |
| NHS England Proxy Repository | System | NHS England National Proxy Data Repository |

### Use Case(s)

- {{pagelink:Home/Analysis/Use-Case-View-a-Relationship.page.md}}

### View a Relationship 

The sequence diagram below is a high level view of the actual process which focuses on the interactions exchanged between the actors. 

<plantuml>
@startuml

hide footbox

participant proxy as "Client Application"

participant repository as "NHS England Proxy Repository"

proxy -> repository: View Relationship Request
repository --> proxy: Search Results

@enduml
</plantuml>