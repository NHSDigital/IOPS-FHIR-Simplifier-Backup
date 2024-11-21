## {{page-title}}

### Actors

| Name | Type | Description |
|------|------|-------------|
| Proxy Application | System | The application the Proxy uses |
| NHS England Proxy Repository | System | NHS England National Proxy Data Repository |

### View a Relationship 

The sequence diagram below is a high level view of the actual process which focuses on the interactions exchanged between the actors. 

<plantuml>
@startuml

participant proxy as "Proxy Application"

participant repository as "NHS England Proxy Repository"

proxy -> repository: View Relationship Request
repository --> proxy: Search Results

@enduml
</plantuml>